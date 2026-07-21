# 02 · Photoshop Basics

Photoshop is a pixel-based (**raster**) image editor: every image is a grid
of colored pixels, which makes it the right tool for photos and painted or
composited artwork, as opposed to the scalable vector shapes you'll meet in
Illustrator (Module 3). This module covers the workspace, the Layers panel,
making selections, cropping/resizing, and exporting — the moves you'll use
in nearly every later Photoshop lesson.

## 1. Workspace tour

1. Open Photoshop and create a new document: **File > New** (⌘/Ctrl+N).
   Pick the **Web** or **Photo** preset category, choose any size (e.g.
   1000×1000 px), and click **Create**.
2. The workspace has four areas you'll use constantly:
   - **Toolbar** (far left) — selection, painting, and shape tools.
   - **Options bar** (top, under the menu) — changes based on which tool is
     active; this is where you set brush size, selection mode, etc.
   - **Canvas** (center) — your document.
   - **Panels** (right, docked) — Layers, Properties, Adjustments, and more.
3. If a panel is missing, every panel lives under the **Window** menu —
   e.g. **Window > Layers** toggles the Layers panel back on if you
   accidentally closed it.
4. Zoom with **⌘/Ctrl +** / **⌘/Ctrl -**, or **⌘/Ctrl+0** to fit the whole
   canvas in the window. Hold **Space** and drag to pan around when zoomed
   in.

## 2. The Layers panel

Photoshop documents are stacked **layers** — think of each as a separate
sheet of acetate, composited top-to-bottom. Almost everything non-trivial
you do in Photoshop involves managing layers deliberately rather than
flattening everything into one.

1. Open **Window > Layers** if it isn't already visible.
2. Click the **New Layer** icon (bottom of the panel, or **Layer > New >
   Layer**, Shift+⌘/Ctrl+N) to add a blank layer above the current one.
3. Layers higher in the stack draw on top of layers below them. Drag a
   layer up or down in the panel to reorder it.
4. Each layer has a visibility toggle (the eye icon) — click it to hide/show
   that layer without deleting it, useful for comparing versions.
5. Double-click a layer's name to rename it — do this constantly; "Layer 14"
   six layers deep is how projects become unmanageable.
6. Group related layers with **Layer > Group Layers** (⌘/Ctrl+G) after
   selecting them (⌘/Ctrl-click or Shift-click to multi-select in the
   panel) — groups act like folders and keep a complex file navigable.

!!! info "Opacity vs. Fill"
    The **Opacity** slider (top of the Layers panel) fades the whole layer,
    including any layer styles (like a drop shadow) applied to it. **Fill**
    fades only the layer's own pixels, leaving layer styles at full
    strength — useful for a stroke-only or shadow-only effect on an
    otherwise invisible shape.

## 3. Basic selections

A selection tells Photoshop "only apply the next action inside this area."

1. **Marquee tools** (rectangle/ellipse) — press **M**, then drag on the
   canvas. Hold **Shift** while dragging to constrain to a square/circle.
2. **Lasso tool** — press **L**, then drag freehand around an area. Use the
   **Polygonal Lasso** (cycle with Shift+L) for straight-edged freehand
   selections, clicking a point at each corner.
3. **Quick Selection tool** — press **W**, then paint over the area you
   want; Photoshop expands the selection to nearby similar pixels
   automatically, which is much faster than lassoing a complex shape.
4. Combine selections without restarting: hold **Shift** while
   selecting to **add** to the current selection, hold **Option/Alt** to
   **subtract** from it.
5. **Select > Deselect** (⌘/Ctrl+D) clears the active selection — a command
   you'll use after almost every selection-based edit.

## 4. Cropping and resizing

Cropping changes the canvas boundary; resizing changes the pixel dimensions
of the whole image. They're different operations and it matters which one
you reach for.

1. **Crop tool** — press **C**, drag handles on the canvas edges to define
   the new boundary, then press **Enter/Return** to commit (or **Esc** to
   cancel). The Options bar lets you type an exact aspect ratio (e.g.
   `16:9`) so the crop stays proportional.
2. **Resize the whole image** — **Image > Image Size** (⌥/Alt+⌘/Ctrl+I).
   With the link icon next to Width/Height enabled, changing one
   dimension scales the other proportionally, avoiding a stretched result.
3. **Resize the canvas without scaling pixels** — **Image > Canvas Size**
   (⌥/Alt+⌘/Ctrl+C) adds or removes blank space around the existing image;
   use the anchor grid to control which side the new space is added to.
4. Resizing up (enlarging) a raster image beyond its original pixel count
   always loses sharpness — Photoshop's "Preserve Details" resampling
   method in Image Size handles this better than the default, but there's
   no way to invent detail that was never captured. This is a fundamental
   difference from Illustrator's vector shapes, which scale infinitely
   without quality loss (see Module 3).

## 5. Saving and exporting formats

Photoshop distinguishes between its native **working format** and
**export formats** meant for sharing or use elsewhere.

1. **File > Save** (⌘/Ctrl+S) saves as `.psd` — Photoshop's native format,
   which preserves layers, layer styles, and editability. Always keep a
   `.psd` as your source file.
2. **File > Export > Export As** (⌥/Alt+⌘/Ctrl+Shift+W) gives a live preview
   dialog for exporting a flattened copy:
   - **PNG** — supports transparency, lossless; best for graphics, UI
     assets, and anything needing a transparent background.
   - **JPG** — no transparency, lossy (adjustable quality slider); best for
     photos where file size matters more than pixel-perfect fidelity.
3. **File > Save a Copy** (⌥/Alt+⌘/Ctrl+S) saves a flattened or format-
     converted copy without altering your open `.psd`.
4. For a quick single-format export without the preview dialog, use
   **File > Export > Quick Export as PNG**.

## Cheat sheet

| Tool/Action | Shortcut |
|---|---|
| New document | ⌘/Ctrl+N |
| New layer | Shift+⌘/Ctrl+N |
| Group selected layers | ⌘/Ctrl+G |
| Marquee (rectangle/ellipse) select | M |
| Lasso select | L |
| Quick Selection tool | W |
| Deselect | ⌘/Ctrl+D |
| Crop tool | C |
| Image Size | ⌥/Alt+⌘/Ctrl+I |
| Canvas Size | ⌥/Alt+⌘/Ctrl+C |
| Save (native .psd) | ⌘/Ctrl+S |
| Export As (PNG/JPG with preview) | ⌥/Alt+⌘/Ctrl+Shift+W |
| Fit image to window | ⌘/Ctrl+0 |

## Exercise

Create a new 1200×800 px document. Add three layers: a solid-color
background, a shape or pasted image on top, and a text layer. Rename all
three layers descriptively and group the shape and text layers together.
Use the Quick Selection tool to select just the background layer's content
and fill it with a different color. Crop the canvas to a 1:1 square, then
export a flattened PNG and a JPG at 80% quality, and compare the two file
sizes.
