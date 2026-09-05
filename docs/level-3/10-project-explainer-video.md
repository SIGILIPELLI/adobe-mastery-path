# 10 · Project — Animated Explainer Video

A single project combining everything from Level 3: After Effects motion
graphics fundamentals, keyframing/easing, compositing, expressions, and
motion tracking (Modules 1-4, 9), Lightroom import and color grading
(Modules 5-6), and InDesign styles for a companion print piece (Modules
7-8). You'll build a short **animated explainer video** plus a matching
one-page print handout, the same way the Level 2 capstone tied a marketing
campaign together across Photoshop, Illustrator, and Premiere.

## What you'll build

- A **graded product photo set** in Lightroom, culled and color-graded
  with a consistent house look.
- An **animated explainer video** in After Effects: a title sequence, an
  animated diagram/icon sequence explaining a product or process, a
  tracked screen-insert shot using real or simulated footage, and a
  looping background accent driven by expressions.
- A **companion one-page handout** in InDesign using the same graded
  photos and a styled layout, reusing the explainer's headline treatment.

This mirrors real studio delivery: one message, explained on video and
reinforced in print, from a shared set of assets rather than three
disconnected pieces.

## Step 1 — Prepare and grade the source photos in Lightroom

1. Import 10-15 product/subject photos relevant to whatever you're
   explaining (even a simple household object works for practice), using
   a file-renaming template and a base keyword during import (Module 5).
2. Cull with Pick/Reject flags and star ratings, then grade a hero shot
   fully in Develop — Basic panel tonal correction, an HSL adjustment, a
   Color Grading three-way tint, and at least one Masking-panel local
   adjustment (Module 6).
3. Save the grade as a Preset and Sync it across the rest of the Picks so
   every photo shares one consistent look, then export the graded set as
   JPEGs/PNGs for use in both AE and InDesign.

## Step 2 — Build the After Effects title and diagram sequence

1. New composition sized for your delivery target (e.g. 1920x1080, 25fps,
   30-45 seconds). Build an animated title card reusing the parenting and
   easing techniques from Modules 1-2: a background shape, headline text,
   and logo, entering with eased Position/Opacity keyframes refined in the
   Graph Editor.
2. Build a simple animated diagram explaining the product/process using
   shape layers and precomps (Module 3) — e.g. three icons appearing in
   sequence with staggered entrances (Sequence Layers keyframe assistant),
   each with a short text label.
3. Add at least one expression-driven element (Module 4): a looping
   rotating accent (`loopOut("cycle")`) or a Slider-Control-driven
   `wiggle()` on a background element for subtle continuous motion.
4. Composite one of the graded product photos into the diagram sequence
   using a track matte or mask (Module 3) so it integrates cleanly rather
   than sitting as an untouched rectangular image.

## Step 3 — Add the tracked screen-insert shot

1. Import a clip showing a hand holding a phone/tablet or a laptop screen
   (real footage, or a simulated static "photo pan" if live footage isn't
   available), and if it's handheld/shaky, stabilize it with Warp
   Stabilizer VFX first (Module 9).
2. Track the screen using a Perspective corner pin track, then composite a
   still or a simple graphic representing your product's interface onto
   the tracked surface via Edit Target > Apply.
3. Cut or composite this tracked shot into the main sequence between the
   title and the diagram section (or after it) so the explainer flows:
   title → diagram → tracked screen demo → closing title.

## Step 4 — Render and check the assembled video

1. **Composition > Add to Render Queue**, and export a final H.264 MP4 (or
   ProRes if it will be edited further in Premiere) at your target
   delivery resolution.
2. Play the full render back and confirm: the title's easing looks smooth
   (no linear/robotic motion), the diagram's staggered icons read clearly,
   the tracked screen insert holds steady with no drift, and the looping
   expression-driven accent doesn't visibly jump or reset.

## Step 5 — Build the companion handout in InDesign

1. New document: Letter or A4, single page (or a simple one-fold), with a
   margin/column grid set up per Module 7, and a Master page carrying a
   footer/page-number placeholder even for a one-pager (good habit for
   reuse as a template).
2. Define at least two paragraph styles (a Heading and a Body style, with
   Next Style/Based On set per Module 8) and apply them to the handout's
   headline and body copy, reusing the same headline wording from the
   video's title card for message consistency.
3. Place one or two of the Lightroom-graded photos with an appropriate
   fitting option, and style a callout/pull-quote box with an Object
   Style.
