# 07 · Premiere Advanced Color Grading (Lumetri Scopes)

Level 1 covered basic Lumetri color correction by eye. Professional
grading relies on **scopes** — objective visual readouts of a shot's
brightness and color values — so a grade is measurably consistent across
every clip in a sequence rather than judged purely by how a monitor
happens to be calibrated that day. This module covers reading scopes and
building a full primary + secondary grade in Lumetri Color.

## 1. Opening and reading the Lumetri Scopes panel

1. **Window > Lumetri Scopes** opens the scopes panel; its own panel menu
   (wrench/hamburger icon) lets you choose which scope(s) display —
   commonly **Waveform (Luma)**, **Vectorscope (YUV)**, and **RGB
   Parade** together.
2. **Waveform (Luma)** plots brightness (0-100 IRE roughly) across the
   frame's horizontal position — use it to check exposure objectively:
   clipped highlights bunch at the top (100), crushed shadows bunch at the
   bottom (0), neither of which usually holds recoverable detail.
3. **RGB Parade** shows the same waveform split into separate Red, Green,
   and Blue channels side by side — use it to spot a color cast: if
   shadows/midtones/highlights aren't roughly level across all three
   channels, there's a tint (e.g. blue trailing higher than red/green in
   shadows means a cool cast there).
4. **Vectorscope (YUV)** plots color hue and saturation on a circular
   graph with labeled targets for skin tone (the "skin tone line" running
   near the R-YL segment) — use it to check skin tones read naturally and
   that overall saturation doesn't push points near the scope's outer edge
   (a common oversaturation warning sign).

## 2. Building a primary grade in Lumetri Color

1. **Basic Correction**: apply an **Input LUT** first if the footage is
   log/flat (per Level 4 Module 3), set **White Balance** using the
   eyedropper on a known neutral, then adjust **Exposure, Contrast,
   Highlights, Shadows, Whites, Blacks** referencing the Waveform as you
   go rather than only the monitor image.
