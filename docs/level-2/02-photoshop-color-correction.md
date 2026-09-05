# 02 · Photoshop Color Correction & Grading

Level 1's Curves/Hue-Saturation adjustment layers (Module 6) covered quick,
everyday fixes. This module goes deeper into deliberate color work:
reading and shaping a **Curves** adjustment precisely, correcting cast with
**Color Balance**, and grading a shot wholesale with the **Camera Raw
Filter** — the same engine Lightroom uses, available directly inside
Photoshop.

## 1. Curves, precisely

Curves (Level 1 introduced it as one option among several) is worth
understanding in real depth — it's the single most flexible tonal tool in
Photoshop.

1. Add a **Curves** adjustment layer (**Layer > New Adjustment Layer >
   Curves**, or the half-filled circle icon in the Layers panel). The graph
   shows input (x-axis, original tones) against output (y-axis, adjusted
   tones), running from black (bottom-left) to white (top-right).
2. Click anywhere on the diagonal line to add a control point, then drag it
   up (brightens that tonal range) or down (darkens it).
3. An **S-curve** — one point pulled slightly down in the shadows, another
   pulled slightly up in the highlights — is the classic contrast boost:
   deepens blacks and brightens whites while leaving midtones roughly
   alone.
4. Use the **on-image adjustment tool** (the hand icon with arrows at the
   Curves panel's top-left) to click directly on the photo and drag up/down
   — Photoshop places a matching point on the curve at that exact tonal
   value automatically, useful when you know which part of the photo needs
   adjusting but not its numeric value.
5. Switch the channel dropdown (top of the panel, default **RGB**) to
   **Red**, **Green**, or **Blue** individually to correct a color cast —
   e.g. pulling the Blue channel's curve down in the shadows removes a blue
   tint from dark areas without touching brightness overall.
6. Reset any curve to its default diagonal by holding **Option/Alt** and
   clicking **Reset** in the Properties panel, or by deleting individual
   points (select a point, press **Delete**).

## 2. Color Balance

**Color Balance** targets color cast per tonal range in a simpler,
slider-based way than Curves' per-channel curves — a faster tool once you
know roughly what's wrong.

1. Add a **Color Balance** adjustment layer (**Layer > New Adjustment
   Layer > Color Balance**).
2. Choose a **Tone** range at the top of the Properties panel — **Shadows**,
   **Midtones**, or **Highlights** — and drag the three sliders
   (Cyan–Red, Magenta–Green, Yellow–Blue) toward whichever color is missing.
3. A common real-world fix: a photo shot under indoor tungsten lighting
   looks too orange/yellow overall — select **Midtones**, drag the
   Yellow–Blue slider toward Blue, and the Cyan–Red slider slightly toward
   Cyan, to neutralize it.
4. Check **Preserve Luminosity** (checkbox at the bottom) to keep overall
   brightness unchanged while only shifting color — usually worth leaving
   on so a color fix doesn't also brighten or darken the image as a side
   effect.
5. Correct shadows, midtones, and highlights as three separate light passes
   rather than trying to fix everything with one slider drag — most real
   color casts aren't uniform across the whole tonal range.

## 3. Camera Raw Filter

The **Camera Raw Filter** brings Lightroom's full adjustment engine into
Photoshop as a filter, applying its own complete panel of controls in one
place rather than stacking several separate adjustment layers.

1. Select a layer (convert it to a **Smart Object** first, Module 1, so the
   filter stays editable as a Smart Filter afterward) and choose **Filter >
   Camera Raw Filter** (**Shift+⌘/Ctrl+A**).
2. The **Basic** panel covers the most common moves top to bottom:
   **Exposure** (overall brightness), **Contrast**, **Highlights**/
   **Shadows** (recover detail at each end independently), **Whites**/
   **Blacks** (set the actual clipping points), **Texture**, **Clarity**
   (midtone contrast/punch), **Dehaze** (cuts through atmospheric haze), and
   **Vibrance**/**Saturation** (Vibrance boosts muted colors more than
   already-saturated ones, giving a more natural result than Saturation's
   flat boost).
3. The **Curve** tab gives the same point-curve control as Photoshop's own
   Curves, inside the same dialog.
4. The **Color Mixer** tab (HSL-style) adjusts Hue, Saturation, and
   Luminance per individual color range (e.g. push just the oranges more
   saturated for skin tones without affecting blues in the sky).
5. **Color Grading** applies the "wheels" look familiar from video grading —
   separate color wheels for Shadows, Midtones, and Highlights, each with
   its own Hue and Saturation control, good for a cohesive stylized look
   across a whole batch of photos.
6. Click **OK** to apply. On a Smart Object, the result appears as an
   editable **Camera Raw Filter** Smart Filter beneath the layer — double-
   click its name any time to reopen and adjust every setting again.

!!! info "Camera Raw Filter vs. adjustment layers"
    Camera Raw Filter bakes its settings into one Smart Filter entry rather
    than separate adjustment layers, which makes it faster to apply a
    consistent full grade to many photos, but harder to mask different
    settings to different areas independently. For that kind of localized
    control, separate adjustment layers with masks (Level 1, Module 6) are
    still the better tool — the two approaches are complementary, not
    competing.

## 4. A full grading workflow, end to end

1. Convert the photo layer to a **Smart Object** first (Module 1) so every
   step below stays editable.
2. Apply **Camera Raw Filter** for the broad first pass — Exposure,
   Contrast, Highlights/Shadows recovery, and a Color Grading wheel tweak
   for overall mood.
3. Add a **Curves** adjustment layer above it for a final contrast S-curve
   and any per-channel cast correction the Camera Raw pass didn't fully fix.
4. Add a **Color Balance** adjustment layer if a specific tonal range
   (often shadows) still reads slightly off after Curves.
5. Mask any adjustment layer (Level 1, Module 6) that shouldn't apply
   everywhere — e.g. excluding a subject's face from a shadows-heavy mood
   grade meant for the background.

## Cheat sheet

| Tool | Best for |
|---|---|
| Curves | Precise per-channel tonal and color cast control |
| Color Balance | Fast, slider-based cast correction per tonal range |
| Camera Raw Filter | Full one-pass grade: exposure, color wheels, HSL mixer |
| Vibrance (in Camera Raw) | Natural saturation boost, protects skin tones |
| Saturation (in Camera Raw) | Flat, uniform saturation boost — easy to overdo |

| Action | Shortcut |
|---|---|
| Open Camera Raw Filter | Shift+⌘/Ctrl+A |
| New Curves adjustment layer | Layer > New Adjustment Layer > Curves |
| New Color Balance adjustment layer | Layer > New Adjustment Layer > Color Balance |
| On-image Curves adjustment tool | Curves Properties panel, top-left hand icon |
| Convert layer to Smart Object first | Layer > Smart Objects > Convert to Smart Object |

## How It Actually Works

- **A curve is a remapping function applied per input tone value, not a
  freehand paint stroke.** Every point you place defines a coordinate on an
  input→output mapping; Photoshop interpolates a smooth spline through all
  placed points and applies the resulting function to every pixel whose
  original value falls along that curve — a pixel at input value 128 simply
  looks up what output value the curve currently assigns to 128. That's why
  an S-curve boosts contrast without an explicit "increase contrast"
  operation: pulling shadows down and highlights up is literally
  remapping dark input values to darker outputs and light input values to
  lighter outputs, while midtones near the curve's unmoved center stay
  close to their original value.
- **Per-channel curves work because a color image is three independent
  numeric planes.** Selecting the Blue channel and pulling its shadow region
  down doesn't touch Red or Green at all — it remaps only the blue
  component of every pixel below a certain blue value. A blue-tinted
  shadow has an elevated blue value relative to red/green at that
  brightness; lowering just blue's curve there brings the three channels
  back into closer balance without an explicit "remove blue cast"
  operation — you're just applying arithmetic to one plane of the data.
- **Vibrance and Saturation use different weighting formulas on the same
  underlying data, which is the entire reason they look different.**
  Saturation applies a uniform multiplier to every pixel's saturation value
  regardless of how saturated it already is. Vibrance's algorithm
  weights that multiplier inversely to existing saturation — it boosts
  low-saturation pixels much more than already-saturated ones, and further
  applies extra damping specifically in skin-tone hue ranges. This is a
  deliberate, hardcoded protection in Adobe's Vibrance implementation, not
  an emergent side effect — it's why Vibrance is the safer default for
  photos with faces.
- **Camera Raw Filter and separate adjustment layers apply changes at
  different points in the same rendering pipeline.** Camera Raw operates on
  the Smart Object's source data through a single unified processing
  pipeline (demosaic-equivalent tone/color math, done once, in one pass)
  before Photoshop's normal layer-compositing engine ever runs, which is why
  it's efficient for a full-image grade but only exposes one mask for the
  whole filter. Adjustment layers instead operate at the Photoshop
  compositing stage itself, each with its own independent mask evaluated
  per-pixel during the same top-down compositing walk covered in earlier
  modules — that's the structural reason stacking several masked adjustment
  layers gives you localized control that one Camera Raw pass structurally
  cannot.
- **"Preserve Luminosity" in Color Balance works by converting to a
  luminance-preserving color model before and after the shift.** Internally,
  Photoshop measures the pixel's luminance value before applying the
  Cyan-Red/Magenta-Green/Yellow-Blue shifts, then rescales the resulting RGB
  values after the shift so the same luminance value is reproduced — this
  is a real corrective calculation each time, not a checkbox that merely
  limits how far you can drag the sliders.

## Exercise

Open a photo with a visible color cast (indoor tungsten lighting or an
overcast/blue-toned shot both work well). Convert its layer to a Smart
Object, apply the Camera Raw Filter for a broad exposure and color-wheel
correction, then add a Curves adjustment layer on top for a final S-curve
contrast boost. If any cast remains in just the shadows or midtones, add a
Color Balance adjustment layer targeted at that tonal range. Mask at least
one adjustment so it doesn't apply to the whole image.