4. Export the finished handout as a print-ready PDF: **File > Export...**,
   format **Adobe PDF (Print)**, with your bleed settings from document
   setup carried through.

## Step 6 — Review video and print together

Play the video and view the handout PDF side by side. Check:

- Does the headline wording and treatment match between the video's title
  card and the handout's Heading style?
- Do the product photos share the same color grade in both the video
  composite and the printed handout?
- Would someone who only saw the handout (no video) and someone who only
  saw the video (no handout) come away with the same core message?

If anything drifts, trace it back to whether that asset came from the
shared Lightroom preset/graded export versus being redone by hand in one
app, and fix the source.

## Cheat sheet — project touchpoints

| Deliverable | App | Level 3 skills reused |
|---|---|---|
| Graded photo set | Lightroom Classic | Import/culling, Develop grade, Masking, Sync/Presets |
| Title + diagram sequence | After Effects | Parenting, keyframing/easing, track mattes, precomps |
| Looping accent | After Effects | `loopOut()`, Slider Control, `wiggle()` |
| Screen-insert shot | After Effects | Warp Stabilizer, Perspective corner pin tracking |
| Handout | InDesign | Grids/masters, paragraph/object styles, PDF export |

## How It Actually Works

- **The review checklist in Step 6 is checking that the same underlying
  data (a graded photo export, a wording string, a treatment style) was
  routed through two different rendering pipelines rather than recreated
  independently in each.** A Lightroom-exported JPEG carries baked-in RGB
  pixel values from Lightroom's Develop pipeline; After Effects composites
  that file as-is, while InDesign places it into its own print color
  workflow. Both apps start from the identical exported pixels, so any
  visible mismatch traces back to something happening *after* that shared
  export — a color-space conversion difference for print CMYK output, or a
  second, independent grading pass applied inside one app but not the
  other — rather than the Lightroom source itself having diverged.
- **The video and the print handout are fundamentally different rendering
  targets for the same source photo: one composites RGB frames for screen
  display (Rec. 709 or sRGB), the other converts to CMYK ink separations
  for a press or printer.** This is the identical RGB-vs-CMYK gamut
  distinction from Level 1's Illustrator module, applied to a photograph
  instead of vector fills — a graded photo that reads accurately on screen
  in the AE composite can legitimately shift somewhat once InDesign's PDF
  export converts it toward CMYK, which is a real, physically-grounded
  color-reproduction limit, not evidence the shared grade "failed."
- **Every reused element in this project (the graded photo, the headline
  wording, the track's applied keyframes, a Sync'd Develop preset) follows
  the same reference-versus-copy pattern this whole course keeps
  returning to**: a Lightroom preset stores parameter values applied fresh
  to each photo's own raw data at render time; an applied motion track
  writes literal keyframe data once, disconnected from the tracker
  afterward; a paragraph style's Based On chain resolves properties live at
  layout time. Recognizing which of those three mechanisms underlies a
  given piece of reused content is exactly what determines whether editing
  the "source" later will or won't propagate automatically — which is the
  practical, checkable question behind Step 6's "trace it back to the
  source" instruction.
- **Rendering the AE composition to H.264 for review versus ProRes for
  further Premiere editing is a real tradeoff in how much of the
  frame-by-frame compositing math survives for later use.** H.264 discards
  the alpha channel and re-encodes the flattened frame with lossy
  compression (see this level's compositing module); ProRes at 4444
  preserves alpha and uses comparatively light compression, which is why
  the tracked screen-insert and any composited elements stay editable and
  recombinable if the explainer needs to be re-cut in Premiere later,
  while an H.264 review copy has already permanently flattened and
  compressed every layer into one opaque stream.

## Stretch goals

- Export the After Effects title text as a separate alpha-channel render
  and place it as a looping preview frame grab inside the InDesign handout
  as a "watch the video" visual callout.
- Add a second Track Camera-based 3D element (Module 9) to the diagram
  sequence — e.g. a floating icon parented to a 3D-tracked null in a
  live-action background shot — instead of using only flat 2D shape
  layers.
- Turn the InDesign handout into a two-page spread using a Book file
  linking a cover file and a content file, synchronized per Module 8, and
  update page numbering across both.
- Recreate the video's title card as a second language version using an
  InDesign-style layer-based approach in After Effects (a hidden alternate
  text layer swapped in), and confirm timing/easing still reads correctly
  with the longer or shorter translated headline.
