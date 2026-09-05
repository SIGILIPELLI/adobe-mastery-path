# 10 · Capstone Project — Brand Kit

A single project that combines everything from Level 1: Creative Cloud
Libraries (Modules 1 & 9), Illustrator vector work (Modules 3 & 7),
Photoshop compositing (Modules 2 & 6), and Premiere Pro editing (Modules 4
& 8). You'll build three connected deliverables — a logo, a poster, and a
short promo video — that all share the same colors, logo, and typography
through one Creative Cloud Library.

## What you'll build

- A **logo** designed in Illustrator, saved as a Graphic asset in your
  shared Library.
- A **poster / social graphic** in Photoshop that reuses the exact same
  logo, colors, and character style.
- A **short (10-15 second) promo video** in Premiere Pro that reuses the
  same logo and brand colors as an on-screen graphic.

Because all three pull from one Library, changing a brand color or the
logo later would (in principle) update it in all three places — the point
of this capstone is proving that pipeline works end to end, not just
producing three unrelated files that happen to look similar.

## Step 1 — Confirm your shared Library

1. Open **Window > Libraries** in Illustrator and select `Mastery Path
   Brand Kit` (created in Module 1, populated further in Module 9).
2. Confirm it has: at least two named color swatches (e.g. `Brand Primary`,
   `Brand Accent`), one saved character style, and at least one saved
   graphic. If anything is missing, add it now using the steps from
   Module 9 before continuing — everything downstream depends on this
   Library being populated first.

## Step 2 — Design the logo in Illustrator

1. Open a new Illustrator document. Using Pathfinder operations (Module 7)
   and/or the Pen tool (Module 3), build a simple logo mark — an icon shape
   plus a short wordmark using your saved character style is enough; this
   doesn't need to be elaborate.
2. Apply your Library's `Brand Primary` and/or `Brand Accent` swatches as
   the fill color(s), rather than picking new colors freehand, so the logo
   and your palette stay linked.
3. Group the finished logo (**Object > Group**, ⌘/Ctrl+G), then drag it
   into the Libraries panel to save (or update) it as your shared Graphic
   asset — this is the version every other file will pull from.
4. Export a standalone copy too: **File > Export > Export As**, both a
   transparent PNG (for the poster) and an SVG (general web use).

## Step 3 — Build the poster in Photoshop

1. Create a new Photoshop document sized for a poster or social post (e.g.
   1080×1350 px for a social graphic, or a print-ready size like 8.5×11in
   at 300 PPI if you want to try the print path from Module 7).
2. Open **Window > Libraries**, select the same `Mastery Path Brand Kit`,
   and drag your logo Graphic asset directly onto the canvas — it lands as
   a linked Smart Object, not a flattened paste.
3. Add a background using a solid fill or an adjustment layer (Module 6)
   built from your Library's brand colors, and a headline text layer using
   your saved character style from the Libraries panel.
4. Use a layer mask (Module 6) if you're compositing the logo or headline
   over any photo/texture background, so the blend looks intentional rather
   than pasted on top.
5. Export the flattened poster as a PNG or JPG (Module 2's Export As
   workflow).

## Step 4 — Cut the promo video in Premiere Pro

1. Gather 2-4 short video clips (stock footage, phone clips, or screen
   recordings all work) and import them (Module 4).
2. Build a 10-15 second sequence: a couple of quick cuts using the Razor
   tool, at least one Cross Dissolve transition (Module 8) between two of
   them, and basic Lumetri color correction on at least one clip.
3. Open **Window > Essential Graphics**, drag your Library's logo asset
   onto the timeline near the start or end as a title card, positioned and
   scaled over a couple of seconds — this is the same logo file used in
   Steps 2 and 3, not a re-exported copy.
4. Add a short text overlay using your brand's character style/colors if
   your Premiere version surfaces Library text styles in Essential
   Graphics; otherwise, manually match the same font, size, and hex color
   values from your Library swatches.
