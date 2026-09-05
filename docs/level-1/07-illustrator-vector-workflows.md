# 07 · Illustrator Vector Workflows

Module 3 covered drawing individual shapes and paths. This module covers
combining them — **Pathfinder** operations to build complex shapes out of
simple ones, working with type as a design element (including text-on-a-
path), organizing a growing file with layers, and exporting the same
artwork differently for web versus print.

## 1. Pathfinder operations

The **Pathfinder** panel (**Window > Pathfinder**, Shift+⌘/Ctrl+F9)
combines multiple selected shapes into one new shape using boolean-style
operations — the standard way real logos and icons get built from basic
shapes rather than drawn point-by-point with the Pen tool.

1. Draw two overlapping shapes (e.g. a rectangle and a circle) and select
   both with the Selection tool (**V**, then drag a box around them, or
   Shift-click each).
2. **Unite** — merges both shapes into a single combined outline (their
   union). Use this to build a rounded-pill shape from a rectangle plus two
   circles at each end, for example.
3. **Minus Front** — subtracts the topmost selected shape from the one(s)
   below it, cutting a hole or notch shape. Use this for a crescent moon
   (circle minus an offset circle) or a shape with a bite taken out.
4. **Intersect** — keeps only the area where all selected shapes overlap,
   discarding everything else. Use this to create a shape that's exactly
   the overlap of two others (a classic Venn-diagram lens shape).
5. **Exclude** — keeps everything except the overlapping area, effectively
   punching out the intersection from the union. Use this for shapes with
   a hole cut exactly where two shapes overlapped.
6. After any Pathfinder operation, the result is a single new path — use
   the Direct Selection tool (**A**) afterward to refine individual points
   if the automatic result needs cleanup.

## 2. Typography and text-on-path

1. Press **T** for the **Type tool**. Click once on the canvas for
   point text (grows with what you type, doesn't wrap), or click-and-drag
   to create an **area type** box that wraps text within fixed bounds —
   use area type for anything longer than a headline.
2. Basic character formatting lives in **Window > Type > Character**: font
   family, size, tracking (letter-spacing), and leading (line-spacing) are
   the four properties worth learning first.
3. **Text on a path**: draw any open path with the Pen tool (Module 3),
   then select the **Type on a Path tool** (hidden under the Type tool —
   click and hold **T** to reveal it, or Shift+T) and click directly on the
   path — a text cursor appears anchored to that path's curve, and
   whatever you type flows along its shape instead of a straight line.
4. Adjust text-on-a-path position by dragging the small bracket markers
   that appear at the path's start/end/middle once you've typed something,
   or flip it to the other side of the path via **Type > Type on a Path >
   Type on a Path Options** and toggling **Flip**.
5. Save frequently-used formatting as a reusable **Character Style**
   (**Window > Type > Character Styles** > new style icon) — this is the
   same kind of asset you can push into a shared Library (Module 9).

## 3. Organizing layers in a growing file

As artwork gets more complex, Illustrator's **Layers** panel (**Window >
Layers**) becomes essential for staying in control of what's selectable and
visible.

1. Give every layer a real name (double-click it in the panel) as soon as
   you create meaningful content on it — "Layer 12" six layers deep is as
   unmanageable in Illustrator as in Photoshop.
2. Click the small square next to a layer's visibility eye to **lock** it
   — locked layers can't be accidentally selected or edited, useful for a
   background or reference layer you don't want to disturb.
3. Twirl open a layer's disclosure triangle to see (and select) individual
   objects nested inside it — useful for isolating one path in a complex
   group without clicking around on the canvas.
4. Use **Object > Group** (⌘/Ctrl+G) to bundle related objects (e.g. a logo
   mark and its wordmark) so they move, scale, and select together as one
   unit, independent of which layer they sit on.

## 4. Exporting for web vs. print

The same artwork typically needs two very different export treatments
depending on where it's going.

1. **For web**: **File > Export > Export As**, choose **PNG** or **SVG**.
   - **PNG** rasterizes the art at a specific pixel size (set the
     resolution in the dialog, e.g. 72 or 144 PPI) — appropriate for use
     as a plain image on a website.
   - **SVG** keeps the artwork as scalable vector markup, ideal for modern
     websites that display the same logo crisply at any screen size or
     zoom level.
