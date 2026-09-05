# 03 · Advanced Color Management Across Apps

Every earlier module assumed color mostly "just worked." At production
scale it doesn't automatically — a photo graded in Lightroom, a graphic
built in Illustrator, and a video graded in Premiere each have their own
color space handling, and a pipeline that ignores this ends up with colors
that shift between apps or between screen and print. This module covers
color spaces, profiles, and where to manage them in each app.

## 1. Color space basics for a mixed pipeline

1. **sRGB** — the standard color space for web/social/most screens; the
   safest default for anything delivered digitally without a specific
   wide-gamut display target.
2. **Adobe RGB** — a wider gamut than sRGB, historically common for print
   photography workflows where the extra range of greens/cyans matters.
3. **CMYK** — the print color model (Cyan/Magenta/Yellow/blacK); required
   for anything going to an offset or digital print press, and a smaller
   gamut than either RGB space above, meaning some RGB colors (especially
   saturated blues and greens) cannot be reproduced exactly and will shift
   when converted.
4. **Rec. 709** — the standard video color space (SDR broadcast/web
   video), analogous to sRGB but with different gamma handling, relevant
   in Premiere/After Effects rather than the still-image apps.
5. The core rule for a multi-app pipeline: decide the **final delivery**
   color space first (web, print, or broadcast), and set every app in the
   chain to work in a space that converts predictably into it, rather than
   discovering the mismatch at final export.

## 2. Color settings in Photoshop and Illustrator

1. **Edit > Color Settings...** in both apps sets the default working RGB
   and CMYK spaces for new documents. For a team, **Save...** a color
   settings preset and share it (or use **Load...** to import a shared
   `.csf` file) so every collaborator's app applies identical defaults.
2. When opening a file whose embedded profile differs from the working
   space, both apps show a **Missing/Mismatch Profile** dialog — choose
   **Use the embedded profile** to preserve the file's original intended
   color rather than silently reinterpreting it in the current working
   space.
3. For final print output, **Edit > Convert to Profile...** (not just
   changing Color Settings, which only affects new documents) converts an
   existing document's actual pixel/color values to the target CMYK
   profile supplied by the print vendor, if one was given.

## 3. Color management in Lightroom Classic

1. Lightroom's internal working space (ProPhoto RGB, a very wide gamut) is
   fixed and not user-configurable — color management surfaces instead at
   **export**: the **Export** dialog's **File Settings > Color Space**
   dropdown lets you choose sRGB (default, safest for anything digital),
   Adobe RGB, or ProPhoto RGB for the exported file.
2. Always export **sRGB** for web/social/video-pipeline use unless a
   downstream app or print vendor specifically requests a wider space —
   an Adobe RGB export viewed in a non-color-managed context (many
   browsers, some video players) can look visibly desaturated compared to
   how it looked in Lightroom.

## 4. Color management in Premiere and After Effects

1. Premiere Pro's newer sequences default to **HDR/Wide Gamut** color
   management under **Sequence > Sequence Settings > Color Management**
   options in recent versions; for standard delivery, confirm the sequence
   is working in **Rec. 709** unless the project specifically targets HDR.
2. **Lumetri Color's Input LUT** (per-clip, at the top of the Basic
   Correction section) applies a color transform on ingest for footage
   shot in a camera log/flat profile (e.g. a LUT converting a Log-C or
   S-Log clip toward Rec. 709) before any creative grading happens on top.
3. After Effects: **File > Project Settings > Color Management** sets the
   project's working color space and whether to use a **Linearize Working
   Space** or a specific **Working Space** profile — for a project mixing
   footage and graphics, keeping this consistent with the Premiere
   sequence it will Dynamic Link into (Module 2) avoids a visible shift
   when the AE comp appears inside the Premiere timeline.

## 5. Soft-proofing for print

1. In Photoshop or InDesign, **View > Proof Setup > Custom...** lets you
   select the target CMYK/print profile and preview on-screen
   approximately how the file will look once printed, including **Simulate
   Paper Color** for an uncoated/coated stock comparison.
2. **View > Gamut Warning** highlights (in gray by default) any pixels in
   the current RGB document that fall outside the selected proof profile's
   printable gamut — a fast way to spot an oversaturated color before it
   surprises you on a printed proof.
3. Soft-proofing is an approximation (dependent on a calibrated, wide-gamut
   monitor) — for critical color work, a physical proof print from the
   actual intended press/printer remains the final check.

## Worked example: checking a campaign for color drift

