# UltimateXIVMarkerManager 0.1.0.6 — English User Guide

Organize, edit and save FFXIV field marker presets on Windows while viewing
the arena floor. Dalamud is not required. The default interface is Japanese;
open Settings (設定) and choose English in the language selector.

Downloads: https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/latest
Illustrated English guide:
https://github.com/Lu-ci-el/UltimateXIVMarkerManager/blob/main/docs/USER_GUIDE_EN.md
Japanese guide:
https://github.com/Lu-ci-el/UltimateXIVMarkerManager/blob/main/docs/USER_GUIDE.md

[日本語ガイド](USER_GUIDE.md) · [Download the app](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/latest)

The illustrations below are the existing 0.0.9.1 Japanese UI samples with fictional paths, layouts and diagrams. They illustrate the workflow; newer field and history controls are described in the text. They are not screenshots proving current game compatibility.

## 1. Install And Start

Requirements: Windows x64, .NET 10 Desktop Runtime x64, WebView2 Runtime,
and a local FFXIV installation containing ffxiv_dx11.exe and its adjacent sqpack.

.NET Desktop Runtime: https://dotnet.microsoft.com/en-us/download/dotnet/10.0
WebView2: https://developer.microsoft.com/en-us/microsoft-edge/webview2/

Extract the whole application ZIP into a writable folder. Open the enclosed
UltimateXIVMarkerManager folder and run UltimateXIVMarkerManager.exe. Keep the
EXE, DLLs, runtimes folder and release.manifest.json / release.manifest.sig
together. The app verifies its signed distribution files. This is the app's
own integrity signature; it is not a Windows Authenticode signature.

## 2. Select The Game And Character

![Select the game executable and character save. Japanese UI sample.](images/01-startup.png)

Select the game executable and character save. Japanese UI sample.

A valid saved selection is used first. Otherwise, the app checks the standard
installation location:
C:\Program Files (x86)\SquareEnix\FINAL FANTASY XIV - A Realm Reborn\game

It selects ffxiv_dx11.exe only when the required adjacent game data is present.
If your installation is elsewhere, use Select EXE. Game files are read to obtain
map names, arena textures and board materials and to analyze save structures.
Selecting the EXE does not launch the game. Explicitly clearing the EXE selection
is remembered; use Select EXE to choose it again.

UISAVE.DAT is normally under your Windows Documents folder:
My Games\FINAL FANTASY XIV - A Realm Reborn\FFXIV_CHR...\UISAVE.DAT

The app checks the standard Documents location and uses a unique candidate.
When there are multiple character files, or none can be found, use Select UISAVE
to choose the intended character manually. Check the loaded duties, presets and
save dates before editing. Valid saved paths take precedence over defaults.
If Documents has moved, use its actual location.

Recent UISAVE files lets you reopen a previous file. Select an entry and use
Remove from history to remove that entry only. This does not delete the actual
UISAVE file, the current draft or the selected path.

## 3. Edit And Save Field Markers

![Position editing: select a marker and adjust its coordinates. Japanese UI sample.](images/04-edit.png)

Position editing: select a marker and adjust its coordinates. Japanese UI sample.

Select a preset slot, then Edit positions. Drag a marker or enter its horizontal
position (X), vertical map position (Z) and height (Y). Use undo/redo as needed.
Apply the changes to the working preset. This updates the draft, not UISAVE.

To write the changes to the game:
1. Exit FFXIV.
2. Choose Save in the marker preset panel.
3. Review the changed slots and individual marker differences. Deselect slots
   you do not want to save.
4. Save the selected slots and wait for the success result.
5. Start FFXIV and check the target character's marker presets.

The app checks the target file again and makes a backup before writing. Saving
and restoring UISAVE are blocked while FFXIV is running. If the game or another
program changed the file, reload it and review the differences before saving.

Dragging preset cards rearranges slots. Emptying a slot, applying a Library
preset, Focus edits and comparison/Merge also modify the draft first. Saving a
Library item or an independent map does not write it to the game's marker slots.

## 4. Focus Editing, Comparison And Library

![Library layouts and destination preset slots. Japanese UI sample.](images/06-library.png)

Library layouts and destination preset slots. Japanese UI sample.

Focus editing offers selection of ALL / ABCD / 1234 or individual markers, with
movement, rotation, spacing and other layout tools. Review the result, leave
Focus editing and use the normal Save workflow to write the chosen slots.
Comparison/Merge shows differences between presets and applies your selections
to the draft.

Save to Library stores a layout on your PC. Use names, folders, tags, notes and
favorites to organize layouts. In preset creation, select or drag a Library
layout into the intended game slot, review it and save through the marker panel.
Layout names are for organization in UXMM; they do not rename game content.

## 5. Maps, Fields And Heights

![Map controls above the arena preview. Japanese UI sample.](images/03-map.png)

Map controls above the arena preview. Japanese UI sample.

