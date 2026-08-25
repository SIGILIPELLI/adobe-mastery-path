# 06 · Lightroom Classic Develop Module & Color Grading

With a shoot imported and organized (Module 5), this module covers the
**Develop** module — Lightroom's non-destructive raw processing and color
grading toolset — from basic tonal correction through to the Color Grading
panel and syncing a look across a whole set.

## 1. Entering Develop and the basic panel

1. Select a photo and press **D** to enter the **Develop** module (or
   double-click a thumbnail in Grid view). The right panel stack holds
   every adjustment tool, top to bottom in a roughly recommended order.
2. **Basic** panel — the primary tonal controls:
   - **White Balance**: Temp/Tint sliders, or the **White Balance
     Selector** (eyedropper) to click a neutral gray/white point in the
     image.
   - **Tone**: Exposure, Contrast, Highlights, Shadows, Whites, Blacks —
     drag or double-click a slider to reset it to default.
   - **Presence**: Texture, Clarity (midtone contrast/definition),
     Dehaze, Vibrance, Saturation.
3. Every adjustment here is non-destructive — it's stored as an edit
   instruction in the catalog, never baked into the original file, and
   fully reversible via the **History** panel (left side) at any time.

## 2. Tone Curve and HSL/Color panels

1. **Tone Curve** panel — refine contrast beyond the Basic sliders by
   dragging points on the curve, or switch to **Point Curve** mode for
   direct control over specific tonal regions (shadows/darks/lights/
   highlights via the four-region sliders in the simpler view).
2. **HSL / Color** panel — adjust **Hue**, **Saturation**, and
   **Luminance** per individual color channel (Red, Orange, Yellow, Green,
   Aqua, Blue, Purple, Magenta) — e.g. pull Orange Saturation down to tame
   an overly warm skin tone without touching any other color.
3. Use the **targeted adjustment tool** (the small circle icon at the top-
   left of the HSL panel) to click-drag directly on the photo — Lightroom
   automatically adjusts whichever color channel is under the cursor.

## 3. Color Grading panel (three-way color wheels)

1. The **Color Grading** panel provides three color wheels — **Shadows**,
   **Midtones**, **Highlights** — each with a hue/saturation wheel and a
   separate **Luminance** slider beneath it.
2. Drag the small dot within a wheel away from center to tint that tonal
   range toward a hue (e.g. teal into shadows, warm orange into highlights
   — the well-known "teal and orange" cinematic look, built from exactly
   this kind of split-toning).
3. The **Blending** and **Balance** sliders at the bottom control how much
   the three ranges overlap and where the midpoint sits, smoothing
   transitions between the shadow/midtone/highlight zones so the grade
   doesn't band or look artificially split.

## 4. Local adjustments: masking

1. The **Masking** panel (top toolbar, mask icon, or press **M**) replaced
   the older individual local-adjustment tool icons with a unified panel
   offering: **Select Subject**, **Select Sky**, **Select Background**,
   **Brush**, **Linear Gradient**, **Radial Gradient**, and **Color/Luminance
   Range** masks, plus **Select People** with per-feature options (skin,
   face, hair, etc.).
2. Click **Create New Mask**, choose a type (e.g. **Select Sky** for a
   product/landscape shoot), and Lightroom generates an AI-based selection
   automatically — a full set of Basic-panel-style sliders then appears,
   scoped only to that masked area.
3. Stack multiple masks (each appears as its own entry in the panel) to
   build up a full local edit — e.g. a Sky mask to darken/tint a background,
   plus a Subject mask to lift exposure and clarity, without affecting the
   rest of the frame.

## 5. Syncing edits and presets across a set

1. Edit one representative "hero" photo fully, then in Grid view select it
   plus every other photo it should match, click **Sync Settings...**
   (bottom of the right panel in Develop, or **Sync** button), and check
   only the categories to copy (e.g. Basic, Tone Curve, Color Grading, but
   not Crop if framing varies).
2. Alternatively, save a finished edit as a reusable **Preset**: **+** icon
   at the top of the **Presets** panel (left side) > **Create Preset...**,
   name it, choose which settings it includes, and apply it to any future
   photo in one click from the Presets panel.
3. **Copy/Paste Settings** (**Ctrl/Cmd+Shift+C** / **Ctrl/Cmd+Shift+V**) is
   the fastest one-off way to apply one photo's full edit (or a chosen
   subset) to a single other photo without opening the Sync dialog.

## Worked example: grading the product shoot

1. Open the 5-star hero shot from Module 5's `Selects` collection in
   Develop.
2. Set white balance with the eyedropper on a known-neutral surface in the
   product packaging, then dial in Exposure/Contrast/Whites/Blacks in
   Basic until the product reads accurately.
3. Use **Select Subject** masking to lift the product's own exposure and
   Clarity slightly, and a **Select Background** mask to darken/desaturate
   the backdrop so the product stands out.
4. Apply a subtle Color Grading pass: cool tint in Shadows, warm tint in
   Highlights, both kept at low saturation for a professional rather than
   stylized look.
5. Save the finished look as a Preset named `Product Shoot House Grade`,
   then select the rest of the Selects collection and apply the preset to
   every shot for a consistent set.

## Cheat sheet — Develop & color grading

| Task | Where / shortcut |
|---|---|
| Enter Develop | D |
| Basic tonal controls | Basic panel |
| Per-color hue/sat/luminance | HSL / Color panel |
| Three-way split toning | Color Grading panel |
| AI subject/sky/people selection masks | Masking panel (M) |
| Copy one edit to many selected photos | Sync Settings... |
| Reusable one-click look | Presets panel > + > Create Preset... |
| Quick one-off copy | Ctrl/Cmd+Shift+C / +Shift+V |

## Exercise

Fully grade one hero photo using Basic, HSL, Color Grading, and at least
one Masking-panel local adjustment (Select Subject or Select Sky). Save it
as a named Preset and apply it to the rest of the set via either Sync
Settings or the Presets panel, confirming every photo in the set now shares
the same white balance and color grade.
