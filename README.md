# FTLPad

Controller support for **FTL: Faster Than Light** (Steam, version 1.6.14), built into the game: focus brackets, a button-prompt bar that follows what you're on, Xbox glyphs on the HUD, a command wheel and a controls card. Works with any XInput pad, including handheld built-in controllers (MSI Claw, ROG Ally, Legion Go).

## Install

1. Download [FTLPad.zip](https://github.com/talama191/FTLPad/releases/latest/download/FTLPad.zip) (always the latest release) and unzip it.
2. Double-click **Install FTLPad.cmd**. It finds FTL through Steam (or asks for the folder).
3. Start FTL from Steam. The controls card shows on the first launch.

**Uninstall FTLPad.cmd** removes it. The installer adds three files next to `FTLGame.exe` and changes nothing of the game:

| File | What it is |
|---|---|
| `dbghelp.dll` | Starts FTLPad when FTL loads, and passes every call through to Windows' own dbghelp |
| `dbghelp_sys.dll` | A copy of your PC's own 32-bit `dbghelp.dll` |
| `FTLPad.InGame.dll` | FTLPad itself |

On a handheld, keep the built-in controller in gamepad (XInput) mode, not desktop/mouse mode.

## What the pad does

- **Ship:** the D-pad walks room to room, crew, systems, weapons and drones; LB/RB change area. A clicks (power up a system, arm a weapon), B right-clicks (send crew, power down, cancel). RT + A/B/X/Y arms weapons 1-4, RT + D-pad fires drones and the battery.
- **Events and menus:** the first choice is focused when they open; confirm dialogs default to the safe answer.
- **Beacon map:** the D-pad goes beacon to beacon at any angle, LB/RB step through the beacons in jump range, Y opens NEXT SECTOR. The cursor starts on your own beacon, never on a jump.
- **Sector map:** pick a ringed sector with LB/RB or the D-pad, A to go, B to close.
- **Ship screen:** LB/RB switch Upgrades / Crew / Cargo; A upgrades, X takes a level back.
- **Hangar:** every control on the D-pad, LB/RB flip ships; it never defaults to START.
- **Command wheel** (hold View): upgrades, crew, cargo, store, stations, autofire, abilities, options, controls.

Full control list: `README.txt` in the zip.

## Notes

- The DLLs are not code-signed. On a fresh Windows 11 with Smart App Control on, Windows may block them; FTL still runs, just without the prompts.
- Works at any screen size: it reads FTL's own 1280x720 picture before FTL stretches it to your screen.
- Settings: `%APPDATA%\FTLPad\config.json`. Log: `%APPDATA%\FTLPad\ftlpad.log`. Turn it off without uninstalling: create an empty file `%APPDATA%\FTLPad\disabled`.
- Not affiliated with Subset Games.
