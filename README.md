# Galaxycraft

**Not to be confused with M0uiDev's Minecraft IN Super Mario Galaxy 2 mod**

**I did not write this README. It was written entirely by Claude. I am working on making my own README though so it comes from me :3**

AI part starts here :p
**Galaxycraft** is a Fabric mod for **Minecraft 1.21.1** that turns you into Mario (or Luigi) from *Super Mario Galaxy*: his moves, physics, animations, voice, music, HUD and death sequence, all taken from the game itself.

**Current version: 1.0.0 Stable**. Grab it from [Releases](../../releases).

> **This mod contains no Nintendo files.** On launch it reads Mario's model, animations, sounds, music and HUD from **your own** extracted copy of Super Mario Galaxy. Without the game files the mod stays switched off and Minecraft plays like vanilla. Please don't share game files.

## Features

- **SMG movement:** running, skidding, side flip, backflip, long jump, triple jump, wall jump, spin, ground pound, ledge grab, and SMG swimming. Uses the game's own physics values.
- **Stomping:** jump on enemies to hurt them and bounce off. Hold jump to go higher; every third stomp in a row goes higher still.
- **Play as Luigi** with his own physics, voice and animations.
- **Power-ups** (creative tab "SMG Power-Ups", structure chests, or `/powerup`), drawn with their real 3D models:
  - Fire Flower: spin to throw bouncing fireballs (Fire Mario music)
  - Ice Flower: water freezes under your feet (Ice Mario music)
  - Rainbow Star: invincible, faster, defeats anything you touch (Rainbow Mario music)
  - Red Star: fly where you look, spin to dash (Flying Mario music)
  - Bee Mushroom: fly until the gauge runs out
  - Boo Mushroom: float up, spin to turn see-through
  - Spring Mushroom: constant bouncing, super bounce if you jump as you land
  - Life Mushroom: life meter grows to 6
  - 1-Up Mushroom: +1 life
- **The game's HUD:** life meter, star counter, lives, coins (XP) and star bits, from SMG's own layout files. Counters slide in when you stand still, count up with a flash, and the life meter shakes on damage and beeps at 1.
- **SMG damage:** every hit takes exactly one segment, with SMG knockback. Lava and fire do the burn jump. XP orbs are coins and refill the life meter; 50 coins = 1-Up.
- **SMG's miss sequence:** the world darkens, TOO BAD!, the Bowser wipe, the lives counter, and GAME OVER at 0 lives, all with the game's timing. Mario only goes down once he lands from the last hit. His death animation depends on how he went down (burnt, electrocuted, drowned, buried, falling, on his back, face down, sitting).
- **Music and sounds from the game:** power-up themes, Lose Life and Game Over, footsteps, voices.
- **SMG objects:** coins, star bits, launch stars, sling stars, black holes, trampolines, coin blocks, Power Stars.
- **Timer challenges and Prankster Comets** (Speedy, Daredevil, Purple Coin, Cosmic, Fast Foe).
- **SMG camera, idle sleep, footstep dust**, and more.
- **Multiplayer:** everyone sees each other's character, power-up form and animations.
- **Configurable:** life, damage, knockback, attack damage, lives, Game Over penalty (none, drop items, lose items, spectator or kick) and lots more, in-game or in the config file.

## Requirements

