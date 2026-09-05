# 10 · Project — Multi-App Marketing Campaign

A single project that combines everything from Level 2: Photoshop
non-destructive compositing and grading (Modules 1-2), automation (Module
7), Illustrator typography, gradients/mesh, and patterns (Modules 3-4, 8),
and Premiere multi-cam, audio, and titles (Modules 5-6, 9). You'll build a
small but complete **marketing campaign** — a product photo set, a poster,
and a promo video — all sharing one visual system, the same way the Level 1
capstone proved out a shared Creative Cloud Library.

## What you'll build

- A **batch-processed product photo set** in Photoshop: several photos
  color-graded identically and watermarked automatically.
- An **Illustrator campaign background** combining a gradient/mesh-shaded
  graphic, an outlined/warped headline treatment, and a repeating pattern
  element.
- A **poster** in Photoshop combining a processed product photo with the
  Illustrator background and headline.
- A **short promo video** in Premiere: cut from at least two synced camera
  angles (or simulated as two takes if a second camera isn't available),
  audio-mixed, and finished with an Essential Graphics title built from a
  Motion Graphics Template.

This mirrors real studio work: one campaign, several deliverables, built
from a shared visual language rather than three unrelated files that
happen to look similar.

## Step 1 — Grade and batch-process the product photos

1. Take 3-5 product/subject photos (even phone photos of any object work
   for practice). Open one and build a grading pass using **Camera Raw
   Filter** plus a **Curves** adjustment on a Smart Object (Module 2).
2. Record an **Action** (Module 7) that applies an equivalent Camera Raw
   grade, adds your campaign watermark/logo via **Place Embedded**,
   flattens, and exports as a JPEG.
3. Run **File > Automate > Batch** with that Action across the full folder
   of product photos, saving to a new destination folder, so every photo in
   the set is graded and watermarked identically.

## Step 2 — Build the campaign background in Illustrator

1. Design a background shape or panel and apply a **gradient** (Module 4) —
   convert part of it to a **Gradient Mesh** if you want a more dimensional,
   shaded look rather than a flat linear/radial transition.
2. Build a repeating **pattern** swatch (Module 8) from a small brand motif
   and apply it as a subtle texture or accent area, scaled independently of
   its shape with the tilde-drag technique.
3. Set the campaign headline, apply any **OpenType** stylistic feature the
   font supports (Module 3), then duplicate it, **Create Outlines**, and
   apply a **Warp** or **Envelope Distort** effect for a distinctive
   treatment rather than plain flat type.
4. Use the **Appearance panel** (Module 4) to add a second stroke or subtle
   drop shadow to the headline so it separates cleanly from the busier
   background beneath it.
5. Group the finished background+headline and export a flattened PNG (for
   the poster) as well as saving it into your Creative Cloud Library
   (Level 1, Module 9) as a Graphic asset.

## Step 3 — Assemble the poster in Photoshop

1. Create a new Photoshop document at your target poster size (e.g.
   1080x1350px for a social post).
2. Drag the Illustrator background Graphic in from your Library — it lands
   as a linked Smart Object (Level 1, Module 9).
3. Place one of the batch-processed, watermarked product photos (Step 1)
   as a Smart Object above it, and use a **layer mask** (Level 1, Module 6)
   to blend its edges into the background cleanly.
4. Add a final **Curves** or **Color Balance** adjustment layer (Module 2)
   over the whole composite, masked as needed, so the product photo and the
   Illustrator background read as one cohesive grade rather than two
   mismatched sources pasted together.
5. Flatten a copy and export as the final poster JPEG/PNG.

## Step 4 — Cut the promo video in Premiere

1. Gather footage from at least two angles of the same short moment (two
   phones, or a planned two-take setup) and build a **Multi-Camera Source
   Sequence** (Module 5), syncing by audio.
2. Cut between angles in multi-camera view for a roughly 10-20 second
   sequence, then **Flatten** the result once the cut is locked.
3. Apply Lumetri color correction (Level 1, Module 8) matching the mood of
   the poster's grade, and mix audio (Module 6): tag dialogue/music, enable
   ducking if music is present, and check final levels on Audio Meters.
4. Build a title/lower-third in **Essential Graphics** (Module 9) reusing
   your campaign's color and headline treatment, pin it with **Responsive
   Design — Position**, and add an opacity fade-in via keyframes.
5. Export the title as a **Motion Graphics Template** to your Library first
   so it's reusable, then export the finished promo as an H.264 MP4 at a
   size appropriate for where it will run (e.g. 1080x1920 vertical for
   social).

## Step 5 — Review the campaign as a set

Lay the photo set, poster, and a frame grab (or the first few seconds) of
the promo video side by side. Check:

- Does the color grade feel consistent across the product photos, the
  poster, and the video?
- Does the same headline treatment (font, OpenType feature, warp/outline
  style) appear identically wherever it's used?
- Does the background pattern/gradient read as the same visual system
  across the poster and the video's title graphic?

If anything drifts, trace it back to whether that asset was pulled from
the shared Library/Action/Motion Graphics Template versus recreated by
hand in that specific app, and fix the source rather than patching the one
deliverable that looks off.

## Cheat sheet — project touchpoints

| Deliverable | App | Level 2 skills reused |
|---|---|---|
| Product photo set | Photoshop | Camera Raw/Curves grade, Actions, Batch |
| Campaign background | Illustrator | Gradient/Mesh, Pattern, Outlined/Warped type, Appearance |
| Poster | Photoshop | Smart Objects from Library, layer masks, adjustment layers |
| Promo video | Premiere | Multi-cam sync/cut, audio mixing, Essential Graphics title |

## How It Actually Works

- **Every "consistency check" in Step 5 is really verifying that a shared
  reference resolved identically in each app, not that a human eyeballed a
  close match.** The photo grade, the headline treatment, and the
  background pattern each trace back to one authoritative source: a
  recorded Action's parameters, a Library Graphic's version, or a `.mogrt`'s
  exposed properties. When something drifts visually, the actual cause is
  always one specific link in that chain being broken — a photo processed
  by hand instead of through the Batch-run Action, a headline retyped in
  Photoshop instead of pulled from the Library Graphic, a title rebuilt from
  scratch in Premiere instead of dropped in from the exported `.mogrt` —
  which is exactly why "fix the source, not the symptom" is the right
  instinct: the visual mismatch is a downstream symptom of a specific
  reference having been bypassed somewhere upstream.
- **The photo set and the poster/video grades can drift for a structural
  reason even when every asset is correctly linked: RGB (Photoshop/
  Illustrator) and Rec. 709 (Premiere/Lumetri) are different working color
  spaces evaluating the same numeric grade differently**, as covered in this
  level's color-correction module — matching the *mood* across deliverables
  built in different apps means matching the intent of a grade (its
  direction and relative strength), not assuming identical slider values
  will render identically once decoded through a different app's color
  pipeline.
- **The whole campaign's reuse strategy rests on the same three reference
  mechanisms stacked together**: Creative Cloud Library assets (cross-app,
  cross-document references resolved by asset ID and version), a `.mogrt`'s
  exposed-parameter whitelist (a locked structure with a small set of
  editable hooks), and a Photoshop Action's recorded, replayable command
  sequence (deterministic operations re-applied to new source data). Each
  solves a different kind of "keep many outputs synchronized with one
  source" problem — asset identity, template safety, and repeatable batch
  transformation, respectively — which is why a real production pipeline
  layers all three rather than relying on any single one to do everything.
- **A batch-processed photo set inherits any grading error uniformly and
  silently across every file, because the Action has no awareness of
  per-photo differences.** If the recorded Camera Raw parameters were tuned
  against one photo's specific exposure and white balance, running that
  same Action against photos shot under different lighting applies the
  identical absolute correction to all of them — correctly for the sample
  photo, and by exactly the same amount (right or wrong) for every other
  one, since the Action has no per-file adaptive logic, only a replayed
  fixed sequence of commands.

## Exercise

Complete all four deliverables — photo set, background, poster, and promo
video — as one connected campaign rather than four unrelated files. Confirm
the grade, headline treatment, and background pattern are visually
consistent across every piece by reviewing them side by side per Step 5.

### Stretch goals

- Export the campaign background's headline as a second, alternate-color
  **Motion Graphics Template** variant, and swap it into the promo video to
  compare which reads better on video versus in the static poster.
- Extend the Batch/Action pass from Module 7 to also output a second,
  smaller size of each product photo (e.g. a thumbnail set) in the same
  run, using the Image Processor's multiple-format option instead of a
  second manual Batch pass.
- Add a second multi-cam angle change and a Cross Dissolve transition
  (Level 1, Module 8) at the promo video's midpoint, timed to land on a
  matching cut in the campaign's visual rhythm (e.g. a beat where the
  on-screen title also changes).
- Recreate the poster at a second aspect ratio (e.g. a square 1080x1080
  version alongside the original 1080x1350) and confirm the Illustrator
  background's Responsive Design equivalent — rebuilding the layout so the
  shared Library graphic still reads correctly — holds up at both sizes.
