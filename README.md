![Subreddit subscribers](https://img.shields.io/reddit/subreddit-subscribers/Ghostrunner?style=for-the-badge) 
![Discord](https://img.shields.io/discord/707647729043636276?color=%237289da&label=Join%20the%20discord%21&style=for-the-badge)

---

- [Frequently asked questions](#frequently-asked-questions)
  - [How do I use the new always available "Instant restart"?](#how-do-i-use-the-new-always-available-instant-restart)
  - [Where are my saves/configs located?](#where-are-my-savesconfigs-located)
    - [Save files](#save-files)
    - [Configs](#configs)
  - [How do I show the Speedometer and death counter in LiveSplit?](#how-do-i-show-the-speedometer-and-death-counter-in-livesplit)
  - [How do I choose which DirectX version to use?](#how-do-i-choose-which-directx-version-to-use)
  - [How to set DirectX 12 by default?](#how-to-set-directx-12-by-default)
  - [Should I use DirectX 11 or 12?](#should-i-use-directx-11-or-12)
  - [How do I downpatch the game?](#how-do-i-downpatch-the-game)
- [Technical issues](#technical-issues)
  - [Troubleshooting](#troubleshooting)
  - [My graphics/keybindings are resetting](#my-graphicskeybindings-are-resetting)
  - [Nothing disables V-sync](#nothing-disables-v-sync)
  - [Input lag and/or broken V-sync](#input-lag-andor-broken-v-sync)
  - [Ray tracing is disabling itself](#ray-tracing-is-disabling-itself)
  - [Stability survey and results](#stability-survey-and-results)
- [General improvements](#general-improvements)
  - [NVIDIA Reflex](#nvidia-reflex)
    - [What is NVIDIA Reflex?](#what-is-nvidia-reflex)
    - [What NVIDIA reflex is NOT?](#what-nvidia-reflex-is-not)
    - [How to enable NVIDIA Reflex for Ghostrunner](#how-to-enable-nvidia-reflex-for-ghostrunner)
  - [AMD improvements](#amd-improvements)
- [Speedrunning resources](#speedrunning-resources)
- [Useful links](#useful-links)
- [Credits](#credits)


# Frequently asked questions

## How do I use the new always available "Instant restart"?
In settings, ensure the option "Instant restart" is set to "On". If you wish to rebind the key, it's the same entry as for Quick restart on death, there is no new entry for this functionality.

## Where are my saves/configs located?
### Save files
- Windows  
`%LOCALAPPDATA%\Ghostrunner\Saved\`

- Steam Play (Linux)  
  `<steamfolder>/steamapps/compatdata/1139900/pfx/drive_c/users/steamuser/Local Settings/Application Data/Ghosteamuser/Local Settings/Application Data/Ghostrunner/Saved/SaveGames`

### Configs
- Windows  
`%LOCALAPPDATA%\Ghostrunner\Saved\Config\WindowsNoEditor\`
- Steam Play (Linux)
`<steamfolder>/steamapps/compatdata/1139900/pfx/drive_c/users/steamuser/Local Settings/Application Data/Ghosteamuser/Local Settings/Application Data/Ghostrunner/Saved/Config/WindowsNoEditor/`

## How do I show the Speedometer and death counter in LiveSplit?
You can activate it by:
1. Right clicking LiveSplit then
2. Edit Splits
3. Activate (If you haven't already)
4. Settings
5. Tick off whichever options you'd like.

## How do I choose which DirectX version to use?
By default, Ghostrunner launches in DirectX 11. To choose which DirectX version to use, launch the game via the Steam application and choose the version you want it to launch.

## How to set DirectX 12 by default?
Open the Steam application, go to Library, right click Ghostrunner, click on Properties, and add `-dx12` in the Steam launch options.

## Should I use DirectX 11 or 12?
DirectX 11 is generally better used for stability. DirectX 12 is better if you want ray tracing, you have an RTX card or DirectX 11 is causing issues.

## How do I downpatch the game?
If you want to play on earlier version, for example for a specific speedrun, or you just want multiple versions of the game, here is a [guide on downpatching.](Downpatching.md)

# Technical issues

## Troubleshooting
For troubleshooting crashes make sure to take a look at the [Troubleshooting page](Troubleshooting.md).
## My graphics/keybindings are resetting
Go to `%LOCALAPPDATA%\Ghostrunner\Saved\Config\WindowsNoEditor`. Set the things you want, then right click each file, go to Properties and set as read-only.

## Nothing disables V-sync
To fix this, do the following:

1. Go to `%LOCALAPPDATA%/Ghostrunner/Saved/Config/WindowsNoEditor` 
2. Open and add to Engine.ini
3. In [ConsoleVariables] section change r.VSync=1 to r.VSync=0

<sub><sup>Credit to LongerWarrior for this.</sup></sub>

## Input lag and/or broken V-sync
- Disable in-game V-sync. In-game V-sync tends to be subpar. NVIDIA and AMD for the most part implement it better.
- Disable Windows 10 [Game Mode](https://www.xsplit.com/support/useful-tools/windows-game-mode) and [Xbox Game Bar](https://www.windowscentral.com/how-disable-and-remove-game-bar-windows-10-creators-update).
- Try this [fix](Blurryfix.md).

## Ray tracing is disabling itself
This is a common bug. Reasons and solutions are currently unknown.

## Stability survey and results
There is a Ghostrunner stability survey handled by Henry, you can read more about it [here](Survey.md).

# General improvements

## NVIDIA Reflex

### What is NVIDIA Reflex?
In layman's terms NVIDIA Reflex decreases the time taken for a frame to be rendered and sent to your display, which helps decrease latency. The benefit of it is varied, there are tons of variables that go into how well it will work, but worst case scenario as far as we know is that it won't do anything, so there is no disadvantages to keeping it enabled (apart from perhaps power consumption but that's negligible). 

### What NVIDIA reflex is NOT?
NVIDIA Reflex will NOT directly increase your FPS. While it can technically happen, it would be an indirect result of reducing the GPU load which would reduce thermal throttling and give you higher FPS, but because Reflex acts also as a frame limiter, it will prevent the framerate from raising too high which would bring the temperatures back up.

NVIDIA Reflex is not a universal tool that works for all applications. It's up to the game developer to implement this in code, google to find an availability list (Obviously for Ghostrunner it's available).

### How to enable NVIDIA Reflex for Ghostrunner
1. Update your graphics drivers to latest version (**You should always keep your GPU drivers up-to-date regardless!**)
2. Enable "Ultra Low Latency" mode:
	1. Open NVIDIA Control Panel (Right click on your desktop and the option is there)
	2. Click the "Manage 3D settings" tab on the left
	3. Scroll down until you see "Low Latency Mode" and set it to Ultra
	4. Hit apply
3. Start Ghostrunner and go to Settings > Video
4. Scroll all the way down and in the dropdown pick "Enabled + Boost" (In temperature constrained scenarios it might be beneficial to not enable Boost, test for yourself)

## AMD improvements
There are a couple settings that can help on AMD cards (no guarantees). In Radeon Adrenalin software enable Radeon Anti-lag or Enchanced Sync. Disable waiting for vertical refresh rate if unwanted.

# Speedrunning resources
- [Speedrun.com page](https://www.speedrun.com/ghostrunner)
- [Speedrunning resources](https://www.speedrun.com/ghostrunner/resources)
- [Ghostrunning - the speedrunning discord](https://discord.gg/eZRz3Q5)
- [New Ghostrunners - Beginner's Guide](https://docs.google.com/spreadsheets/d/1jWBOuxSY-zlBgzhkYnsVYtNJFscbObve67g9Xy_biV0/edit)
- [Inbounds speedtech doc](https://docs.google.com/spreadsheets/d/1RVfpfNUJEUBfPfs1Ch-7rmXD_IFO37Iyw50tFEgnEbY/edit)
- [Out of Bounds speedtech doc](https://docs.google.com/spreadsheets/d/1r6YV0NYDE0wTVllcY1qSab4n7Z-VYIdu4Z3DuqsDE48)
- [Glossary of terms]([Glossary.md](https://docs.google.com/spreadsheets/d/1jWBOuxSY-zlBgzhkYnsVYtNJFscbObve67g9Xy_biV0/edit#gid=14803918))

# Useful links
- [LiveSplit](https://livesplit.org/)
- Micrologist's [trainer](https://github.com/Micrologist/GhostrunnerTrainer/releases)
- Dmgvol's [save unlocker](https://github.com/Dmgvol/GRUnlocker)
- [PCGamingWiki entry](https://www.pcgamingwiki.com/wiki/Ghostrunner)
- [Ghostrunner subreddit](https://www.reddit.com/r/ghostrunner)

# Credits
- [One More Level](https://www.omlgames.com/en/home/) and [Slipgate Ironworks](https://en.wikipedia.org/wiki/Slipgate_Ironworks) for developing the game
- [TheEvilSkeleton](https://github.com/TheEvilSkeleton) for help with the README
- [Dmgvol](https://github.com/Dmgvol) for downpatching guide and GRUnlocker.
- [Micrologist](https://github.com/Micrologist) for the trainer.
- LongerWarrior for Vsync fix

---
 <p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/Kellegram/Ghostrunner_faq">Ghostrunning FAQ</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/Kellegram">Kellegram</a> is licensed under <a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"></a></p>
