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

## Exercise

Take one graded photo and produce two exports: an sRGB version for web/
video use and a CMYK version converted to a specific print profile for a
layout piece. Soft-proof the CMYK version in Photoshop or InDesign with
Gamut Warning enabled, and note (in writing) any colors that shifted or
fell outside the printable gamut, and what you'd adjust in the original
grade to compensate.
