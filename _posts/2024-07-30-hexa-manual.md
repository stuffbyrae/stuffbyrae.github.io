---
title: HEXA Manual
tag: hexa
desc: How to get started and conquer the universe!
---
![HEXA](/blog/images/2024-07-30-1.png)

## Synopsis

> Board the helm of Starship HEXA, and conquer the universe the only way you know how: shapes.

You're the commander of Starship HEXA, the head of a space fleet dead-set on taking over the universe. You're well on your way to assuming control of everything that is and shall be, but your attack methods are a bit...unorthodox. We can't dwell on it for too long, though, so get out there and match those hexagons!

HEXA is a unique, quick to pick up, and super fun logic puzzle game based on everybody's favorite polygon. Try for a high score in Arcade Mode, take on the dynamic Daily Run; or conquer dozens of unique challenges in Mission Mode! See if you can't conquer the HEXAPLEX, wrangle those Power-ups, and maybe even become ruler of the universe along the way.

Give it a try... it's *HEXA-good!*

# Gameplay Basics

## Controls

The d-pad and A and B buttons are required to play this game. These buttons are used to navigate menus, and are mandatory in main gameplay.

You can also optionally use the crank to perform the turning action usually done by the A and B buttons. This can be toggled in the Options menu. (The crank can also be used to navigate menus.)

## Gameplay

When you start a new game, you'll be faced with the HEXAPLEX — a grid of 19 triangles (black, gray, or white), all interlaced with one another. Your goal is simple: create HEXAs!

Use the D-pad to navigate your Cursor along the HEXAPLEX, and the A and B buttons (or the crank) to rotate the currently-selected hexagon clockwise or counter-clockwise — this is called a Swap.

A full hexagon of similarly-colored triangles is called a HEXA. These are the main way to earn points — create a HEXA match, and BOOM!! You gain points, and the triangles involved are randomized and replaced.

As far as basic gameplay is concerned...that's all you gotta know to get started! But, depending on the mode you're playing, there are a few more things you need to learn...

# Modes

## Arcade Mode

Arcade Mode is the basic gameplay mode in *HEXA*.

In this mode, you start out with 45 seconds on the clock. As you match HEXAs, you'll earn points, as well as more time on the timer! Your goal is to match as many HEXAs, and thus, earn as many points, as you can before time runs out. White tiles earn you 100 points, gray tiles earn you 150 points, and black tiles earn you 200 points.

There's another element to this mode to keep you on your toes: randomly-generated Power-ups! These do various different things when matched:

- Bombs — If matched into a HEXA, the whole board gets "blown up" and replaced with a new, randomized set of tiles.
- 2x Tiles — When matched into a HEXA, you'll earn double points for that match! Plus, a bigger timer boost.
- Wild Tiles — These tiles can be used in place of any other color when creating a HEXA. No penalty nor reward.

Power-ups will not stack up with themselves. For example, if you have multiple 2x Tiles in a match, you'll still only receive one bonus. However, Power-ups *will* stack with eachother — if a match contains a 2x Tile and a Bomb, you'll get double points *and* reshuffle the entire board.

You can also score HEXA Combos — if you match a HEXA, and the resulting grid contains another HEXA, BOOM!! You'll get double the points for that match! This stacks exponentially up until you reach a board state without an immediate HEXA. These are mostly luck-based, but it's possible to create them intentionally if you really know what you're doing.

As you earn more HEXAs, the timer boost will gradually become less and less effective. See how long you can keep it rolling!

The game will end when the timer reaches zero. If you wanna end it early, open the Slide menu and just select "end game". The game will end from the current point, and any high scores will be saved.

## Chill Mode

Chill Mode is a more relaxed experience, meant for casual play.

In this mode, there's no score-keeping, Power-ups, or timers. The goal is just to chill out, and have a good time creating HEXA matches at your own pace!

To end the game, open the Slide menu and select "i'm done!" to wrap up.

## Daily Run

Daily Run plays a lot like Arcade Mode, but with one big catch: you only get one shot per day!

In this mode, the board is *seeded* — every day, you play with the same starting layout as everyone else. From here, it plays just like Arcade Mode!

When you end the game, you won't be able to play again until tomorrow. The Daily Run refreshes automatically at 00:00 midnight GMT, after which you'll be able to play another game with a new layout.

> 💡 *There's also a handy timer on the Title screen to let you know when the next run will appear!*

# Mission Mode

In Mission Mode, 50 new challenges await you! These can be grouped into four distinct modes:

- Picture: In this mode, there are no HEXAs! Perform Swaps from a random state to try and create the picture in as little Swaps as possible.
- Time Attack: This plays like Arcade Mode, except...you get no time bonus for HEXAs! See how much of a score you can nab in the time allotted!
- Logic: From a determined starting layout, try and clear the condition using as little Swaps as possible! No time limit or pressure.
- Speedrun: Plays like Logic — complete the clear condition — but instead of Swaps, do it as fast as possible!