Field Map shows the normal map image. Real Battle Map draws a top-down arena
from local game geometry and textures. None hides the background.

Initial and Placement location choose which background location to display.
Where available, Field 1, Field 2 and subsequent buttons select different arena
backgrounds. These are field choices, not automatic detection of the current
battle phase. Changing the field or displayed height does not alter saved XYZ.

For markers at different heights, select the appropriate upper/lower floor.
Markers on a different height may appear gray with an arrow and height value.
For Abyssos: The Fifth Circle (Savage), the initial metal floor is Field 1 and
the rock floor is Field 2. Stored marker height does not replace the initial
field selection.

Use the grid and its color controls to align layouts. The mouse wheel changes
zoom in 10% steps; you can also enter a percentage. Dragging the background pans
the display without changing saved coordinates. Reset map position recenters the
view while keeping zoom. Use Edit positions when you intend to move a marker.

Generated maps are cached in the MAP folder beside the EXE. Matching cached
images are reused. A renderer update may regenerate an image on its next use.
If loading fails, read the error and use the reload control to retry.

Arena extraction is still being checked across content. Lighting, glow, VFX,
animated mechanics and all in-game material effects are not fully reproduced.
An offline floor image may differ in color or appearance from the live game.

## 6. Strategy Board And Independent Maps

![Saved Strategy Board folders and board viewer. Japanese UI sample.](images/08-strategy.png)

Saved Strategy Board folders and board viewer. Japanese UI sample.

Strategy Board can display the game's saved and shared boards. Open or collapse
folders, export a list or folder, and open supported external files. Inserting
or deleting a saved folder, or adding selected shared/external boards to the
saved list, changes UISAVE: exit FFXIV and review the confirmation first.

The layouts in the game's saved/shared lists are view-only in UXMM. UXMM's
independent maps and custom diagrams have separate editing tools for objects,
positions, size, rotation, layers, visibility and locking. Saving an independent
map saves it in UXMM, not into the game's Strategy Board.

Existing FFXIV shared codes support limited editing of existing objects in the
strategy editor. This does not support adding, deleting or changing object types.
Creating a custom UXMM diagram does not generate a new FFXIV shared code.
Board coordinates are not automatically converted to world marker coordinates.

External files:
- .mmp: a Map PACK containing selected independent maps.
- .mms: a Strategy saved list or saved folder.
- .mmsh: a Strategy shared list.
- Compatible legacy .uxmm files remain readable through their matching import.

Renaming an extension does not convert a file. Review names, notes and the public
author name before sharing a PACK.

## 7. Backup, Restore And Update

Backup creates a copy of the current UISAVE. Restore lets you select a saved
marker state for the current file. Normal marker restoration changes only the
marker slots; it does not roll back other game settings or Strategy Boards.
Exit FFXIV before restoring and review the chosen state.

App data is stored beside the EXE:
- Marker\Backup: backups and marker save history.
- Marker\Library: your saved layouts.
- Marker\Workspace: working data and drafts.
- settings\Authority: local settings/analysis data.
- MAP: generated map cache.
- runtimes: application dependencies and WebView2 data under W2.

Before updating, close UXMM and keep a copy of your current app folder. Extract
the new distribution into the same layout while preserving your personal data
folders. Keep all files from the new signed distribution together. Recheck the
EXE and UISAVE selections after starting the new version.

## 8. Troubleshooting

Cannot start: confirm .NET 10 Desktop Runtime x64 and WebView2 are installed and
that the whole ZIP was extracted. Do not run only the EXE from inside the ZIP.
Cannot select UISAVE: select a valid game EXE and adjacent sqpack first.
Cannot save: exit FFXIV and read the displayed reason, including whether there
are changes or the target file has changed since loading.
Changes missing in game: check the character's UISAVE and confirm that you saved
the marker slots after applying the draft.
Wrong or clipped map: check Initial / Placement location, Field, height, zoom and
pan. Report the duty name and selected background if the floor is still wrong.
Cannot edit a game board: the saved/shared list viewer is separate from the
independent custom-diagram editor.

For a bug report, include the application version, duty, selected field/height,
steps and exact error text. Hide personal paths and character information in
screenshots. Do not post UISAVE files, backups or your entire personal app folder.

## 9. This Release

0.1.0.6 uses native horizontal floor surfaces supporting the marker area to
improve framing at 100% zoom. Matching platform assemblies and aspect ratio
are retained. Ambiguous scenes keep their previous framing; detection is
not guaranteed for every arena. Marker coordinates stay unchanged.

31 native floor, height and field views passed regression checks: 15 improved
frames and 16 identical fallback images. Three headless UI cases passed 234
checks including 100% framing and marker pixel alignment. The signed build
and packages were verified. WPF and the game were not run.
The version represents update count 106, with decimal carry in each component.

This repository distributes the application and user documentation. The
application's development source is private. GitHub's automatically generated
Source code ZIP/tar.gz contains the public documentation repository, not the
application development source.