2. **For print**: **File > Save As**, choose **PDF** (or keep the native
   `.ai`, which most print shops and prepress software can open directly).
   - In the Save As PDF dialog, choose the **Adobe PDF Preset**, e.g.
     **High Quality Print** or a press-specific preset your printer
     supplies — this controls resolution, bleed, and color settings.
   - Print work should use **CMYK** color mode (**File > Document Color
     Mode > CMYK Color**) since that's how commercial printing presses mix
     ink, whereas web/screen work should stay in **RGB**, matching how
     screens emit light. Check your document's mode before finalizing
     either kind of export.
3. **Bleed and safe area** for print jobs that go right to the paper's
   edge: **File > Document Setup** lets you add a bleed value (commonly 3mm
   or 0.125in) so artwork slightly overhangs the trim line, avoiding thin
   white slivers if the physical cut is a fraction off.

## Cheat sheet

| Tool/Action | Shortcut |
|---|---|
| Pathfinder panel | Shift+⌘/Ctrl+F9 |
| Unite / Minus Front / Intersect / Exclude | Pathfinder panel buttons |
| Type tool | T |
| Type on a Path tool | Shift+T (or click-hold on Type tool) |
| Group objects | ⌘/Ctrl+G |
| Layers panel | Window > Layers |
| Export for web (PNG/SVG) | File > Export > Export As |
| Save for print (PDF) | File > Save As > Adobe PDF |
| Switch to CMYK (print) | File > Document Color Mode > CMYK Color |
| Set bleed | File > Document Setup |

## How It Actually Works

- **Pathfinder operations are boolean set algebra performed on path
  geometry.** Illustrator treats each closed path as defining a set of
  enclosed points on the plane; Unite computes the mathematical union of
  those point sets and re-traces a single outline around the combined
  region, Intersect keeps only points common to all sets, Minus Front
  subtracts one set from another, and Exclude is a symmetric difference
  (union minus intersection). The result is always freshly recomputed path
  geometry — new anchor points where boundaries crossed — not the original
  shapes hidden behind a mask, which is why the source shapes stop existing
  as separate editable objects unless you use the non-destructive **Shape
  Builder** or the Pathfinder panel's Expand-later options instead.
- **Text-on-a-path repurposes the path as a positioning spine, not a
  container.** Illustrator measures the path's arc length and lays out each
  glyph's baseline as an offset along that arc, rotating each character to
  stay tangent to the curve at its position — this is why very tight curves
  cause glyphs to visually overlap or fan apart (the tangent angle changes
  faster than the glyph width can compensate for) and why flipping the text
  effectively reverses which direction the arc-length offset is measured
  from.
- **RGB and CMYK aren't just different presets, they're different, non-
  interchangeable color models with different gamuts.** RGB is additive —
  a display starts black and adds red/green/blue light to reach a color,
  covering a wide gamut including highly saturated colors screens can emit
  directly. CMYK is subtractive — ink absorbs (subtracts) wavelengths from
  reflected white light, and the achievable gamut is physically smaller,
  especially in saturated blues, greens, and oranges. Converting a
  saturated RGB color to CMYK necessarily clips it to the nearest color the
  ink combination can reproduce, which is the actual mechanism behind
  colors "looking duller" after switching Document Color Mode — it isn't
  a display bug, it's a real reduction in reproducible color.
- **SVG export serializes the same path math as literal markup, while PNG
  export rasterizes it once at a fixed size.** An exported SVG's `<path d="...">`
  attribute contains the same anchor-point and Bézier-handle coordinates
  Illustrator uses internally, encoded as SVG's path command syntax — the
  browser's own rendering engine re-runs the same curve math at whatever
  size the SVG is displayed, which is the actual reason it stays crisp at
  any zoom. PNG export instead asks Illustrator to rasterize that vector
  math once, at the PPI/pixel-dimensions you specify, permanently locking
  in a fixed pixel grid — after that, it behaves exactly like any other
  raster image, sharp only at or below its exported resolution.
- **Bleed works because presses cannot cut with zero tolerance.** A
  bleed value tells Illustrator to extend background artwork past the
  trim boundary; the physical guillotine or cutting die is only accurate to
  within a small tolerance, so if art stopped exactly at the trim line, any
  cut that lands a fraction of a millimeter short would reveal a sliver of
  uncut white paper. Extending artwork into the bleed margin means that
  tolerance window is safely covered by more of the same artwork instead of
  blank stock, regardless of which direction the real cut drifts.

## Exercise

Using the artboard you left blank in Module 3's exercise, build a simple
icon or badge shape using at least two Pathfinder operations (e.g. Unite
two shapes, then Minus Front to cut a notch). Add a short label using
Type-on-a-Path around part of the shape. Name and organize your layers.
Then export the result twice: once as an SVG for web use, and once as a
PDF with the document color mode switched to CMYK for print.
