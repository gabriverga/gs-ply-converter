# GS PLY → RGB PLY Converter

A browser-based tool to convert Gaussian Splatting `.ply` files into standard RGB point clouds — no installation required.

---

## Why this exists

**Gaussian Splatting** is a technique for capturing and rendering 3D scenes from photos or video. The output is a `.ply` file where colors are not stored as standard RGB values, but as **spherical harmonics DC components** (`f_dc_0`, `f_dc_1`, `f_dc_2`) — a mathematical representation that most 3D software cannot read directly.

I ran into this problem while downloading `.ply` files from **World Lab / Marble World**: every time I imported them into CloudCompare, Houdini or Blender, the point cloud showed up with completely wrong or missing colors.

This tool fixes exactly that — it reads the `f_dc` values, converts them to proper RGB using a sigmoid function, and outputs a clean `.ply` file that any software can read correctly.

---

## Before & after

| Before | After |
|--------|-------|
| ![Wrong colors — the point cloud appears as a flat yellow-green mass](images/before.png) | ![Correct colors — the point cloud shows realistic colors](images/after.png) |

---

## Live demo

👉 [**Open the converter**](https://gabriverga.github.io/gs-ply-converter)

---

## How to use

![The converter UI — a dark drop zone with animated particles](images/ui.png)

**1. Open the page**
Go to the link above. No installation, no account needed.

**2. Drop your file**
Drag and drop your Gaussian Splatting `.ply` file into the drop zone, or click to browse.

**3. Convert**
Click **Convert to RGB PLY**. A progress bar will show the conversion status. Depending on the file size this may take a few seconds.

**4. Download**
Once done, click **Download converted .ply** to save the file.

---

**Compatible with:** Unity, CloudCompare, Blender, Houdini...

---

## Credits

Created by [@gabriverga](https://www.instagram.com/gabriverga/) with [Claude Code](https://claude.ai/code)
