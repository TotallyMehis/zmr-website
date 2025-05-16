---
title: 'Beta 7'
description: New weapons, new models and so much more!
date: 2025-03-02
image: /assets/bg002.jpg
---

## Beta 7

It's here. It has been... a while.

## Steam when?

People have been asking about the Steam release since the very beginning. Now that we're here - after 4 years since the last update - I guess it's a good time to shed some light on the topic.

For a long time, the standards for *Source mods on Steam* have been very high. The classic example is Black Mesa; a dedicated group of semi-professional people coming together to build a cohesive game. ZMR has been very much the opposite of this. I would describe our development process as anarchism; people contribute what they can and want, and whenever they feel like it.
The lack of structure can very much be blamed on me. I'm just not interested in managing a whole project and its community. Even writing these release notes is a pain in the ass, lol.

I mention this because the original vision for ZMR was a big Steam release with remade assets. While we have progressed a lot and the standards have... changed, a Steam release is just very unlikely to happen. Life gets in the way and there is still so much to do. For example, we are still using the original ZM 1.2.1 zombie sounds made by *somebody*. Releasing the mod on Steam without permissions for all assets just feels shitty.

There is also the fact that a Steam release is not a magical bullet. People tend to view a Steam release as this magical moment when suddenly there is a giant surge of new players and The Good Old Times(TM) are back. That's just not the reality. Games like Brain Bread 2 and Zombie Panic: Source see daily players in the 10-40 range.

That being said, if you are waiting for a Steam release to play ZMR, you are going to be disappointed. I would like to point out that installing a Source mod is very easy. Nothing is stopping you from downloading the mod and joining our sunday sessions. We have been playing ZM in one form or another for 10 years or so every other sunday. Even if this game is only played by 16 players for a few hours every other week, I feel content.

\- Mehis

## Changelog

### Notable

- The game is now 64-bit only.
- New weapons:
    * Snubnose revolver
    * Glock
    * 9mm AR
    * Pipebomb
    * Baseball bat
- New weapon models & animations.
- Added radial fog.
- Added bicubic filtering on lightmaps.
- Added VScript support.

### General

- Added 2D skybox rendering when moving outside the world. Being a ZM is a lot less jarring this way.
- Added `zm_cl_lefthanded` cvar to control viewmodel handedness.
- Drastically improved ZM vision performance.
- Replaced older Discord rich presence support with Discord Game SDK.
- Security & stability fixes.
- Added ZMR weapon autocompletion to `give` command.
- Made viewmodel bobbing less pronounced.
- Increased max players to 101. 16 players is still the default and recommended maximum player count.
- Added `zm_movetosurvivor` command, which ZM & spectators can use to teleport to a survivor. 
- Fixed infinite reload if reload time was misconfigured in the weapon config.
- Fixed weird zombie behavior with higher tick rates.
- Fixed zombie spawning causing water reflections to break.
- Fixed `env_laser` & `func_tank` related crashes (zm_deep_b5).
- Fixed transient areas not getting unblocked.
- Fixed `zm_sv_debug_nav_transient_nofloor` not working if `zm_sv_debug_nav_transient` wasn't on.
- Fixed scoreboard "importance" image tooltip not working / flickering.
- Fixed being able to walk through props with collision attached to bones.
- Fixed `info_loadout` distributing revolvers while it was set to give out pistols.
- Fixed zombie population count becoming invalid when changing cvars in between spawning and deleting.

### Balance

- Deleting a zombie returns half of its cost to the ZM.
- Zombies predict survivors' movement trajectory.
    * This was a long time coming. Should make it harder to run past zombies.
- You can no longer hold pipebomb / molotov indefinitely after arming, it will blow up in your hands.
- Decreased survivor movement acceleration.
    * You can't change your movement direction in an instant anymore. We're not Quake, ya know. You might need to be a bit more careful with your movement around zombies, that's about it.
    * `sv_accelerate` 10 -> 8.5
    * `sv_stopspeed` 100 -> 80
- Sniper rifle spawn chance in the world was reduced to 30%. `info_loadout` will still distribute them 50/50.
- Lighting a molotov is no longer random and dependant on your health.
    * It stuck around from the original mod, but it's honestly just annoying and more work for the animator for little return.

### Mapping

- New entities:
    * `logic_eventlistener`
    * `skybox_swapper`
    * `weapon_zm_snubnose`
    * `weapon_zm_ar9mm`
    * `weapon_zm_glock`
    * `weapon_zm_pipebomb`
    * `weapon_zm_baseballbat`
- Fixed `npc_enemyfinder` not working without AI graph.
- Added `viewmodel_armversion` option to weapon configs. If 0 or not set, the weapon will default to legacy citizen arms. If you want to use the newer arms, you'll have to re-rig your models and set the value to 1.