A new mission will unlock as soon as you clear the latest. If you're ever feeling stuck, open the Slide menu to get another look at your objective.

> 💡 *In Picture puzzles, the Slide menu will also show the picture you're trying to re-create!*

# Custom Missions

Keep the fun going with custom missions! Accessible from the Mission Mode menu, these optional level packs can provide infinite world-conquering content.

## Importing Custom Missions

Follow these steps to import custom missions:

1. Access Data Disk Mode on your Playdate by following [these steps](https://help.play.date/games/sideloading/#data-disk-mode).

2. Navigate to <span class="code-span">Data/wtf.rae.hexa/missions</span>.

3. Drop all your custom mission JSON files straight into the root of this missions folder. Don't put 'em outside, or within any sub-folders!

4. Exit Data Disk Mode, launch HEXA, and enter the Mission Mode menu.

5. From here, open the Slide menu, and enable "custom". If your missions got imported correctly, you should see them listed here in date order!

> 💡 *If you've sideloaded your copy of HEXA, you can still play Custom Missions — but your save data will be in a different place! Look for the same folder within Data, but prepended with "user.XXXX.".*

# On-line Capability

## About on-line play

This game connects to Playdate's on-line leaderboard API, to enable sending and receiving of high scores among players across the globe. To use on-line functionality in this game, make sure your Playdate has an active Wireless connection.

## Submitting your scores

The Arcade Mode and Daily Run both support global on-line leaderboards. You're not the only one competing for the universe — go for the top spot!

To submit a new score to a global leaderboard, simply complete a game. When you reach the end results screen, your score will be submitted to the proper leaderboard automatically.

> ⚠️ *Be careful — if you close out of the game without properly ending your run, your score won't be saved or submitted!*

## My score didn't send! What do?

If you obtained a new high score, but it didn't get sent up to the appropriate leaderboard, there are a few things you can try:

1. Give it a little time, and see if it sends up automatically.

2. Try playing another round — it doesn't need to be *yet another* new high score, but this might kick the OS' caching into high gear.

3. Try checking the scoreboards in-game (see below), which will attempt to send a "fake score" and bump the cache.

## Viewing global scores

You can view global scores using two primary methods:

1. Visit the *HEXA* game page in your Web browser, at [play.date/games/hexa](https://play.date/games/hexa/). From here, you can view all available scores in the Scoreboards section. You can see top 10 scores in every available board.

2. Enter the 'High Scores' menu within the game, accessible from the Title screen. When in this screen, you can use the A button to toggle between the Arcade Mode and Daily Run leaderboards. From here, you can see the top scores for the currently-highlighted board, as well as your own score and ranking (if available).

The Daily Run leaderboard refreshes automatically at 00:00 midnight GMT, clearing all scores from the past day. When viewing scores in-game, there's also a handy timer to tell you when the boards will be cleared.

# Strategies

Here are a couple tips to hopefully help you conquer the HEXAPLEX!

- Know your difference between clockwise and counter-clockwise.
- It's easier to fill a gap of two than it is to fill a gap of one.
- Plan for the tiles that reward higher points!
- Make use of power-ups when possible, and especially when beneficial.
- The crank can perform Swaps faster, but is harder to dial in precisely.
- Use bombs at opportune times to reshuffle a poor layout!
- When in doubt, just take a moment to study the board. You've got more time than you think!

# Enhanced Sound Pack

As of v2.1.0, HEXA comes packed with compressed mono music tracks to ensure a balance of fidelity and a more manageable download speed. For a crisper, stereo quality, please download the *Enhanced Sound Pack*. This replaces the in-game audio files with higher-fidelity tracks, at the cost of a larger file size.

> ⚠️ *Installing the Enhanced Sound Pack is an advanced maneuver! If done improperly, it could lead to game crashes, or loss of precious data. Please navigate your Playdate's Data Disk responsibly!*

<a href="https://rae.wtf/hexa/enhanced-sound-pack.zip" class="button">Download the HEXA Enhanced Sound Pack — 26.4 MB</a>

To install the Enhanced Sound Pack:

1. Access Data Disk Mode on your Playdate by following [these steps](https://help.play.date/games/sideloading/#data-disk-mode).

2. Navigate to <span class="code-span">Games/Purchased/HEXA.pdx</span>, and open it. (If you're in MacOS, you may need to right-click and select "Show Package Contents".)

3. Navigate to <span class="code-span">audio/music</span>. Replace the files inside with the files contained inside the Enhanced Sound Pack.

That should be all you need to enjoy top-quality stereo sound! Plug in your headphones, and enjoy.

> ⚠️ *If your HEXA game file enters an unrecoverable state, please un-install and re-install it from your Playdate directly, in Settings > Games.*

# Credits

- Art and code — [Rae](https://rae.wtf)
- Music — [Watson at MusMus](https://musmus.main.jp); [Terms](https://musmus.main.jp/info.html)
- SFX — [JSFXR](https://sfxr.me)
- [Tanuk](https://github.com/Schyzophrenic/Tanuk_CodeSequence) library — [Toad](https://toadleyundercontrol.itch.io/) and [Schyzo](https://twitter.com/Schyzo99); [MIT](https://github.com/Schyzophrenic/Tanuk_CodeSequence/blob/main/LICENSE)
- Full Circle and Mikodacs Clock fonts — [Panic](https://panic.com); [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- [Righteous](https://fonts.google.com/specimen/Righteous) font — Astigmatic; [OFL](https://openfontlicense.org)
- Addtl. code — [lua-users wiki](http://lua-users.org/wiki/FormattingNumbers) and [Drew-Lo](https://aloebach.itch.io)
- Thanks — Voxy, Toad, scizzorz, superfunc, Mag, Hunter Bridges, Scenic Route, DRD, IGDA Twin Cities, and Panic!

# Additional Notes

This game started life on the 4th of July, 2024. It came together pretty much over the weekend — initially being sent to the Catalog on July 7th, and approved on the 10th. The game was originally scheduled for release on August 13th, 2024, before suddenly having the opportunity to jump back and instead release on July 30th. This means that the game went from "start of development" to "literally out for people to buy" in just under a months' time. New record!!

Special thanks to the folks in the Catalog dev chat for being there to witness my tomfoolery throughout development, and everybody who helped out and cheered me on as this game barreled through the finish line. And thanks to you, for reading, playing, and (hopefully) enjoying!

# Changelog

<!--
## Version 2.1.5

- Added achievements! [Learn more here.](https://github.com/PlaydateSquad/pd-achievements)
-->
## Version 2.1.2
### 02.07.2025
- *Actually* fixed crash that sometimes fired upon entering Mission Mode

## Version 2.1.1
### 01.15.2025

- De-looped music tracks. Whoops!
- Fixed crash that sometimes fired upon entering Mission Mode
- "Hard Mode" is now available as a direct toggle in the Options menu
- Added slight deadzones to swapping with the crank

## Version 2.1.0
### 01.06.2025

- Fix wi-fi cauterization in sideload copies
- Edit static list icon to be more visually interesting
- Compress music to get file size from ~30 MB down to <10. For original quality, check out the [enhanced sound pack](https://rae.wtf/blog/hexa-manual#enhanced-sound-pack)
- Music now also loops a bit more appropriately
- Add hidden "Hard Mode" in Arcade/Daily Run
- Swap SFX quietened
- Added support for importing Custom Missions
- Fixed bug with "flip rotation" setting mid-game
- If all missions are beaten, the mission screen will now start at the beginning of the list instead of the end
- B button will now skip end card as well as A
- The crank can now be used to scroll through missions
- In a situation with multiple HEXAs, any with bombs will be de-prioritized to avoid unfortunate scenarios
- Added cranking deadzone of 5º
- Enhanced scene management optimization

## Version 2.0.0
### 08.13.2024

- Added Mission Mode! 50 all-new challenges to complete across four unique game-modes!
- Adjusting round end behavior to fix potential soft lock.
- Pause preview is now hidden for time-sensitive game modes.
- Added additional "2:1" option for crank sensitivity.
- Removed brief timeout between Swaps
- Fixed bug where randomized tag would show up twice in ending card, in specific scenarios
- Hopefully fixing a bug with Daily Run metrics not saving.
- Commalizing best scores on Title screen
- Additional gameplay tweaks and fixes.

## Version 1.1.0
### 08.05.2024

- Fixed a bug where restarting the game wouldn't properly clear the timer.
- The user can now press A to skip the fanfare mid-way through, if "Skip Fanfare" setting is off.
- Added Jukebox, which cycles through the game's music tracks randomly with a nice screensaver.
- Rewording How to Play section slightly to make some game rules more clear.
- Show scores for Arcade Mode and Daily Run on the Title screen, if applicable.
- Fixed a bug in Options where some SFX weren't playing correctly.
- Added all-time Swap and HEXA tracking to the Options menu, starting with the release of v1.1.0.
- Fixed potential bug in Daily Run on-line score caching.
- Reworded "Local Scores" to "Local Stats" in Options; this function now clears Swaps/HEXA counts too.

## Version 1.0.0
### 07.30.2024

- Initial release.

<br>
<a href="https://play.date/games/hexa" class="button">Buy <i>HEXA</i> in Catalog</a>
