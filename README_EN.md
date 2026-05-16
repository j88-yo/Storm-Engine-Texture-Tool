# Storm Engine Texture Tool

Utility for viewing and converting textures with `.tga`, `.png`, and `.tga.tx` file types.

Designed for working with textures while creating user modifications, test materials, and non-commercial game builds based on the Storm Engine ([Storm Engine GitHub](https://github.com/storm-devs/storm-engine)).

The application allows you to:
- view textures and their properties, including resolution, storage format, color depth, alpha channel type, mip level count, and compression method;
- convert `.tga` and `.png` textures to `.tga.tx` at resolutions up to 16K, including mip-level generation;
- unpack `.tga.tx` into `.tga` or `.png` without quality loss;
- use DXT1 / DXT3 / DXT5 compression;
- perform single-file and batch file conversion;
- use a convenient bulk upscaling pipeline: unpack `.tga.tx` to `.png`, process textures in an external upscaler, then build them back into `.tga.tx`;
- open `.tga` and `.tga.tx` files directly from Windows Explorer.

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
- recommended by default;
- approximate texture size for 1024×1024 — ~1 MB.

---

# Working with the Application

## Texture Preview

To preview a texture, select a `.tga` or `.png` file in the left file panel, or a `.tga.tx` file in the right file panel.

Supported features:
- zooming with the mouse wheel, slider, and `1:1`, `100%`, `Fit` buttons;
- browsing textures using interface buttons and `←`, `→`, `↑`, `↓` keys;
- dragging the image with the mouse;
- switching preview background modes;
- fullscreen preview mode with exit by `ESC`.

---

## Working with Files and Folders

The left file panel is intended for `.tga` and `.png`, the right panel — for `.tga.tx`.

Supported features:
- folder navigation with `Back`, `Forward`, `Up`, `My Computer`, `Downloads`, and mouse side buttons;
- file list navigation with `↑`, `↓`, `←`, `→`;
- file sorting by name and file type;
- pinning and unpinning folders through the context menu or the icon to the left of the folder;
- pinned folders section (`★`);
- drag-and-drop reordering of pinned folders;
- opening the conversion window with `Enter`, confirming actions with `Enter`, deleting selected files with `Delete`;
- context menu actions: open file folder, open folder in Windows Explorer, rename, delete.

---

# Conversion

## Converting to `.tga.tx`

To convert to `.tga.tx`, select a `.tga` or `.png` file in the left file panel and press the `Build TX` button.

Supported features:
- storage format selection;
- DXT1 / DXT3 / DXT5 compression;
- mip-level generation;
- replacing existing files;
- creating copies when file names already exist;
- calculating the total size of selected files before and after conversion.

Conversion to `.tga.tx` is supported for textures with power-of-two dimensions.
For example: 256×256, 512×1024, 2048×2048, 4096×8192, 16384×16384.

---

## Unpacking `.tga.tx`

To unpack `.tga.tx`, select the desired file in the right file panel and press the `Unpack` button.

In the unpacking window, select the output format:
- `.tga` — 32-bit TGA, 8-bit alpha, lossless;
- `.png` — 32-bit PNG, 8-bit alpha, lossless.

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

For batch conversion, select several files in the file panel and press the `Build TX` or `Unpack` button.

Supported features:
- simultaneous conversion of several `.png` and `.tga` files;
- replacing existing files;
- creating copies;
- skipping conflicting files.

During conversion, the processing progress and the number of processed textures are displayed.
After the operation is completed, the final processing result is displayed.
