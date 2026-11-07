<p align="center"><img src="docs/cover.jpg" alt="Illustration of a game main menu panel with three buttons, a mute toggle and a quit button, with an arrow leading to a 2D platformer scene" width="100%"></p>

# Unity Main Menu UI

A small Unity script that handles the buttons of a game's main menu and in-game menu.

## What it does

`MainMenuController` gives you public methods to wire to UI buttons: start the game, quit, mute or unmute all audio, restart the level, and go back to the main menu.

It was written for the same 2D platformer as [unity-2d-player-controller](https://github.com/MemeGamer/unity-2d-player-controller) and [unity-2d-bird-adventure](https://github.com/MemeGamer/unity-2d-bird-adventure); all three were uploaded together.

## How it works

| Method | What it does |
| --- | --- |
| `PlayGame()` | Loads the scene named `SampleScene` |
| `EndGame()` | Calls `Application.Quit()` (no effect in the Editor) |
| `Mute()` | Toggles `AudioListener.pause`, which pauses or resumes all audio |
| `GameRestart()` | Waits 1 real second, then reloads `SampleScene` (works while `Time.timeScale` is 0) |
| `Mymenu()` | Loads the scene named `Main menu` |

## Tech

- Unity UGUI buttons and `SceneManager`, C#.
- The repository has no `ProjectSettings`, so the exact Unity version is not recorded.

## Use it

1. Copy `MainMenuController.cs` into `Assets/`.
2. Add it to any GameObject in your menu scene (an empty `MenuController` object works).
3. On each `Button`, add an `On Click ()` entry, drag in that GameObject and pick the method, for example `MainMenuController.PlayGame`.
4. Add both scenes, `Main menu` and `SampleScene`, to File > Build Settings, or change the scene names in the script to match yours.

## Scripts

| Script | Purpose |
| --- | --- |
| `MainMenuController.cs` | Play, quit, mute, restart and back-to-menu button handlers |

## Notes

- This repository contains a single script: no scenes, canvas or button prefabs.
- Scene names are hard-coded strings and must match the scene files exactly, including the space in `Main menu`.
