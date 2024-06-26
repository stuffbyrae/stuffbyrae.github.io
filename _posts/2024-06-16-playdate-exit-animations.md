---
title: Playdate Exit Animations
tag: blog
desc: How to abuse the termination callback for your own personal gain.
---
Hello!

If you've come across this blog post, you're likely a Playdate dev who's just seen something like this —

![](/blog/images/2024-06-16-1.gif)

— a cool animation that happens *after* the player exits back to the Launcher, providing a nice smooth transition. And you may be wondering how to do that for yourself! Luckily, this is the authoritative guide on *Making a Cool Exit Animation for your Playdate Game*. Let's go!

The base of this trick is in the [<span class="code-span">playdate.gameWillTerminate()</span>](https://sdk.play.date/2.5.0/Inside%20Playdate.html#c-gameWillTerminate) function. This allows you to run code after the player exits the game to go home.¹ Ordinarily, this function is used for reasonable things, like saving the game's state. However, with some funny little trickery, we can use this for whatever we want before the game closes.

There are two more special things that make this trick possible: <span class="code-span">while</span> loops, and [<span class="code-span">playdate.display.flush()</span>](https://sdk.play.date/2.5.0/Inside%20Playdate.html#f-display.flush).

If you know Lua code already, you should be familiar with <span class="code-span">while</span> loops — they catch the code and keep it running a specific loop until its condition is not met anymore. For example, something like this...

{% highlight lua %}
local foo = 0
while foo ~= 10 do
	foo = foo + 1
end
{% endhighlight %}

...will loop through 10 times, incrementing <span class="code-span">foo</span> by 1 each time. When it reaches 10, the <span class="code-span">while</span> loop's condition stops being met, and so it stops iterating.

<span class="code-span">playdate.display.flush()</span> is responsible for manually updating the Playdate screen. When you're running functions such as <span class="code-span">playdate.gameWillTerminate()</span>, your game's usual update code is not being run. On one hand, this is nice because it means you don't have to worry about your game's code continuing to update and possibly messing stuff up while your game is paused or closing. On the other hand, it means <span class="code-span">playdate.update()</span>, which is responsible for updating the screen normally, isn't running at all. So this function's important to make sure things are displaying.

We can combine all these components to make something graphical happen over a period of time, upon the <span class="code-span">playdate.gameWillTerminate()</span> function being called. Here is an example code snippet demonstrating a basic use case:

{% highlight lua %}
function playdate.gameWillTerminate()
	local img = playdate.graphics.getDisplayImage()
	local byebye = playdate.graphics.imagetable.new('byebye')
	local byebyeanim = playdate.graphics.animator.new(1500, 1, #byebye)
	playdate.graphics.setDrawOffset(0, 0)
	while not byebyeanim:ended() do
		img:draw(0, 0)
		byebye:drawImage(math.floor(byebyeanim:currentValue()), 0, 0)
		playdate.display.flush()
	end
end
{% endhighlight %}

Let's break this down quickly.

When the <span class="code-span">playdate.gameWillTerminate()</span> function is called:

- <span class="code-span">img</span> is created, which essentially takes a picture of the last thing your game was showing before you ran the close function. We gotta make sure to save this, or else it wouldn't display otherwise.
- <span class="code-span">byebye</span> is created; an imagetable depicting some kind of closing animation. 400x240 resolution is recommended, but transparency is OK (the game's snapshot will be drawn under this!)
- A Playdate animator is created, to travel from 1 to the length of the imagetable over the course of a second and a half (this can be adjusted to whatever length you like²)
- Also, the graphics' draw-offset is reset back to the origin point. Depending on what happens in your game, this might not be necessary, but if you do use draw-offset in your game code make sure to reset this, or else any graphics you have won't be drawn on-screen.
- Now, the <span class="code-span">while</span> loop — this essentially is running through repeatedly, checking if the animator has ended yet. If not, it proceeds to draw to the display; first laying down the game snapshot, then drawing the current frame of the imagetable (this value is floored since it only accepts integers), and then the all-important <span class="code-span">playdate.display.flush()</span> is called to make it appear on-screen.

After the animation has ended, the <span class="code-span">while</span> loop will stop iterating, and the OS will close your game as normal.

A couple more notes about usage:

- Since <span class="code-span">playdate.update()</span> isn't around to manage the FPS, This <span class="code-span">while</span> + <span class="code-span">playdate.display.flush()</span> combo will refresh the screen as fast as it possibly can. Make sure nothing inside your loop relies on frame-based timing, as it will run *way* faster than expected.
- You can absolutely run other code alongside this – just make sure that any additional code you add is *not* placed inside the <span class="code-span">while</span> loop! Otherwise, it will run hundreds and hundreds of times every time your game closes; and that's not too great.
- If created inside the <span class="code-span">playdate.gameWillTerminate()</span> loop, you can use the Playdate's [sampleplayer](https://sdk.play.date/2.5.0/#C-sound.sampleplayer) function to play sound effects as part of your exit animation as well!³

[Swap Machina](https://play.date/games/swap-machina) was the first game to apply this tactic, adding it in a post-launch update. This game's dev, [NaOH](https://nstbayless.github.io), gets all the credit for discovering how to put all this together and make a super cool effect! I just like spreading the word about how to use it because it's a really neat trick and every dev I've seen put it in a game seems to use it in a super unique way. You can see the original source code⁴ for the effect in Swap Machina [here](https://discord.com/channels/675983554655551509/675983555209330691/1131269469902217327) (link to within the Playdate Squad Discord server). You should also check out Swap Machina on Catalog — it's pretty great!

Here are a few more examples of games with cool-as-heck exit animations:

- Reel-istic Fishing, from Toad (pictured at the start of this article)
- Platform 10 & Diction, from Dr. Gabe
- Diora, from The3DPrintist
- Shift II from Scenic Route Software uses it as a funny easter egg

Anyway, that should be all you need to know to get started! If you make a rad exit animation for your game, feel free to let me know! I'd love to see it.

<hr>

¹It should be noted that there are similar functions for things such as locking & unlocking the device, opening and closing the system menu, and letting the device go to sleep as it runs out of battery. This tactic could work with these as well, but just keep in mind the player's patience level as these can be more repetitive actions (for example, a player wouldn't wanna see a 10-second animation play out every time they open the menu). Also, when it comes to device unlocking, your regular update code starts running just before the function is called.

²When using this technique, make sure that your code doesn't run for over 10 seconds consecutively. Playdate has a "watchdog" that constantly checks the last time <span class="code-span">playdate.update()</span> has been called. If it hasn't run in over 10 seconds, it will assume your game is stuck in an endless loop or otherwise frozen (because it, technically, is); and crash the whole system to bail the user out of it.

³Combine this with the points brought up in footnote 1, and you can do hilarious stuff like [this](https://youtu.be/D5gCeK8DPRY).

⁴Swap Machina was created with Pulp, and then converted to Lua to add extra juice using their [Pulp Mill](https://github.com/nstbayless/pulp-to-lua) tool. Unfortunately, I don't think it's possible to implement such an effect in a Pulp game without first converting it to Lua. Sorry!