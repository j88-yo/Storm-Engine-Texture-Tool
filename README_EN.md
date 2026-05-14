# Storm Engine Texture Tool 0.5.2 — User Guide

# 1. Introduction

Storm Engine Texture Tool is a utility for viewing and converting textures between `.tga.tx` and `.tga` formats.

The application allows you to:
- preview textures;
- view texture parameters;
- convert TGA ↔ TX;
- convert TX textures with mipmaps;
- use DXT1 / DXT3 / DXT5 compression;
- perform batch file conversion.

The utility uses a dual-panel interface with a built-in preview area and supports the main compression modes used by the Storm Engine.

NVIDIA Texture Tools library is used for texture compression.

Supported formats:
- `.tga`
- `.tga.tx`

---

# 2. Using the Application

## Texture Preview

Select a `.tga` or `.tx` file in one of the file panels.

The image will automatically appear in the preview area.

Supported features:
- mouse wheel zoom;
- zoom reset;
- 1:1 mode;
- Fit mode;
- image panning;
- alpha channel preview;
- hiding interface panels.

If at least one interface panel is hidden, pressing `ESC` restores the default layout.

---

## File Panels

The file panels support:
- folder navigation;
- pinned folders;
- multi-selection;
- mouse Back and Forward buttons;
- context menu:
  - open;
  - open file location;
  - rename;
  - delete.

---

## Information Block

The information block displays:
- texture resolution;
- format;
- alpha type;
- bit depth;
- mip level count;
- file size.

Some parameters include additional tooltip descriptions.

---

# 3. Conversion

## TX Build

The following formats are available for `.tga.tx` creation:

Uncompressed:
- A8R8G8B8
- X8R8G8B8
- A4R4G4B4
- A1R5G5B5
- R5G6B5

DXT Compression:
- DXT1
- DXT3
- DXT5

Texture compression is performed using the NVIDIA Texture Tools library.

---

## Mipmaps

Supported modes:
- base level only;
- full mip chain;
- custom mip count.

Mipmaps are used for more stable texture rendering at long distances.

To generate mipmaps correctly, texture dimensions must use power-of-two sizes.

---

## Batch Conversion

The application supports simultaneous processing of multiple files.

Available conflict handling modes:
- overwrite existing files;
- create copies;
- skip conflicting files.

After conversion is complete, the application displays a final processing result.

---

# 4. Additional Information

The application can be used as the default viewer for `.tga.tx` files.

Default file association is available in the "About" section.

---

# 5. Limitations

The utility supports textures with power-of-two dimensions only.

Some textures may use non-standard storage parameters.

DXT compression may affect image quality.