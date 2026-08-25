# 03 · After Effects Compositing & Effects

With motion and easing in place, this module covers **compositing** — how
multiple layers combine into one convincing image — and the Effects
pipeline that adds looks, corrections, and generated visuals on top.
This is After Effects' equivalent of Photoshop's blend modes and layer
masks, extended across time.

## 1. Blend modes and track mattes

1. Reveal the **Modes** column in the Timeline (panel menu > **Columns >
   Modes**, or press **F4** to toggle between the Switches and Modes
   columns) and choose a blend mode from a layer's dropdown — **Screen**,
   **Multiply**, **Add**, and **Overlay** behave the same as their
   Photoshop counterparts.
2. For a **track matte**, place the matte shape/text layer directly above
   the layer it should mask, then on the layer *below* it, use the **Track
   Matte** dropdown (also in the Modes columns area) and choose **Alpha
   Matte "[layer above]"** (mask by the matte layer's alpha/transparency)
   or **Luma Matte "[layer above]"** (mask by its brightness).
3. The matte layer's own visibility eye can be turned off once it's set as
   a track matte source in most workflows, but leave it on while setting
   up so you can see what you're aligning.

## 2. Masks

1. With a layer selected, draw directly on it in the Composition panel
   using the **Pen tool**, or select the layer and draw a shape with the
   **Rectangle/Ellipse** tool while the layer (not a new shape layer) is
   selected — this creates a **Mask** on that layer instead of a new shape.
2. Twirl open the layer's **Masks** property group to adjust **Mask Path**
   (animatable, for a moving matte), **Mask Feather** (soft edge),
   **Mask Opacity**, and **Mask Expansion**.
3. Set **Mask Mode** (Add, Subtract, Intersect, etc., in the Timeline's
   Modes area for that mask) to combine multiple masks on one layer, the
   same logic as Photoshop's mask calculations.

## 3. The Effects & Presets panel

1. **Window > Effects & Presets** opens the searchable effects browser.
   Drag any effect directly onto a layer in the Timeline or Composition
   panel to apply it.
2. Applied effects appear in the **Effect Controls** panel (**Window >
   Effect Controls**, or double-click the layer) with their own
   parameters — every parameter here can be keyframed exactly like a
   Transform property.
3. Common corrective/stylistic effects to know: **Lumetri Color** (the
   same color grading engine as Premiere, usable here for consistency
   across a pipeline), **Gaussian Blur**, **Curves**, **Hue/Saturation**,
   and **CC Light Sweep** or **Glow** for stylized motion graphics accents.
4. Reorder effects by dragging them in the Effect Controls panel — like
   layers, effects apply top-to-bottom, so a Blur above a Curves effect
   produces a different result than the reverse order.

## 4. Adjustment layers and precomps

1. **Layer > New > Adjustment Layer** creates a layer whose effects apply
   to every visible layer beneath it in the stack, without altering any
   individual layer directly — the AE equivalent of a Photoshop adjustment
   layer, but effects-based rather than tonal-adjustment-only.
2. To treat a group of layers as a single unit (for a shared effect, blend
   mode, or to declutter the Timeline), select them, right-click > **Pre-
   compose...**, choose **Move all attributes into the new composition**,
   and name it — this nests them into a new composition that appears as
   one layer in the parent.
3. Precomping is the AE equivalent of grouping in Illustrator/Photoshop:
   it isolates a set of layers so effects, blend modes, and masks applied
   at the precomp level affect the group as a whole.

## 5. Rendering with alpha for compositing elsewhere

1. **Composition > Add to Render Queue**, then in the **Output Module**
   settings choose a format that supports transparency (e.g. **QuickTime**
   with the **Apple ProRes 4444** codec, or a PNG sequence) and set
   **Channels: RGB + Alpha** so the rendered element carries its
   transparency into Premiere or another app.
2. This is essential for motion graphics elements (lower thirds, animated
   logos) meant to sit over live footage in a later edit rather than stand
   alone.

## Worked example: compositing the title card over footage

1. Import a short background video clip into the `Title_Card` project and
   add it to the Timeline below the text+logo group.
2. Add an **Adjustment Layer** above the background footage only (below
   the text group) with **Lumetri Color** applied to grade the footage to
   match the brand palette.
3. Give the background footage a soft vignette using **Curves** or a
   feathered mask darkening its edges, so the title reads clearly against
   it.
4. Render the text+logo group alone (precomposed) as a ProRes 4444 file
   with alpha, confirming it composites correctly over a different
   background when reopened.

## Cheat sheet — compositing & effects

| Task | Where |
|---|---|
| Show blend mode / track matte columns | F4, or panel menu > Columns > Modes |
| Apply a track matte | Track Matte dropdown on the layer below the matte |
| Draw a mask on a layer | Pen/shape tool with the layer (not new layer) selected |
| Browse/apply effects | Window > Effects & Presets, drag onto layer |
| Adjust applied effect parameters | Window > Effect Controls |
| Adjustment layer | Layer > New > Adjustment Layer |
| Group layers into one unit | Right-click > Pre-compose... |
| Render with transparency | Output Module > Format/Codec supporting alpha, Channels: RGB + Alpha |

## Exercise

Composite the title card over the background footage: grade the footage
with an adjustment layer, mask its edges for a vignette, and confirm the
text+logo group reads clearly on top. Render the text+logo group alone as
a ProRes 4444 (or PNG sequence) file with alpha and verify it drops
cleanly over a different clip when reopened, confirming the alpha channel
survived the render.
