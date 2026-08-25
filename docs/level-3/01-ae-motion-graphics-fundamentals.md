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

## Exercise

Build the animated title card above end to end: a full-frame background
shape, a styled headline text layer, and a parented logo. Confirm the
composition settings (resolution, frame rate, duration) match a realistic
delivery target, and that moving the background layer does not move the
text/logo group (they should only move together via the logo's own
parenting to the text, not the background).