5. Level the audio (Essential Sound, Module 8) and export as an H.264 MP4
   sized appropriately for where this promo would actually be posted (e.g.
   1080×1920 for a vertical social promo, or 1920×1080 for a general web
   promo).

## Step 5 — Review the whole kit together

Lay the three outputs side by side — the logo PNG/SVG, the poster export,
and a frame grab or the first few seconds of the promo video. Check:

- Does the same logo appear identically (same proportions, same colors) in
  all three?
- Do the brand colors match across the poster background/accents and any
  on-screen graphic in the video?
- Does the headline/title typography look consistent between the poster
  and the video's text overlay?

If any of these drift, that's the exact failure mode a shared Library is
meant to prevent — trace it back to whether that asset was actually pulled
from the Library versus recreated by hand in that app, and fix the source.

## Cheat sheet — capstone touchpoints

| Deliverable | App | Library assets reused |
|---|---|---|
| Logo | Illustrator | Colors (created here), saved as the Graphic asset |
| Poster | Photoshop | Logo Graphic (Smart Object), colors, character style |
| Promo video | Premiere Pro | Logo Graphic (title card), colors, character style (where supported) |

## How It Actually Works

- **Every deliverable resolves the same asset IDs, not copies of the same
  values.** The logo, poster, and promo video don't happen to use matching
  colors because you typed the same hex code three times — each app reads
  the color swatch and Graphic by the Library's internal asset ID and
  resolves it to whatever data is currently attached to that ID. This is
  the structural reason the "make one deliberate change" step in the
  exercise is worth doing: it proves the three files are wired to a shared
  source of truth rather than three independent snapshots that merely
  started out looking the same.
- **Color drift between the poster and the video is usually a color-space
  mismatch, not a broken Library link.** Photoshop's document, if left in
  RGB, and Premiere's Lumetri pipeline, which operates in its own working
  color space (typically Rec. 709 for SDR video), can render the *same*
  underlying RGB values as visibly different colors on screen if one
  environment applies a different gamma/transfer curve than the other. This
  is why "the colors match on paper" (identical hex values in both
  Libraries panels) can still look slightly different side by side —
  it's two different rendering pipelines interpreting the same numbers, not
  a sync failure.
- **A logo placed as a Smart Object in Photoshop versus a linked graphic in
  Premiere are resolved through two different rendering paths from the same
  source data.** Photoshop's Smart Object resolves the Illustrator document
  through its own vector-rasterization engine at whatever size/resolution
  the Smart Object bounding box requires. Premiere's Essential Graphics
  engine resolves the same underlying asset through its Motion Graphics
  template renderer, which composites it directly into the video frame's
  color space and frame rate. Both start from the identical Library asset,
  but each app's own compositing engine is what actually produces the pixels
  you see — which is why a shape can look subtly different in weight or
  antialiasing between the poster and the video overlay even when nothing
  about the source Graphic changed.
- **Frame grabs and exported stills are a one-time rasterization, frozen at
  export time.** Once you flatten the poster to a PNG or export a frame from
  the promo video, that specific file is permanently disconnected from the
  Library — it holds no asset ID, no version reference, nothing that would
  let it "catch" a later color change automatically. Only the *source*
  Photoshop/Premiere project files stay live-linked; every exported
  deliverable is a snapshot that has to be manually re-exported after a
  Library update if it needs to stay current, which is exactly the
  distinction the review step in Step 5 is testing you on.

## Exercise

Complete all three deliverables — logo, poster, promo video — pulling
every shared element (logo, colors, character style) from your `Mastery
Path Brand Kit` Library rather than recreating them independently in each
app. Then make one deliberate change to a color swatch in the Library
(e.g. adjust `Brand Accent`'s hex value slightly) and check, in each app,
whether the placed instances offer a way to refresh/update to the new
value versus needing to be manually replaced — this is worth understanding
now, since it's exactly the workflow professional teams rely on to keep a
brand consistent across dozens of files.

Completing this project means you're ready for **Level 2 · Intermediate**.
