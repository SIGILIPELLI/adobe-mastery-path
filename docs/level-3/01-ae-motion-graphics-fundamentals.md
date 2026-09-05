# 01 · After Effects Motion Graphics Fundamentals

Everything in Levels 1-2 lived in a single frame: a photo, a poster, a
static layout. After Effects adds the missing dimension — **time**. This
module covers the core building blocks every AE project is made of:
compositions, layers, the Timeline, and basic transform animation, so the
rest of Level 3 (keyframing, compositing, expressions, tracking) has
somewhere to stand.

## 1. Creating a composition

1. Launch After Effects and choose **Composition > New Composition...**
   (or click **New Composition** on the Home Screen).
2. Set **Width/Height** (e.g. 1920x1080), **Frame Rate** (24, 25, or 29.97
   fps depending on delivery target), **Resolution** (Full for final
   render, Half while working on a slower machine), and **Duration** (e.g.
   0:00:10:00 for a 10-second piece).
3. Click **OK**. The new composition opens as a tab in the **Composition**
   panel, with a matching entry in the **Project** panel and an empty
   **Timeline** panel below.
4. Save the project immediately (**File > Save As**) into a dedicated
   project folder — After Effects projects reference footage by path, so
   keeping a stable folder structure from the start avoids "missing
   footage" relinking later.

## 2. Importing and adding footage as layers

1. **File > Import > File...** (or double-click empty space in the Project
   panel) to bring in images, video, or audio. Multi-file selections and
   whole folders (**Import As: Footage** vs **Import As: Composition** for
   an Illustrator/Photoshop file with layers) are both supported.
2. Drag any Project panel item onto the Timeline to add it as a layer in
   the active composition, or onto the Composition panel to place and
   position it at the same time.
3. For a layered Photoshop or Illustrator file, choose **Composition -
   Retain Layer Sizes** on import so each layer keeps its own
   editable bounding box instead of being flattened.
4. Reorder layers by dragging them up/down in the Timeline's stacking
   order — exactly like Photoshop, layers higher in the stack render on
   top.

## 3. The Timeline, layer properties, and transforms

1. Select a layer and press **U** to reveal every property on it that has
   been changed from its default (useful once keyframes are added later);
   press **U U** (twice, quickly) to reveal every animatable property that
   has *any* non-default value including expressions.
2. Twirl open a layer's **Transform** group (the arrow to its left, or
   press the shortcut for a single property):
   - **P** — Position
   - **S** — Scale
   - **R** — Rotation
   - **T** — Opacity
   - **A** — Anchor Point
3. Change a value by dragging its blue numeric label left/right (a
   "scrubby slider"), or click the number to type an exact value.
4. Move the **Current Time Indicator** (the blue playhead) along the
   Timeline ruler, or press **Page Up / Page Down** to step one frame at a
   time, and the **Spacebar** to preview playback (RAM Preview via the
   numpad **0** key for full-speed audio+video preview).

## 4. Text and shape layers

1. **Layer > New > Text** (or select the **Type tool** and click in the
   Composition panel) to add a text layer; type directly, then style it in
   the **Character** panel (**Window > Character**) and align it with the
   **Align** panel (**Window > Align**).
2. **Layer > New > Shape Layer** creates an empty shape layer; with the
   **Pen**, **Rectangle**, or **Ellipse** tool selected, draw directly into
   the Composition panel — each shape becomes a **Path** inside the shape
   layer's **Contents** group, with its own **Fill** and **Stroke**.
3. Both text and shape layers are fully vector and resolution-independent,
   so scaling them up in Scale doesn't lose quality the way a raster image
   layer would.

## 5. Parenting layers

1. In the Timeline, use each layer's **Parent & Link** column (enable it
   via the panel menu if hidden, or right-click the column headers >
   **Columns > Parent & Link**) and pick another layer from the pick-whip
   dropdown, or drag the spiral pick-whip icon onto the target layer.
2. Once parented, moving, scaling, or rotating the parent layer carries the
   child along with it, while the child's own Transform values stay
   relative to the parent — the same logic as grouping in Illustrator, but
   live and animatable.

## Worked example: an animated title card

1. New composition, 1920x1080, 25fps, 5 seconds, named `Title_Card`.
2. Add a shape layer: a full-frame rectangle filled with your brand color
   as a background.
3. Add a text layer with the campaign headline, styled in Character panel
   (typeface, size, tracking) to match the brand system from earlier
   levels.
4. Add a small logo (imported as a Photoshop/Illustrator layer) and parent
   it to the text layer so both move together.
5. Set Position on the text+logo group to start off-frame to the left,
   scrub the playhead to 1 second, and note the target on-frame position —
   this sets up the keyframed move covered in Module 2.

## Cheat sheet — After Effects basics

| Task | Where |
|---|---|
| New composition | Composition > New Composition (Ctrl/Cmd+N) |
| Import footage | File > Import > File... (Ctrl/Cmd+I) |
| Reveal changed properties | Select layer, press U |
| Position / Scale / Rotation / Opacity shortcuts | P / S / R / T |
| RAM Preview | Numpad 0 |
| Parent a layer | Parent & Link column, pick-whip |
| New Shape / Text layer | Layer > New > Shape Layer / Text |

## How It Actually Works

- **A project references footage by file path, not by embedding it**, which
  is the mechanical reason moving or renaming a source file produces a
  "missing footage" error rather than silently continuing to work — the
  `.aep` project file stores a pointer (path + a checksum/metadata for
  verification) to each imported asset, and every layer built from that
  footage item resolves through the same pointer at render time. Keeping a
  stable folder structure from the start isn't a style preference; it's
  avoiding invalidating every one of those stored paths at once.
  
- **Transform properties are stored per-layer as independent numeric
  channels (Position, Scale, Rotation, Opacity, Anchor Point), evaluated
  fresh at every frame** — which is exactly why "revealing" a property with
  P/S/R/T doesn't compute anything, it just displays a channel that already
  exists on every layer by default (at rest values: 0% rotation, 100%
  scale, full opacity). Keyframing one later is simply telling that same
  channel to hold different values over time instead of one constant value.

- **The Anchor Point is the origin every other transform is computed
  relative to, not just a visual dot.** Position places the anchor point at
  a location in the composition; Scale and Rotation both pivot around that
  same point. Two identical-looking layers with the anchor point set at
  their center versus at a corner will rotate completely differently under
  the exact same Rotation keyframes — the visual shape doesn't change, but
  the coordinate space the transform math operates in does.

- **Text and shape layers stay resolution-independent because their
  content is Bézier path and glyph-outline data evaluated at render
  resolution, the same underlying math as Illustrator paths and OpenType
  glyphs from earlier levels** — After Effects rasterizes them fresh at
  whatever pixel dimensions the current composition and Scale value
  require, rather than scaling a pre-rendered bitmap the way an imported
  raster image layer must.

- **Parenting works by making a child layer's transform properties relative
  to its parent's *resolved* transform matrix instead of the composition's
  absolute coordinate space.** Internally, After Effects computes the
  parent's full transform for the current frame, then applies the child's
  own Position/Scale/Rotation values on top of that as an offset — which is
  why moving the parent moves the child (the child's absolute position is
  recomputed through the parent's matrix every frame) while the child's own
  keyframed animation still plays out normally in that now-shifted local
  space, rather than being overwritten by the parent's motion.

## Exercise

Build the animated title card above end to end: a full-frame background
shape, a styled headline text layer, and a parented logo. Confirm the
composition settings (resolution, frame rate, duration) match a realistic
delivery target, and that moving the background layer does not move the
text/logo group (they should only move together via the logo's own
parenting to the text, not the background).
