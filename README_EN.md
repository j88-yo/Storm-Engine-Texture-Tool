# Storm Engine Texture Tool

Utility for viewing and converting textures with `.tga` and `.tga.tx` file types.

Designed for working with textures while creating user modifications, test materials, and non-commercial game builds based on the Storm Engine (https://github.com/storm-devs/storm-engine)

The application allows you to:
- view textures and their properties, including resolution, storage format, color depth, alpha channel type, mip level count, and compression method;
- convert textures between TGA and TX up to 16K resolution, including mip-level generation;
- use DXT1 / DXT3 / DXT5 compression;
- perform batch file conversion;
- use the application to open `.tga.tx` files directly from Windows Explorer.

Texture compression uses the latest NVIDIA Texture Tools version (NVTT 3.2.5, 2024).

---

# Supported Storage Formats

## A8R8G8B8

Uncompressed 32-bit format.

- maximum image quality without losses;
- 8-bit alpha channel transparency;
- largest file size.

Approximate texture size for 1024×1024 — ~4 MB.

---

## X8R8G8B8

Uncompressed 32-bit format.

- no transparency;
- maximum image quality without losses;
- largest file size.

Approximate texture size for 1024×1024 — ~4 MB.

---

## A4R4G4B4

16-bit format.

- 4-bit alpha channel transparency with limited smoothness;
- reduced color precision compared to 32-bit formats;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## A1R5G5B5

16-bit format.

- 1-bit alpha channel transparency;
- transparency works only in fully visible / invisible pixel mode;
- reduced color precision;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## R5G6B5

16-bit format.

- no transparency;
- reduced color precision compared to 32-bit formats;
- compact file size.

Approximate texture size for 1024×1024 — ~2 MB.

---

## DXT1

Compressed format.

- 4-bit block compression;
- 1-bit alpha channel transparency;
- transparency works only in fully visible / invisible pixel mode;
- noticeable image quality loss;
- minimum file size.

Approximate texture size for 1024×1024 — ~512 KB.

---

## DXT3

Compressed format.

- 8-bit block compression;
- 4-bit alpha channel transparency;
- higher quality compared to DXT1;
- possible artifacts on smooth transparency gradients.

Approximate texture size for 1024×1024 — ~1 MB.

---

## DXT5

Compressed format.

- 8-bit block compression;
- 8-bit alpha channel transparency;
- optimal balance between quality and file size;
- most universal format.

Approximate texture size for 1024×1024 — ~1 MB.
DXT5 is the recommended format for most textures.

---

# Working with the Application

## Texture Preview

To preview a texture, select a `.tga` file in the left panel or a `.tga.tx` file in the right panel.

The image will automatically appear in the preview area.

Supported features:
- zooming (mouse wheel, slider, preview area buttons, 1:1 / 100% scale, fit to preview area);
- texture browsing (interface buttons and left / right arrow keys);
- image dragging;
- background switching (light, dark, checkerboard);
- fullscreen preview mode (hiding interface panels using fullscreen or panel toggle buttons, returning to standard mode with the `ESC` key).

---

## Working with Files and Folders

The left file panel is предназначена for `.tga` files, the right panel — for `.tga.tx`.

Supported features:
- folder navigation buttons (back / forward, up, “My Computer”, “Downloads”, drives), additional mouse side buttons (back / forward actions);
- pinning and unpinning folders (through the context menu or the icon to the left of the folder);
- pinned folders section (`★`);
- batch conversion of selected files;
- file operations through the context menu:
  - open file folder;
  - open folder in Windows Explorer;
  - rename;
  - delete.

---

# Conversion

## Converting to `.tga.tx`

To convert to `.tga.tx`, select a `.tga` file in the left file panel and press the “Build TX” button.

Supported features:
- storage format selection;
- DXT1 / DXT3 / DXT5 compression;
- mip-level generation;
- replacing existing files;
- creating copies when file names already exist.

Conversion to `.tga.tx` is supported for textures with power-of-two dimensions.
Examples: 256×256, 512×1024, 2048×2048, 4096×8192, 16384×16384.

---

## Converting to `.tga`

To convert to `.tga`, select a `.tga.tx` file in the right file panel and press the “Extract TGA” button.
Conversion is performed into an uncompressed 32-bit A8R8G8B8 format with alpha channel while preserving the original image quality without losses.

---

## Mip Levels

Supported modes:
- base level only (1 mip level);
- full mip chain;
- custom mip-level count.

Mip levels are used for correct texture rendering at different object distances. Their amount depends on the texture size.
Using a full mip chain is recommended for most textures.

---

## Batch Conversion

For batch conversion, select multiple files in the file panel and press the “Build TX” or “Extract TGA” button.

Supported features:
- simultaneous conversion of multiple files;
- replacing existing files;
- creating copies;
- skipping conflicting files.

During conversion, the processing progress and the number of processed textures are displayed.
After completion, the final processing result is shown.
