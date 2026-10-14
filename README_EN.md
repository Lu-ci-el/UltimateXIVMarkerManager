# UltimateXIVMarkerManager (UXMM)

**A Windows app for organizing, editing and saving FFXIV field markers while viewing the arena floor.**

**0.1.0.5** (update 105) · Windows x64 · No Dalamud required

[日本語](README.md) · [Download the app](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/download/v0.1.0.5/UltimateXIVMarkerManager_0.1.0.5.zip) · [Release notes](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/tag/v0.1.0.5) · [Illustrated English guide](docs/USER_GUIDE_EN.md)

![Marker presets and arena preview — Japanese UI sample with fictional data](docs/images/02-overview.png)

The illustration is an existing 0.0.9.1 Japanese UI sample using fictional data and illustrative floor artwork. The app includes English UI: open Settings (設定) and select English.

## Get started

1. Download the application ZIP and extract the entire folder to a writable location.
2. Run `UltimateXIVMarkerManager.exe`. Install [.NET 10 Desktop Runtime x64](https://dotnet.microsoft.com/en-us/download/dotnet/10.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) if needed.
3. Check the selected `ffxiv_dx11.exe` and adjacent `sqpack`. A valid saved selection is preferred; otherwise the standard installation location is checked. Use **Select EXE** for a different installation.
4. Check the character's `UISAVE.DAT`. The standard Documents location is checked, and a unique candidate can be selected automatically. With multiple characters or a custom location, use **Select UISAVE**.
5. Edit a preset, apply it to the draft, exit FFXIV, then use **Save** in the marker panel. Review the selected slots and differences before writing.

Saving to Library or an independent map is separate from writing marker slots to the game's UISAVE.

## Included in this release

- English user guide in the signed app ZIP (`README_EN.txt`), plus the illustrated online guide.
- Recent UISAVE history entries can be removed without deleting the files or current draft.
- Default EXE/UISAVE discovery while preserving valid saved choices and explicit EXE deselection.
- Arena-floor fixes, field selection and separated help/loading text. Multiple backgrounds use **Field 1, Field 2, …**; these are not live phase detection.
- Abyssos Fifth Circle (Savage): initial metal floor and rock floor are separate fields. Other recent arena fixes are retained from 0.1.0.2.

0.1.0.5 restores the visible edges of the lower floor in Cruiserweight M3. Image regression checks cover 31 floor, height and field combinations; the other 30 images remain unchanged. Passing checks are now required before distributing a release ZIP. Marker coordinates are preserved. Version components are decimal digits of the update count: 0.0.9.9 is followed by 0.1.0.0.

## Features and scope

| Feature | Available operations |
| --- | --- |
| Marker presets | Position editing, slot rearrangement, comparison/Merge, Focus editing and selected-slot saving |
| Backup / restore | Backup before saving and marker-slot restoration |
| Library | Saved layouts, folders, tags, notes, favorites and Pack import |
| Maps | Field map or top-down arena, initial/placement location, field and height selection, zoom, pan and grid |
| Map cache | Generated images stored beside the EXE and reused when compatible |
| Game Strategy Board | View saved/shared lists; external export/import; folder insertion/deletion; add selected shared/external boards to the saved list |
| Independent maps | Edit custom UXMM diagrams and share selected maps with Map PACK |

Game saved/shared board layouts are view-only in UXMM. Custom UXMM diagrams have separate editing tools; they do not generate new FFXIV shared codes. Arena lighting, glow, VFX and animated mechanics are not fully reproduced. Content-wide floor accuracy and compatibility after game updates still require checking.

The signed build, package contents and checksum are checked for this release. A successful build does not establish current in-game compatibility.

## Documentation and files

- [Illustrated English guide](docs/USER_GUIDE_EN.md)
- [Japanese guide with current-version notes](docs/USER_GUIDE.md)
- [Archived Japanese PDF for 0.0.9.1](docs/UltimateXIVMarkerManager_Manual_0.0.9.1.pdf)

`.mmp` stores a Map PACK, `.mms` a Strategy saved list/folder, and `.mmsh` a shared list. Compatible legacy `.uxmm` imports are retained. Changing an extension does not convert a file.

## Distribution

The application is attached to GitHub Releases. This repository contains documentation and distribution information; **the application's development source is private**. GitHub's automatic “Source code” ZIP/tar.gz contains this documentation repository.

Keep all signed distribution files together. Personal data stays beside the EXE, including `Marker`, `settings`, `MAP` and WebView2 data in `runtimes/W2`. Close UXMM and back up your existing folder before updating; preserve those data folders.

For a bug report, include the version, duty, selected field/height, steps and error text. Hide personal paths and character details; do not post UISAVE files or your personal application folder.
