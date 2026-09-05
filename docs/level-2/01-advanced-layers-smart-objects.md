# 01 · Advanced Layers & Smart Objects (Photoshop)

Level 1 treated a layer as a single sheet in the stack. Real production work
needs more control than that: **Smart Objects** to edit non-destructively
and scale without quality loss, **layer groups** to keep a complex file
navigable, and **blending modes** to combine layers in ways a plain opacity
fade can't. This module covers all three, plus the non-destructive scaling
workflow they enable together.

## 1. Smart Objects

A **Smart Object** wraps a layer's content — a pixel layer, a placed file,
or even a group — in a container that Photoshop treats as a single sealed
unit. Any filter, transform, or scale you apply happens to the *container*,
not the underlying pixels, so the original data is always recoverable.

1. Select one or more layers, then **Layer > Smart Objects > Convert to
   Smart Object** (or right-click the layer(s) in the Layers panel and
   choose the same command). The layer thumbnail changes to show a small
   page icon in its bottom-right corner, marking it as a Smart Object.
2. Double-click the Smart Object's thumbnail to open its contents in a
   separate tab (for a Photoshop-native Smart Object) or the originating
   app (for a Smart Object placed from Illustrator, Module 9 of Level 1).
   Edit and **File > Save**, and the placed instance back in your main
   document updates automatically.
3. **File > Place Embedded** (or **Place Linked**) imports another file
   directly as a Smart Object rather than flattened pixels. **Embedded**
   stores a full copy inside the `.psd`; **Linked** keeps a reference to the
   external file on disk, keeping your `.psd` smaller but dependent on that
   file staying in place.
4. **Layer > Smart Objects > Replace Contents** swaps a placed Smart Object
   for a different source file while preserving any transforms, filters, or
   position you've already applied — useful for swapping a placeholder photo
   for a final one late in a layout.

!!! info "Smart Objects and Smart Filters"
    Any filter (**Filter** menu) applied to a Smart Object layer becomes a
    **Smart Filter**, listed underneath the layer in the Layers panel with
    its own mask. Double-click a Smart Filter's name to reopen and adjust its
    settings later, or paint on its mask to limit where it applies — the
    same non-destructive logic as an adjustment layer's mask (Level 1,
    Module 6).

## 2. Non-destructive scaling

Scaling an ordinary raster layer up and down repeatedly degrades it a little
more each time, because Photoshop resamples the pixels on every transform.
A Smart Object avoids this because Free Transform always scales from the
original embedded (or linked) data, not from the last-resampled result.

1. Convert the layer to a Smart Object first (Section 1).
2. Press **⌘/Ctrl+T** for Free Transform, drag a corner handle to scale, and
   press **Enter/Return** to commit.
3. Scale it back down, then back up again later — because the transform is
   stored as an editable instruction on the container rather than baked
   into pixels, the result looks the same as scaling the original once,
   instead of accumulating blur from repeated resampling.
4. This matters most for placed logos, icons, or any asset you expect to
   resize more than once while a layout is still in progress — exactly the
   kind of asset a Creative Cloud Library shares between files (Level 1,
   Module 9).

## 3. Layer groups

A **layer group** (folder icon in the Layers panel) bundles related layers
so they move, transform, and toggle together.

1. Select multiple layers (Shift-click or ⌘/Ctrl-click each in the panel),
   then **Layer > Group Layers** (**⌘/Ctrl+G**) to bundle them into a new
   group.
2. Double-click the group's name to rename it — do this immediately, the
   same discipline as naming individual layers (Level 1, Module 2).
3. A group's own blend mode defaults to **Pass Through**, meaning layers
   inside interact with everything below the group exactly as if the group
   didn't exist. Change it to any other blend mode (Section 4) to make the
   whole group composite as one flattened unit against the layers beneath
   it — useful once you want a group's combined result to behave as a
   single layer for blending purposes.
4. Nest groups inside groups for deep organization (a "Header" group
   containing a "Logo" group and a "Nav" group, for example) — twirl open
   the disclosure triangle to navigate in without cluttering the top level
   of the panel.
5. Add a layer mask directly to a group (same **Add Layer Mask** icon,
   Level 1 Module 6) to mask everything inside it at once, rather than
   masking each layer individually.

## 4. Blending modes

A **blend mode** changes how a layer's pixels mathematically combine with
everything beneath it, instead of just fading (opacity) or masking (hiding)
it.

1. Select a layer, then choose a mode from the dropdown at the top-left of
   the Layers panel (default: **Normal**).
2. The modes are grouped by what they do to the underlying pixels:
   **Darken** group (Multiply, Darken, Color Burn) only darkens; **Lighten**
   group (Screen, Lighten, Color Dodge) only lightens; **Contrast** group
   (Overlay, Soft Light, Hard Light) darkens dark areas and lightens light
   areas for added punch; **Comparative** group (Difference, Exclusion)
   highlights pixel differences; **Composite** group (Hue, Saturation,
   Color, Luminosity) blends specific color properties only.
3. **Multiply** is the most common starting point for combining a shadow or
   texture layer onto a background — it darkens wherever the layer isn't
   pure white, leaving white areas untouched, so a scanned texture's white
   background effectively disappears.
4. **Screen** is Multiply's opposite — useful for adding light, glow, or
   fire elements onto a photo, since it lightens wherever the layer isn't
   pure black.
