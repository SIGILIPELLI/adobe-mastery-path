# 06 · Photoshop Compositing & Retouching

Where Module 2 covered Photoshop's basic mechanics, this module covers the
techniques that make Photoshop work feel professional: **layer masks** for
non-destructive hiding/revealing, **adjustment layers** for editable color
correction, and the **Healing Brush**/**Clone Stamp** for removing
blemishes or unwanted objects from a photo.

## 1. Layer masks

A **layer mask** hides parts of a layer without deleting any pixels —
painting black on the mask hides, white reveals, and gray partially hides.
This is the non-destructive alternative to erasing or deleting pixels
outright, and it's reversible at any point later.

1. Select a layer, then click the **Add Layer Mask** icon at the bottom of
   the Layers panel (a rectangle with a circle) — a white mask thumbnail
   appears next to the layer, meaning nothing is hidden yet.
2. Press **B** for the Brush tool. Press **D** to reset colors to default
   (black/white), then **X** to swap which one is currently active.
3. With the mask thumbnail selected (click it once to make sure it's
   targeted, not the layer image itself) and black as your foreground
   color, paint over the canvas — the painted area becomes transparent,
   revealing whatever is on the layer below.
4. Press **X** to swap to white and paint back over any area you hid by
   mistake — masks are fully reversible as long as you keep painting on the
   mask rather than the pixels.
5. A common use: place a background photo above a solid-color layer, add a
   mask to the photo layer, and paint black around a subject to reveal the
   solid color behind them — a simple manual cutout, without ever deleting
   a pixel from the original photo.

!!! info "Selection-to-mask shortcut"
    If you already have an active selection (Module 2), clicking **Add
    Layer Mask** converts that selection directly into a mask — everything
    outside the selection is hidden immediately, instead of hand-painting.

## 2. Adjustment layers

An **adjustment layer** applies a color/tone edit (brightness, hue,
levels, curves, and more) to everything beneath it in the stack, without
altering any pixels directly — like a mask, it's fully editable and
reversible at any time.

1. Click the **half-filled circle icon** at the bottom of the Layers panel
   (or **Layer > New Adjustment Layer**) and choose a type — **Brightness/
   Contrast**, **Hue/Saturation**, and **Curves** cover most everyday needs.
2. The adjustment appears as its own layer with a mask already attached.
   Double-click its thumbnail at any time to reopen its settings in the
   **Properties panel** and tweak the values further.
3. Because it has a mask automatically, you can paint black on that mask
   (same technique as above) to exclude specific areas from the
   adjustment — e.g. brightening a subject's face without affecting the
   background.
4. Adjustment layers only affect layers **below** them in the stack — drag
   one up or down in the panel to change what it applies to.
5. To constrain an adjustment to just the single layer directly beneath it
   (instead of everything below), click the **clip to layer** icon between
   the adjustment layer and the one below it in the Layers panel (or
   **Layer > Create Clipping Mask**, ⌥/Alt+⌘/Ctrl+G).

## 3. Healing Brush and Clone Stamp

Both tools sample pixels from one part of an image and paint them
elsewhere, but they behave differently — knowing when to use which one
matters.

1. **Clone Stamp** (**S**) — Option/Alt-click a source point, then paint
   elsewhere to stamp an exact copy of the sampled area, pixel for pixel.
   Good for duplicating a distinct object or pattern.
2. **Spot Healing Brush** (**J**, then Shift+J to cycle to plain **Healing
   Brush** if needed) — just paint directly over a blemish with no separate
   sampling step; Photoshop automatically samples nearby texture and blends
   the edges, lighting, and texture to match the surrounding area. This is
   the faster, more automatic tool for small blemishes (a spot, a scratch,
   a stray hair).
3. **Healing Brush** (Shift+J to cycle from Spot Healing Brush) — like Clone
   Stamp, requires an Option/Alt-click to set a source point first, but
   then blends the sampled texture into the destination's lighting and
   tone rather than pasting it exactly — better than Clone Stamp when
   source and destination lighting differ slightly.
4. Work on a **duplicated layer** (⌘/Ctrl+J) rather than the original so
   retouching stays non-destructive and reversible by simply toggling or
   deleting that layer.

## 4. A basic retouching workflow, end to end

1. Open a photo and duplicate its layer (⌘/Ctrl+J) — always retouch on the
   copy.
2. Use the **Spot Healing Brush** to remove small blemishes or distracting
   specks first — it's fast and usually needs no further adjustment.
3. Use the **Healing Brush** or **Clone Stamp** for larger unwanted objects
   or areas, sampling from nearby similar texture (e.g. clear skin, plain
   background) so the blend looks natural.
4. Add a **Curves** or **Hue/Saturation** adjustment layer above the
   retouched layer to correct overall color/tone — mask out any area (like
   the eyes, if you brightened the whole face) where the adjustment
   shouldn't apply.
5. Add a **layer mask** to the retouched layer itself if you want to blend
   it back with an untouched version underneath at partial strength, for a
   more natural, less "overworked" result.
6. Flatten only your final export copy (**Image > Flatten Image**, or just
   export via **Export As**, Module 2) — never flatten your working `.psd`,
   so every mask and adjustment stays editable if you need to revisit it.

## Cheat sheet

| Tool/Action | Shortcut |
|---|---|
| Add layer mask | Layers panel > Add Layer Mask icon |
| Brush tool | B |
| Reset colors to black/white | D |
| Swap foreground/background color | X |
| Add adjustment layer | Layers panel > half-filled circle icon |
| Clip adjustment to layer below | ⌥/Alt+⌘/Ctrl+G |
| Duplicate layer | ⌘/Ctrl+J |
| Clone Stamp tool | S |
| Spot Healing Brush | J |
| Cycle to Healing Brush | Shift+J |
| Flatten image (final export copy only) | Image > Flatten Image |

## Exercise

Open any photo (a selfie, a product photo, or a downloaded stock image).
Duplicate the layer and use the Spot Healing Brush to remove at least one
blemish or distraction. Add a Curves adjustment layer to improve overall
contrast, masking it so it only affects part of the image. Finally, add a
layer mask to the retouched layer and paint at 50% gray to partially blend
the retouch back with the original underneath it. Export the result as a
JPG.
