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
