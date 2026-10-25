# UltimateXIVMarkerManager (UXMM)

**A Windows app for organizing, editing and saving FFXIV field markers while viewing the arena floor.**

**0.1.1.1** (update 111) · Windows x64 · No Dalamud required

[日本語](README.md) · [Download the app](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/download/v0.1.1.1/UltimateXIVMarkerManager_0.1.1.1.zip) · [Release notes](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/releases/tag/v0.1.1.1) · [Illustrated English guide](docs/USER_GUIDE_EN.md)

![Marker presets and arena preview — Japanese UI sample with fictional data](docs/images/02-overview.png)

The illustration is an existing 0.0.9.1 Japanese UI sample using fictional data and illustrative floor artwork. The app includes English UI: open Settings (設定) and select English.

## Report arena MAP problems and share evidence

**If a floor is clipped, the wrong field appears or patterns look broken, please share the duty, screenshots and reproduction details.**

- [Issues: bugs, logs and reproduction data (English and Japanese forms)](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/issues/new/choose)
- [Discussions: community chat, questions, layouts and reference material](https://github.com/Lu-ci-el/UltimateXIVMarkerManager/discussions/categories/general)
- [How to attach files and what to include](.github/SUPPORT.md#english)

You can attach screenshots and ZIP files. **Investigation and fixes depend on financial support and available development time. Reports, contributed data and donations do not guarantee a fix or deadline.** A donation is not required to report a problem.

Support development: **[Ko-fi](https://ko-fi.com/lost2)** / **[OFUSE](https://ofuse.me/lost)**

## Get started

1. Download the application ZIP and extract the entire folder to a writable location.
2. Run `UltimateXIVMarkerManager.exe`. Install [.NET 10 Desktop Runtime x64](https://dotnet.microsoft.com/en-us/download/dotnet/10.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) if needed.
3. Check the selected `ffxiv_dx11.exe` and adjacent `sqpack`. A valid saved selection is preferred; otherwise the standard installation location is checked. Use **Select EXE** for a different installation.
4. Check the character's `UISAVE.DAT`. The standard Documents location is checked, and a unique candidate can be selected automatically. With multiple characters or a custom location, use **Select UISAVE**.
5. Edit a preset, apply it to the draft, exit FFXIV, then use **Save** in the marker panel. Review the selected slots and differences before writing.

Saving to Library or an independent map is separate from writing marker slots to the game's UISAVE.

## Included in this release

- Create Strategy Boards and add, delete, duplicate or change object types. Edit text, color, opacity, flipping, layer order, titles and backgrounds.
- Edit both saved and shared drawings directly. Shared drawings do not need to be moved into the saved list. Move or copy drawings between either list.
- Ctrl+click to select multiple objects, move them together, align them vertically or horizontally, and use grid or nearby-object snapping. Undo and redo are available.
- Fix continuous canvas shrinking after entering the editor or resizing the window.

Open **Strategy Board → Saved list / Shared list → New drawing**, or select a drawing and choose **Edit**. A board supports up to 50 objects; text is limited to 31 UTF-8 bytes and titles to 63 UTF-8 bytes. Exit FFXIV, then choose **Save changes → Save to DAT** after reviewing the confirmation.

## Features and scope

| Feature | Available operations |
| --- | --- |
| Marker presets | Position editing, slot rearrangement, comparison/Merge, Focus editing and selected-slot saving |
| Backup / restore | Backup before saving and marker-slot restoration |
| Library | Saved layouts, folders, tags, notes, favorites and Pack import |
| Maps | Field map or top-down arena, initial/placement location, field and height selection, zoom, pan and grid |
| Map cache | Generated images stored beside the EXE and reused when compatible |
| Game Strategy Board | Create and directly edit saved/shared drawings; external export/import; folder insertion/deletion; move or copy between lists |
| Independent maps | Edit custom UXMM diagrams and share selected maps with Map PACK |

Game saved/shared drawings can be edited and saved in **Strategy Board**. Custom UXMM diagrams under **Maps** have a separate storage destination and do not generate new FFXIV shared codes. Arena lighting, glow, VFX and animated mechanics are not fully reproduced. Content-wide floor accuracy and compatibility after game updates still require checking.

Known MAP limitations remain: Aloalo Island can have clipped edges in placement/selected-height views, and first/second-phase views for P12S, E12S and P4S are not fully separated. Version 0.1.1.1 does not include fixes for these MAP issues.

## Documentation and files

- [Illustrated English guide](docs/USER_GUIDE_EN.md)
- [Japanese guide with current-version notes](docs/USER_GUIDE.md)
- [Archived Japanese PDF for 0.0.9.1](docs/UltimateXIVMarkerManager_Manual_0.0.9.1.pdf)

`.mmp` stores a Map PACK, `.mms` a Strategy saved list/folder, and `.mmsh` a shared list. Compatible legacy `.uxmm` imports are retained. Changing an extension does not convert a file.

## Distribution

The application is attached to GitHub Releases. This repository contains documentation and distribution information; **the application's development source is private**. GitHub's automatic “Source code” ZIP/tar.gz contains this documentation repository.

Keep all signed distribution files together. Personal data stays beside the EXE, including `Marker`, `settings`, `MAP` and WebView2 data in `runtimes/W2`. Close UXMM and back up your existing folder before updating; preserve those data folders.

For a bug report, include the version, duty, selected field/height, steps and error text. Hide personal paths and character details; do not post UISAVE files or your personal application folder.