1. Export the campaign's hero photo from Lightroom as sRGB for web/video
   use and separately as a CMYK-converted TIFF (via Photoshop's Convert to
   Profile with the print vendor's supplied profile) for the InDesign
   print piece.
2. Confirm the Premiere sequence and the linked After Effects composition
   (Module 2) are both set to Rec. 709 so the title sting doesn't shift in
   saturation when it appears in the timeline.
3. In InDesign, soft-proof the placed CMYK photo against the print
   profile, checking Gamut Warning on the original RGB source for any
   colors that won't survive the CMYK conversion, before sending to print.

## Cheat sheet — color management touchpoints

| App | Where to manage color |
|---|---|
| Photoshop / Illustrator | Edit > Color Settings..., Edit > Convert to Profile... |
| Lightroom Classic | Export dialog > File Settings > Color Space |
| Premiere Pro | Sequence Settings > Color Management, Lumetri Input LUT |
| After Effects | File > Project Settings > Color Management |
| Photoshop / InDesign print preview | View > Proof Setup > Custom..., View > Gamut Warning |

## How It Actually Works

- **A color profile is a mathematical mapping between a device-independent
  reference space and a specific set of numeric RGB/CMYK values, not a
  cosmetic tag.** An ICC profile defines exactly what real-world color
  (in a standardized space like CIE Lab) each possible numeric value in
  that profile's space corresponds to. This is why "Use the embedded
  profile" versus letting an app reinterpret a file in its own working
  space produces genuinely different colors: the identical numeric pixel
  values (say, RGB 200,50,50) mean a measurably different real-world color
  under an Adobe RGB profile than under an sRGB profile, because each
  profile defines its own mapping from numbers to actual color.
- **Converting between color spaces (RGB to CMYK, sRGB to Adobe RGB) is a
  real numeric transform through that device-independent reference space,
  and it is lossy whenever the destination gamut is smaller.** Convert to
  Profile looks up each pixel's color in the reference space via the source
  profile, then finds the nearest reproducible value in the destination
  profile's gamut using a chosen rendering intent (Perceptual compresses
  the whole gamut relatively to preserve smooth gradations, Relative
  Colorimetric clips out-of-gamut colors to the nearest in-gamut edge
  while leaving in-gamut colors unchanged) — which is exactly the
  mechanism behind Gamut Warning: it's flagging pixels whose reference-space
  color falls outside the boundary the destination profile can represent
  at all.
- **A camera Log/flat profile stores sensor data non-linearly specifically
  to preserve more dynamic range in a standard bit depth, and an Input LUT
  is a lookup table reversing that specific non-linear encoding back toward
  a standard viewing space.** Log encoding intentionally under-represents
  shadows and compresses highlights relative to how a display expects to
  show them, trading immediate "correct-looking" footage for extra
  recoverable range during grading; the LUT is a literal per-value or
  per-cube remapping table (the same interpolated-lookup concept as an
  adjustment layer's tone curve) built to invert that specific encoding
  curve, which is why using the wrong camera's LUT on another camera's log
  footage produces visibly incorrect color — the lookup table doesn't match
  the actual encoding that was applied at capture.
- **Rec. 709 and sRGB share nearly the same color primaries and gamut but
  differ in their transfer function (gamma curve), which is the specific,
  measurable reason "video" and "web/print" color pipelines aren't
  simply interchangeable despite looking similar.** Both define red/green/
  blue primaries and a white point close enough to be nearly identical in
  gamut extent, but the numeric-value-to-brightness relationship (the
  transfer function/gamma) each specifies differs slightly — an image
  correctly decoded under one transfer function and displayed as if it used
  the other renders with a measurable brightness/contrast shift, which is
  the mechanical reason keeping Premiere's sequence and a Dynamic-Linked AE
  comp's project color settings aligned specifically matters, beyond just
  "using similar-sounding color spaces."
- **Lightroom's fixed ProPhoto RGB working space is deliberately wider than
  any output target, which is why export-time conversion (not the internal
  working space) is the actual control point for color management.**
  ProPhoto RGB's gamut is wide enough to contain essentially the full range
  of colors a camera sensor can capture, so every internal Develop
  calculation happens with maximum headroom; the meaningful compression
  down to sRGB, Adobe RGB, or a CMYK proof profile only happens once, at
  the export step, which is precisely the mechanism the exercise below is
  demonstrating by producing two different exports from one graded source.

## Exercise

Take one graded photo and produce two exports: an sRGB version for web/
video use and a CMYK version converted to a specific print profile for a
layout piece. Soft-proof the CMYK version in Photoshop or InDesign with
Gamut Warning enabled, and note (in writing) any colors that shifted or
fell outside the printable gamut, and what you'd adjust in the original
grade to compensate.