5. **Overlay** and **Soft Light** both add contrast/punch by combining
   Multiply and Screen behavior depending on the underlying tone — Soft
   Light is the gentler of the two, a common choice for subtle color
   grading passes.
6. Preview blend modes quickly by selecting a layer and pressing
   **Shift+Plus** or **Shift+Minus** to step through the list without
   opening the dropdown each time.

## 5. Worked example: a light-leak texture composite

1. Open a base photo and a separate light-leak or texture stock image.
   Place the texture above the photo as its own layer.
2. Convert the texture layer to a **Smart Object** (Section 1) so you can
   scale it to fit the frame non-destructively.
3. Set the texture layer's blend mode to **Screen** (Section 4) — the black
   background of the texture disappears, leaving only the bright light
   streaks visible over the photo.
4. Group the texture layer with any duplicate/adjustment layers used to
   tweak its color (**⌘/Ctrl+G**), and add a layer mask to the group to hide
   the effect from areas of the photo where it looks wrong (e.g. across a
   subject's face).
5. Because the texture is a Smart Object inside a masked group, you can
   still resize, reposition, or swap it (**Replace Contents**) at any point
   without redoing the mask or blend mode from scratch.

## Cheat sheet

| Blend mode | Effect |
|---|---|
| Normal | No blending; standard opacity fade only |
| Multiply | Darkens; white becomes transparent |
| Screen | Lightens; black becomes transparent |
| Overlay | Adds contrast; midtone-dependent Multiply/Screen mix |
| Soft Light | Gentler version of Overlay |
| Color Dodge | Strong brightening/glow, high contrast |
| Difference | Shows pixel differences; useful for alignment checks |
| Luminosity | Applies only the layer's brightness values |

| Action | Shortcut |
|---|---|
| Convert to Smart Object | Layer > Smart Objects > Convert to Smart Object |
| Place a file as Smart Object | File > Place Embedded / Place Linked |
| Replace a Smart Object's source | Layer > Smart Objects > Replace Contents |
| Group selected layers | ⌘/Ctrl+G |
| Free Transform | ⌘/Ctrl+T |
| Step through blend modes | Shift+Plus / Shift+Minus |

## How It Actually Works

- **A Smart Object defers rasterization to render time instead of baking it
  in at edit time.** Internally it stores the original embedded (or linked)
  data plus a stack of transform/filter instructions — a scale factor, a
  rotation matrix, a list of Smart Filter parameters — rather than a single
  resampled pixel grid. Every time Photoshop needs to display or export the
  layer, it re-renders from the *original* source data through that
  instruction stack in one pass. That's the actual mechanism behind
  non-destructive scaling: repeatedly changing the scale value just edits a
  number in the instruction stack, so Photoshop always resamples once, from
  full-resolution source, at whatever the final scale ends up being — never
  from an already-resampled intermediate result the way a plain raster
  layer would.
- **A Smart Filter is a per-filter entry in that same instruction stack,
  each with its own mask channel.** Because the filter's parameters are
  stored rather than applied to pixels, reopening a Smart Filter re-invokes
  the filter algorithm with the saved settings against the *current*
  resolved content of the Smart Object — which is why editing the source
  file and re-saving it correctly re-runs every downstream Smart Filter
  automatically, rather than leaving stale filtered pixels behind.
- **A layer group's "Pass Through" blend mode is a flag that skips an
  intermediate compositing step, not a default with no effect.** With Pass
  Through, Photoshop composites each layer inside the group directly against
  whatever is beneath the *group* in the main stack, exactly as if no group
  boundary existed. Any other blend mode forces Photoshop to first
  fully composite the group's contents into an isolated buffer, then blend
  *that flattened buffer* against the layers below using the chosen mode —
  this two-stage versus one-stage compositing is the literal reason a
  group's blend mode is the one property that can change how identical
  contents render.
- **Blend modes are per-channel arithmetic functions evaluated on
  normalized (0-1) pixel values, not visual presets.** Multiply computes
  `base × blend` for each of R, G, and B independently — since any value
  multiplied by 1 (white) stays unchanged and anything multiplied by a
  fraction darkens, white in the blend layer becomes invisible and darker
  values progressively darken the base. Screen is the inverted-space
  version: `1 - (1-base)×(1-blend)`, which is mathematically why it behaves
  as Multiply's mirror image and treats black as the "invisible" value.
  Overlay is a conditional blend that branches per-pixel on whether the base
  value is above or below 0.5, applying Multiply-like or Screen-like
  behavior accordingly — which is exactly why it adds contrast rather than
  uniformly darkening or lightening.
- **The Screen-mode light-leak trick works because near-black source pixels
  evaluate to almost zero contribution in that formula** — not because
  Photoshop is doing any special-case "remove black background" operation.
  Any texture authored with a true black background will disappear under
  Screen for the same underlying arithmetic reason, which is also why a
  texture with a dark-gray-not-black background leaves a faint visible haze
  instead of fully vanishing.

## Exercise

Build a two-layer composite: a base photo and a texture or graphic overlay.
Convert the overlay to a Smart Object, scale it up and back down twice using
Free Transform to confirm it stays sharp, then set its blend mode to Screen
or Multiply (whichever suits the image). Group the overlay with a
supporting adjustment layer, add a mask to the group to limit where the
effect shows, and confirm you can still double-click the Smart Object to
edit its source content afterward.
