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

On a handheld, keep the built-in controller in gamepad (XInput) mode, not desktop/mouse mode, and leave Steam Input's mouse emulation off for FTL (FTLPad warns if something else moves the mouse).

## What the pad does

FTLPad reads FTL itself (read-only): which screen or popup is open, every button with its click area and name, event choices, rooms, crew and beacons come from the game's own objects, so nothing is guessed from the picture. If this FTL doesn't match (another version, a mod), it reads the picture instead.

- **Crew:** Y selects the next crew member and puts the cursor on them, by name.
- **Ship:** A does (select, send selected crew, power up, fire), B undoes (cancel aiming, deselect, power down). LB/RB walk the weapon and drone row and only pick a slot: A arms the weapon (the cursor then goes to the enemy, A fires and it comes back) or deploys the drone. Hold RT for abilities (cloak, battery, hacking, teleport...). The D-pad crosses from area to area. No button combinations.
- **Events and menus:** the first choice is focused when they open; an event only takes its choices (FTL locks the ship until you choose); confirm dialogs default to the safe answer.
- **Beacon map:** the D-pad goes beacon to beacon at any angle, LB/RB step through the beacons in jump range, Y opens NEXT SECTOR. The cursor starts on your own beacon, never on a jump.
- **Sector map:** pick a ringed sector with LB/RB or the D-pad, A to go, B to close.
- **Ship screen:** LB/RB switch Upgrades / Crew / Cargo; A upgrades, X takes a level back.
- **Hangar:** every control on the D-pad, LB/RB flip ships; it never defaults to START.
- **Command wheel** (hold View): upgrades, crew, cargo, store, stations, autofire, abilities, options, controls.

Full control list: `README.txt` in the zip.

## Notes

- The DLLs are not code-signed. On a fresh Windows 11 with Smart App Control on, Windows may block them; FTL still runs, just without the prompts.
- Works at any screen size and display mode: it reads FTL's own 1280x720 picture before FTL scales it, and places the cursor with the same window-to-game mapping FTL applies to a real mouse (read from the game, not guessed from the resolution).
- Settings: `%APPDATA%\FTLPad\config.json`. Log: `%APPDATA%\FTLPad\ftlpad.log`. Turn it off without uninstalling: create an empty file `%APPDATA%\FTLPad\disabled`.
- Not affiliated with Subset Games.
