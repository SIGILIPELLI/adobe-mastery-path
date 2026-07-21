# 03 · Illustrator Basics

Illustrator is a **vector** editor: shapes are stored as mathematical paths
(points and curves) rather than a grid of pixels, so they scale to any size
— a business card and a billboard — with no loss of sharpness. This module
covers the workspace, artboards, basic shapes, the Pen tool, and the
vector-vs-raster distinction that decides when you reach for Illustrator
instead of Photoshop.

## 1. Workspace tour

1. Open Illustrator and create a new document: **File > New** (⌘/Ctrl+N).
   Pick any preset (e.g. **Web** at 1000×1000 px) and click **Create**.
2. The layout mirrors Photoshop's: **Toolbar** (left), **Options/Control
   bar** (top), **Artboard/canvas** (center), **Panels** (right — Layers,
   Properties, Swatches, Stroke).
3. Every panel is reachable via the **Window** menu if it's not docked —
   **Window > Layers**, **Window > Stroke**, etc.
4. Zoom with **⌘/Ctrl +** / **⌘/Ctrl -**; **⌘/Ctrl+0** fits the active
   artboard in the window. Hold **Space** and drag to pan.

## 2. Artboards

An **artboard** is Illustrator's equivalent of a page or canvas boundary —
and unlike Photoshop, a single Illustrator document can hold many
artboards, useful for a set of related assets (e.g. a logo at three sizes,
or three social-media post variants) in one file.

1. Press **Shift+O** to select the **Artboard tool**. Drag on an empty part
   of the canvas to create a new artboard; drag an existing artboard's edge
   handles to resize it.
2. **Window > Artboards** lists every artboard in the document and lets you
   rename, reorder, or duplicate them.
3. To duplicate an existing artboard along with everything on it, select it
   with the Artboard tool and Option/Alt-drag it to a new position.
4. Each artboard exports as its own file when you use **File > Export >
   Export As** with **Use Artboards** checked — handy for producing several
   sized logo variants from one source file (used in Module 7 and the
   Module 10 capstone).

## 3. Basic shapes

1. Press **M** for the **Rectangle tool** (cycle Shift+M for Rounded
   Rectangle), **L** for the **Ellipse tool**. Drag on the canvas to draw;
   hold **Shift** while dragging to constrain to a perfect square/circle.
2. Every shape has both a **Fill** (interior color) and a **Stroke**
   (outline) — set both from the color swatches at the bottom of the
   Toolbar, or the **Window > Color** panel for precise values.
3. The **Selection tool** (**V**) moves and resizes whole shapes; the
   **Direct Selection tool** (**A**) selects and drags individual anchor
   points or path segments within a shape — you'll need Direct Selection
   constantly once you start editing paths in Module 7.
4. Shapes support live corner-radius handles: with the Selection tool
   active, click a rectangle to reveal small circular handles at its
   corners — drag one to round all four corners live, non-destructively.

## 4. The Pen tool — fundamentals

The **Pen tool** (**P**) draws arbitrary paths point-by-point and is the
core skill that separates basic Illustrator use from real vector drawing —
it's how logos, icons, and custom shapes actually get built.

1. Click once to place a straight-line anchor point; click again elsewhere
   to draw a straight segment between the two points.
2. Click-and-**drag** (instead of a plain click) to place an anchor point
   with curve handles — dragging out further makes the curve on either side
   of that point more pronounced.
3. Close a path by clicking back on the very first anchor point (a small
   circle appears next to the pen cursor when you're hovering over it,
   confirming it will close the path).
4. Press **Esc** or select a different tool to end an open path without
   closing it.
5. While actively drawing, hold **Option/Alt** and click a curve point to
   convert it to a corner point for the next segment — this is how a single
   path mixes smooth curves and sharp corners (e.g. a speech-bubble shape).
6. Use the **Direct Selection tool** (**A**) afterward to click and drag
   individual anchor points or their curve handles to refine a path you've
   already drawn.

!!! warning "The Pen tool has a learning curve — that's normal"
    Getting smooth, evenly-spaced curves with the Pen tool takes practice.
    A reliable way to build intuition: trace the outline of a simple round
    logo or icon placed on a locked layer beneath your drawing layer, using
    as few anchor points as possible — fewer, well-placed points make
    smoother curves than many closely-spaced ones.

## 5. Vector vs. raster

This is the single most important concept to internalize before moving
between Illustrator and Photoshop:

| | Vector (Illustrator) | Raster (Photoshop) |
|---|---|---|
| Stored as | Math (points, curves, fills) | A grid of colored pixels |
| Scaling | Infinite, no quality loss | Loses sharpness past original resolution |
| Best for | Logos, icons, type, illustrations | Photos, painted/composited images |
| File formats | `.ai`, `.svg`, `.eps` | `.psd`, `.jpg`, `.png` (as a raster) |

You can bring a raster image into Illustrator (**File > Place**) to trace
or use as reference, and you can bring vector art into Photoshop, where it
becomes a **Smart Object** that stays somewhat scalable within Photoshop
but ultimately renders to pixels once flattened. But a vector path itself —
the anchor points and curves — cannot be "converted back" from a rasterized
image; once flattened to pixels, the underlying path math is gone. This is
why logos should always be designed and archived in Illustrator, even if a
raster export is what actually ships.

## Cheat sheet

| Tool/Action | Shortcut |
|---|---|
| New document | ⌘/Ctrl+N |
| Artboard tool | Shift+O |
| Rectangle tool | M |
| Ellipse tool | L |
| Selection tool (move/resize whole shapes) | V |
| Direct Selection tool (edit anchor points) | A |
| Pen tool | P |
| Constrain shape to square/circle while dragging | Shift |
| Place a raster image | File > Place |
| Export artboards (with sizes/formats) | File > Export > Export As |
| Fit artboard to window | ⌘/Ctrl+0 |

## Exercise

Create a new document with three artboards side by side (use **Window >
Artboards** to confirm you have exactly three). On the first, draw a
rounded rectangle and a circle with a Fill and Stroke of your choosing. On
the second, draw a simple closed shape using only the Pen tool that mixes
at least one straight segment and one curved segment (e.g. a speech
bubble or a rounded arrow). Leave the third blank for now — you'll use it
in Module 7. Export all three artboards as separate PNGs using **Export As
> Use Artboards**.