2. **Color Wheels & Match**: the three wheels (**Shadows, Midtones,
   Highlights**) each combine a color balance ring with a lift/gamma/gain
   style brightness control beneath — drag the center point off-axis to
   introduce a tint per tonal range (the same split-tone logic as
   Lightroom's Color Grading panel from Level 3).
3. **Curves**: the **RGB Curves** tab allows per-channel adjustment for
   fine control beyond the wheels; **Hue Saturation Curves** lets you
   target a specific hue range (e.g. desaturate just the greens in a
   background) without a full secondary mask.

## 3. Secondary corrections: HSL Secondary and masks

1. **HSL Secondary** panel: use the **eyedropper (Set Color)** and its
   **+/-** add/subtract eyedroppers to sample a specific color range (e.g.
   a product's packaging color), fine-tune the **H, S, L** range sliders,
   and check the **Color/Gray** matte preview toggle to see exactly what's
   selected before adjusting it.
2. Apply a correction only to the selected range using the wheels/sliders
   at the bottom of the HSL Secondary panel — e.g. boost saturation on
   just a logo's color without affecting skin tones or background
   elsewhere in frame.
3. **Masks** (the mask icons at the top of any Lumetri effect fixture, or
   Effect Controls > Opacity > Create Ellipse/4-point/Freeform mask) apply
   a correction to a specific spatial region instead of a color range —
   e.g. a vignette mask darkening the frame's edges, or a mask isolating a
   window to fix a blown-out sky separately from the interior exposure.

## 4. Matching shots across a sequence

1. Select a graded reference clip's Lumetri effect, then with a second
   clip selected, use **Lumetri Color > Color Match** — flip through the
   comparison view and click **Apply Match** to auto-approximate the
   reference grade's tone/color onto the new clip as a starting point.
2. For more controlled consistency, **copy/paste the Lumetri effect**
   itself (select the graded clip, **Edit > Copy**, select target clip(s),
   **Edit > Paste Attributes**, checking only Video Effects) to apply an
   identical grade rather than an approximate match.
3. Check matched shots side by side using **Window > Reference Monitor**
   pinned to a specific frame while scrubbing the main sequence, or by
   temporarily placing two clips adjacent on the timeline and stepping
   frame by frame across the cut.

## 5. Creative looks and LUTs

1. **Creative** tab in Lumetri Color offers built-in look presets plus
   **Faded Film**, **Sharpen**, and **Vibrance** controls layered on top of
   the primary grade — treat it as a finishing pass, applied after
   exposure/color balance are already correct.
2. Export a finished grade as a shareable **.cube LUT**: Lumetri Color
   panel menu > **Export .cube...**, so the same look can be applied
   consistently to other projects or handed to a colorist/other editor as
   a starting point.

## Worked example: grading an interview + b-roll sequence

1. Grade the primary interview shot first using Basic Correction plus
   Color Wheels, checking Waveform for correct exposure and the
   Vectorscope's skin tone line for natural skin color.
2. Use HSL Secondary to isolate and slightly desaturate a distracting
   colored object in the background without affecting the subject.
3. Copy the finished Lumetri effect onto every other angle of the same
   interview setup (identical lighting) via Paste Attributes, and use
   Color Match plus manual RGB Parade checks for b-roll shot in different
   lighting, since a straight copy won't correct for a different exposure
   or white balance on its own.

## Cheat sheet — Lumetri scopes & grading

| Task | Where |
|---|---|
| Open scopes | Window > Lumetri Scopes |
| Check exposure objectively | Waveform (Luma) |
| Check per-channel color cast | RGB Parade |
| Check hue/saturation/skin tone | Vectorscope (YUV) |
| Isolate a color range for correction | Lumetri Color > HSL Secondary |
| Isolate a spatial region for correction | Lumetri Color mask icons |
| Auto-approximate a grade onto another clip | Color Match |
| Apply an identical grade to other clips | Copy clip > Edit > Paste Attributes (Video Effects) |
| Export a shareable grade | Lumetri panel menu > Export .cube... |

## How It Actually Works

- **A Waveform is a direct, objective plot of luma values sampled across
  every horizontal pixel column, which is exactly why it's trustworthy
  when a monitor isn't.** For each horizontal position in the frame, the
  scope plots every pixel in that column's vertical line at a height
  corresponding to its brightness value — a monitor's own calibration,
  brightness, or ambient-light viewing conditions can make identical pixel
  data look brighter or dimmer to your eyes, but the Waveform is reading
  the actual numeric luma values directly, unaffected by any display's
  rendering of them. That's the whole reason professional grading trusts
  scopes over "how it looks on my screen right now."
- **RGB Parade plots the identical waveform computation three times, once
  per color channel, which is precisely why a level mismatch between the
  three plots reveals a color cast mathematically rather than by
  perception.** A true neutral gray or white object has equal R, G, and B
  values; if the same tonal region's red trace sits measurably higher than
  its blue trace, that's a direct numeric imbalance between channels at
  that brightness level — a tint — read straight off the data, the same
  underlying insight as checking a Curves per-channel graph in Photoshop
  but visualized as a live per-pixel plot instead of an editable function.
- **The Vectorscope plots each pixel's hue as an angle and its saturation
  as a radius from center, derived from converting RGB to a hue/saturation
  color model per pixel and accumulating those points into a density
  plot.** The skin-tone line is a fixed angle on that wheel corresponding
  to the hue range human skin reliably falls near across a wide range of
  actual skin tones and lighting — checking that skin-toned pixels cluster
  along that line is checking a real mathematical property of the color
  data, not an aesthetic judgment call.
- **HSL Secondary isolates a color range by converting every pixel to
  Hue/Saturation/Luminance and testing whether each falls inside the
  ranges you've set, producing a per-pixel mask exactly like a Photoshop
  luminance mask or a Lightroom color-range mask** — the Color/Gray matte
  preview is literally displaying that computed mask (white = fully
  selected, black = fully excluded, gray = partial) so you can verify the
  selection boundary before applying a correction scoped to it, the
  identical mask-as-opacity-map principle used throughout this course.
- **Color Match and Paste Attributes solve the matching problem through
  two fundamentally different mechanisms, which is exactly why one
  requires manual scope-checking for different lighting and the other
  doesn't.** Paste Attributes copies the literal stored parameter values
  from one clip's Lumetri effect onto another — identical numbers applied
  to different source pixels, which only produces a matching *look* if the
  two clips' underlying exposure and white balance were already similar.
  Color Match instead runs an algorithm that analyzes both clips' actual
  pixel/histogram data and computes new, clip-specific correction values
  intended to make the second clip's tonal and color distribution
  statistically resemble the reference — a real per-shot calculation, not
  a copy, which is why it can approximate a match even across differently
  lit footage where a literal parameter copy would fail.

## Exercise

Grade a short sequence of at least three clips (ideally from at least two
different shots/setups) using Basic Correction and the Color Wheels,
checking Waveform and Vectorscope throughout rather than by eye alone. Use
HSL Secondary to correct one specific color range in isolation, and match
the remaining clips to your primary grade using either Paste Attributes or
Color Match as appropriate to how similar their source lighting is.
