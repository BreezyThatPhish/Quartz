---
description: Information about how to use my twitch chat integration mod for Ultrakill by Flazhik
comments: "false"
---
---

A mod kindly made for me by [Flazhik](https://github.com/Flazhik), it allows various Ultrakill related channel points on my twitch stream to go right through and effect the game directly and instantly. Loadout changes, PSX Graphic settings, hitstop modification, etc. 
Its a hilarious mod that allows for a great amount of viewer agency and its been a great boon to have, however its syntax is a little precise. So this page is dedicated entirely to explaining how to use it. 

# General Prompt Syntax

All of these go through point redeems, and all those that require a text input follow universal syntax. 
```
paramater_name:value
```
Everything is case insensitive, and the amount of whitespace (number of spaces) doesnt matter.
The content of the message itself besides the prompt:syntax input doesnt matter, provided it has that sequence in it. 
For example:
>[!quote]+ Example Prompt 
>hitstop: 2.5

and:
>[!quote]+ Example Prompt
>This game is far too fast, I think to slow it down you ought to set hitstop: 2.5

are parsed the exact same, because all that matters is the "hitstop: 2.5". 

All text prompts are treated like this. 

<br>

# Boss Spawns 

The simplest redeem, requires no text input from the viewer. It simply activates cheats and enables boss spawns. a cybergrind-related option, for a set duration of time. 

<br>

# Hitstop 

This one has a single mandatory parameter: hitstop.
The value can be anything between 0 and 3, and will set my truestop and hitstop multiplier to the value via [daemonweaponutils](https://thunderstore.io/c/ultrakill/p/daemon47/DaemonWeaponUtils/); truestop is the full pause that happens during parries and hitstop is the slowdown on strong / multihit attacks.  
>[!quote]+ Example Prompt 
>I hit my head the other day, and ever since then my reaction time has been awful. Here, have hitstop: 2 so I can actually process what's going on

<br>

# PSX Graphics 

This has four parameters that are all optional, you can do as many or as few as you like. These are: 
1. **Downscaling** 
	The resolution of the game, values include:
	**720, 480, 360, 240, 144** 
2. **Dithering** 
	A method of colour rendering, wherein existing colours are combined in a pattern to create a new one. Typically used in situations where, due to hardware constraints, the colour in question cannot be directly rendered. ULTRAKILL dithering emulates this restraint, higher values making it more intense / limited. Values can range from: 
	**0-500**
3. **Vwarping** 
	Vertex warping is where polygons snap to pre-existing points due to hardware constraints in their coordinate calculations, causing models to look wobbly. The higher the value, the more intense this wobbling is. Values can range from:
	**0-5** 
4. **Twarping**
	Texture warping is the same as vertex warping but instead of model polygons its textures, higher values increase this effect. Values can range from:
	**0-100**
>[!quote]+ Prompt Example 
>Dont suppose you need glasses do you? Downscaling : 480. 480p is the way to go, that's what I've been told by my ISP. dithering: 500 because I feel like it. I don't really feel like texture warping does that much, so have twarping : 50 just for the sake of it. Oh, and of course, have fun with vwarping: 4 lmao

<br>

# Change Loadout 

The most complicated one. Each weapon is its own parameter and has multiple aliases it can go by, and some have multiple values they can be set to. 

**Weapon Parameters**
- Revolver: rev, revolver 
- Shotgun: s, shotgun, shot, sho
- Nailgun: n, nail, nails, nailgun, nai
- Railcannon: rail, rails, railcannon, raligun, rai
- Rocket Launcher: rocket, rockets, rock, rocketlauncher, rl

**Arm Parameters**
- Feedbacker: feedbacker, fb, bluearm
- Knuckleblaster: knuckleblaster, kb, redarm
- Whiplash: whiplash, wl, hook, greenarm 

**Value Options**
Every weapon related value must involve three letters, one for each variant per weapon. There are four options for what any given letter can be:
- D: Default Variant 
- A: Alternate Variant 
- E: Equip
- U: Unequip
Weapons that dont have an alternate variant (railcannon and rocket launcher), "Alternate" will just select the default variant. 

Arm related values only require one letter, and will handle anything besides "U" (unquip) as an equip option. 

>[!quote]+ Example Prompt 
> Have fun navigating arena now! rockets:UDD, lmao!
>*Unequips a blue rocket launcher*

>[!quote]+ Example Prompt 
>fb:U go ahead, try and parry this shit now
> *Unequips feedbacker*

>[!quote]+ Example Prompt 
> rev: AAA shot: AAA nail: AAA rails:AAA rocketlauncher:AAA
>*Enables alts for all weapons; equips all the railcannon and rocketlauncher variants*