- Minecraft **1.21.1** with **Fabric Loader**
- [Fabric API](https://modrinth.com/mod/fabric-api) for 1.21.1
- [Mod Menu](https://modrinth.com/mod/modmenu) (optional, for the in-game settings screen)
- An **extracted** copy of **Super Mario Galaxy** (Wii, US/EU, game ID RMG**01). Not the .iso.

## Install

1. Make a Minecraft 1.21.1 Fabric instance (Prism Launcher, the Fabric installer, etc.).
2. Put `galaxycraft-<version>.jar` (e.g. `galaxycraft-1.0.0-stable.jar`) and Fabric API in the instance's `mods` folder. Delete any older Galaxycraft or smgmario jar.
3. Launch the game once, then close it. This creates `config/smgmario.properties`.
4. Open `config/smgmario.properties` and set `smgPath` to your extracted game folder, for example:
   ```
   smgPath=/Users/you/Games/SMG
   ```
   On Windows use forward slashes: `smgPath=C:/Games/SMG`
5. Launch again. Chat says **"Super Mario Galaxy files loaded"**, or tells you what's missing.

### Extracting the game

In Dolphin: right-click Super Mario Galaxy, then **Properties > Filesystem**. Right-click the disc and choose **Extract Entire Disc**. Point `smgPath` at the folder you extracted to (the one that contains `DATA` or `files`).

## Controls

| Move | How |
|---|---|
| Toggle Mario / normal | **M** |
| Run, jump, crouch | WASD, Space, Sneak |
| Long jump | Sneak while running + Jump |
| Backflip | Sneak + Jump while standing |
| Side flip | Turn around while running + Jump |
| Triple jump | Jump three times in a row while running |
| Spin | **R** (Fire Mario throws a fireball) |
| Ground pound | Sneak in mid-air |
| Wall jump | Jump while sliding down a wall |
| Stomp | Land on an enemy (hold Jump to bounce higher) |
| Swim | Jump = stroke, hold Jump or W = flutter kick, Sneak = dive, R = spin dash |

## Commands

| Command | What it does |
|---|---|
| `/powerup <type> [player]` | Give a power-up |
| `/smgtimer [seconds]` / `/smgtimer stop` | Start or stop a timer challenge |
| `/comet speedy\|daredevil\|fastfoe\|purple\|cosmic\|off` | Start or stop a Prankster Comet |

## Settings

Everything can be changed in-game through Mod Menu, or in `config/smgmario.properties` (every option has a comment explaining it). Some highlights:

| Option | Default | What it does |
|---|---|---|
| `maxLife` | 3 | Life meter segments |
| `startingLives` | 4 | Lives at the start and after a Game Over |
| `gameOver` | none | Game Over penalty: `none`, `drop_items`, `clear_items`, `spectator`, `kick` |
| `keepItemsOnMiss` | false | Keep items and XP when you lose a life but have lives left |
| `stomp` / `stompAllMobs` | true / false | Stomping, and whether non-monsters can be stomped |
| `stompDamage`, `spinDamage`, `groundPoundDamage`, `fireballDamage` | 6, 3, 5, 4 | Attack damage in half-hearts |
| `smgCamera` | true | SMG-style camera |
| `smgDeath` | true | SMG miss sequence instead of the death screen |

## Multiplayer

Install the mod on the **server** too, so power-ups, damage, stomps and Game Over penalties work. Each player needs their own game files. Players without the mod see normal Steves.

## Versions

Releases are named **X.X.X Stable** (tested and ready to play) or **X.X.X Beta** (everything before 1.0.0, still being tested).

### 1.0.0 Stable
First stable release.
- Everything from the betas, plus: Mario keeps facing the way he was when he dies (he used to spin around with the camera).
- Fixed Game Over penalties and SMG death animations not working (the server never saw Mario's death).
- Falling out of the world works like Galaxy: the camera stops where it is and smoothly turns to watch Mario fall away.
- The mod is now called **Galaxycraft** (jar files are `galaxycraft-<version>.jar`). The config file is still `config/smgmario.properties`, so your settings carry over.

### 0.12.0 Beta
- Stomping: land on an enemy while falling to hurt it and bounce off, using SMG's logic. Hold jump to bounce higher; every third stomp in a row goes higher still. By default only monsters can be stomped (`stompAllMobs` adds other mobs, never your own pets).
- Configurable attack damage: spin, ground pound, fireball, stomp, Rainbow Mario.
- Death animations match how Mario went down: burnt, electrocuted, drowned, buried, falling into the void, crushed, knocked onto his back or face down.
- Game Over penalty option: none, drop items, lose items, spectator (hardcore style) or kick. Optional keeping items when you still have lives left.
- Fixed the vanilla death screen flashing after TOO BAD! / GAME OVER.
- The life meter number is centered properly.

### 0.11.2 Beta
- Smooth HUD textures, like on the Wii.

### 0.11.1 Beta
- Fixed a crash when loading into a world.

### 0.11.0 Beta
- Music comes from the game files (no separate music needed).
- Footstep, jump and landing sounds and dust; spin sparkles.
- Idle sleep, ledge grab, SMG camera (toggleable).
- Luigi's own animations.
- Multiplayer: correct character, power-up form and animations for every player.

### 0.10.0 Beta
- Timer challenges (`/smgtimer`) and Prankster Comets (`/comet`) with their sounds and HUD.

### 0.9.0 Beta
- SMG Objects creative tab: coins, star bits, launch and sling stars, black holes, trampolines, coin blocks, Power Stars.
- Power-ups can show up in structure chests.

### 0.8.0 Beta
- Play as Luigi.

### 0.7.0 Beta
- In-game settings screen (Mod Menu).

### 0.6.0 - 0.6.2 Beta
- Miss sequence with SMG's exact timing: TOO BAD!, Bowser wipe, lives counter, GAME OVER.
- Full jingles (1-Up, power-up, coins, low-life beep).
- Many new config options.

### 0.5.0 - 0.5.1 Beta
- Power-ups, SMG swimming, burn jump, life meter, SMG knockback, delayed death, the game's HUD.

### 0.1.0 - 0.4.0 Beta
- First versions: Mario's model, SMG movement and physics, face and hand animations.

## Reporting bugs

Open an issue with:
- what happened and what you expected
- the mod version
- your `latest.log` (and the crash report if the game crashed)

## Credits

- Movement, animation and sequence logic is based on the [Petari](https://github.com/SMGCommunity/Petari) Super Mario Galaxy decompilation.
- Super Mario Galaxy is © Nintendo. This is a fan project and is not affiliated with or endorsed by Nintendo.
- **This mod was vibecoded with Claude and was originally a personal project. please don't hate me :3**
