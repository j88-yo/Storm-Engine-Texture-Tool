# Storm Engine Texture Tool

Utility for viewing and converting textures with `.tga`, `.png`, `.tga.tx`, and `.dds` file types.

Designed for working with textures while creating user modifications, test materials, and non-commercial game builds based on the Storm Engine ([Storm Engine GitHub](https://github.com/storm-devs/storm-engine)).

The application allows you to:
- view textures and their properties, including resolution, storage format, color depth, alpha channel type, mip level count, and compression method;
- convert from `.tga` or `.png` to `.dds` or `.tga.tx` at resolutions up to 16K, including mip-level generation;
- convert from `.dds` or `.tga.tx` to `.tga` or `.png` without quality loss;
- use DXT1 / DXT3 / DXT5 compression;
- perform single-file and batch file conversion;
- open `.tga`, `.dds`, and `.tga.tx` files directly from Windows Explorer;
- work in one or several windows.

Texture compression uses the latest NVIDIA Texture Tools version (NVTT 3.2.5, 2024).

---

# Supported Storage Formats

## A8R8G8B8

Uncompressed 32-bit format.

- maximum image quality without losses;
- 8-bit alpha transparency;
- largest file size.

Approximate texture size for 1024×1024 — ~4 MB.

---

## X8R8G8B8

Uncompressed 32-bit format.

- no alpha;
- maximum image quality without losses;
- largest file size.

Approximate texture size for 1024×1024 — ~4 MB.

---

## A4R4G4B4

16-bit format.

- 4-bit alpha with limited smoothness;
- reduced color precision compared to 32-bit formats;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## A1R5G5B5

16-bit format.

- 1-bit alpha;
- transparency works only in fully visible / invisible pixel mode;
- reduced color precision;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## R5G6B5

16-bit format.

- no alpha;
- less saturated colors compared to 32-bit formats;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## DXT1

Compressed format.

- compression, no alpha;
- minimum file size;
- noticeable artifacts are possible.

Approximate texture size for 1024×1024 — ~512 KB.

---

## DXT3

Compressed format.

- compression, sharp alpha;
- suitable for textures with hard alpha edges;
- approximate texture size for 1024×1024 — ~1 MB.

---

## DXT5

Compressed format.

- compression, smooth alpha;
- no noticeable quality loss;
- approximate texture size for 1024×1024 — ~1 MB.

---

# Working with the Application

## Texture Preview

To preview a texture, select a `.tga` or `.png` file in the left file panel, or a `.dds` or `.tga.tx` file in the right file panel.

Supported features:
- zooming with the mouse wheel, slider, and the `1:1` (100%) and `⛶` (Fit) buttons;
- browsing textures using interface buttons and `←`, `→`, `↑`, `↓` keys;
- dragging the image with the mouse;
- switching preview background modes;
- fullscreen preview mode via the `Expand Preview` button, with exit by `ESC`.

---

## Working with Files and Folders

The left file panel is intended for `.tga` and `.png` (source files); the right panel is for `.dds` and `.tga.tx` (output files).

Supported features:
- folder navigation with `Home` (go to the drive list), `Up`, `Back`, `Forward`, and mouse side buttons;
- file list navigation with the keyboard `↑`, `↓`, `←`, `→`;
- quick file jump: pressing a letter or digit in the file list selects the nearest file whose name starts with that character;
- file sorting by name, type, size, and format, ascending and descending (A to Z and Z to A);
- pinning and unpinning folders through the context menu or the icon to the left of the folder in the file table or in the pinned folders block;
- pinned folders are displayed above the file table in each file panel;
- drag-and-drop reordering of pinned folders;
- opening the conversion window with a double-click or `Enter`; the output format is the last one selected in that panel (`DDS` or `TGA.TX` on the left, `TGA` or `PNG` on the right);
- confirming actions with `Enter`, renaming with `F2`, deleting selected files with `Delete`;
- context menu actions: convert, open file folder, open folder in Windows Explorer, rename, delete.

---

## File Association

In the About window, the “Open TGA / DDS / TGA.TX with Storm Engine Texture Tool” switch sets the application as the default program for `.tga`, `.dds`, and `.tga.tx` files.

- enabled — the files open from Windows Explorer and are shown with their own format icons;
- disabled — the association and icons are removed, and the files open with the previous default program.

---

## Multiple Windows

In the About window, the “Allow opening in multiple windows” switch controls the behavior when the application is launched again or a file is opened.

- enabled — each new launch or file opening creates a separate window;
- disabled — the already open window is used.

---

# Conversion

## Convert to DDS / TGA.TX

Select a `.tga` or `.png` file in the left file panel and press:
- `DDS →` — convert to `.dds`;
- `TGA.TX →` — convert to `.tga.tx`.

Supported features:
- storage format selection (8 formats: A8R8G8B8, X8R8G8B8, R5G6B5, A1R5G5B5, A4R4G4B4, DXT1, DXT3, DXT5);
- DXT1 / DXT3 / DXT5 compression;
- mip-level generation;
- replacing existing files;
- creating copies when file names already exist;
- calculating the total size of selected files before and after conversion;
- remembering settings: after a successful conversion, the selected format, alpha state, and mip-level settings are saved separately for DDS and TGA.TX and applied the next time the window is opened.

Conversion is supported for textures of any resolution up to 16384×16384.

---

## Convert to TGA / PNG

Select a `.dds` or `.tga.tx` file in the right file panel and press:
- `← TGA` — output format TGA, 32-bit, 8-bit alpha, lossless;
- `← PNG` — output format PNG, 32-bit, 8-bit alpha, lossless.

---

## Mip Levels

Supported modes:
- base level only (1 mip level);
- full mip chain;
- custom mip-level count.

Mip levels are used for correct texture rendering when the distance to an object changes. Their number depends on the texture size.
A full mip chain is recommended for most textures.

---

## Batch Conversion

For batch conversion, select several files in the file panel and press the conversion button.

Supported features:
- simultaneous conversion of several `.tga` and `.png` or several `.dds` / `.tga.tx` files;
- replacing existing files;
- creating copies;
- skipping conflicting files.

During conversion, the processing progress and the number of processed textures are displayed.

