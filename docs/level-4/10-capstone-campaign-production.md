# 10 · Capstone Project — Full Campaign Production

The final project of the entire Adobe Mastery Path. It combines everything
from Level 4 — pipeline planning, Dynamic Link, color management, Team
Libraries, automation, Motion Graphics Templates, Lumetri scopes, InDesign
print production, and delivery workflows — into one complete, multi-app
campaign, built and delivered the way a real small studio would run it.

## What you'll build

- A **pipeline plan** (Module 1) mapping every asset and hand-off before
  any app work starts.
- A **Team Library** (Module 4) holding the campaign's shared logo,
  colors, and character styles.
- A **graded photo set** (reusing Level 3 Lightroom skills) exported at
  both sRGB and CMYK, with color management decisions documented
  (Module 3).
- A **hero video** cut in Premiere with at least one After Effects element
  brought in via Dynamic Link (Module 2), graded using full Lumetri
  scopes-based primary and secondary correction (Module 7), and titled
  using a reusable .mogrt built in After Effects (Module 6).
- A **print piece** in InDesign, built to full print-production standard —
  preflighted, packaged, and exported as a press-ready PDF (Module 8).
- At least one **automated step** (Module 5) somewhere in the pipeline —
  a Lightroom Publish Service, an Export Preset, or an InDesign Data Merge.
- A final **delivery package** and **archive** (Module 9), plus a short
  portfolio write-up.

## Step 1 — Plan the pipeline

1. Before opening any app, write out the full asset map per Module 1: what
   originates where, what's shared via the Team Library, which handoffs
   stay linked through production, and which flatten only at final
   delivery.
2. Decide the delivery color targets up front (Module 3): sRGB/Rec.709 for
   video and web, a specific CMYK profile for print — every later grading
   decision should trace back to this plan rather than being improvised
   per file.

## Step 2 — Set up the Team Library

1. Create a Team Library for the campaign (Module 4) containing the logo,
   2-3 brand colors, and a paragraph/character style pair.
2. If working solo, still go through the sharing setup steps so the
   workflow is understood; if collaborating, invite at least one other
   person with edit access and confirm a synced color/graphic appears
   identically in two different apps.

## Step 3 — Photography: grade and export

1. Import, cull, and grade a product/subject photo set in Lightroom
   (Level 3 skills), pulling the brand colors from the Team Library as a
   Color Grading reference where relevant.
2. Export two versions per Module 3: sRGB for the video/social pipeline,
   and a CMYK conversion (via Photoshop's Convert to Profile) for the
   print piece, using whatever profile a real print vendor would supply
   (or a standard commercial/coated profile as a stand-in).
3. If usable for automation, set up a Lightroom Export Preset or Publish
   Service (Module 5) for one of these exports.

## Step 4 — Build the hero video

1. Build an animated title or lower-third in After Effects, expose at
   least three controls via Essential Graphics, and export it as a .mogrt
   into the Team Library (Module 6) so it's reusable and shareable.
2. Separately, build one more complex AE element (a motion-tracked insert,
   an expression-driven background accent, or a multi-layer diagram) and
   bring it into the Premiere edit via Dynamic Link (Module 2) rather than
   a flattened render, so it can still be revised live during editing.
3. Cut the video in Premiere using the graded sRGB photos and/or original
   footage, then grade the full sequence using Lumetri scopes — Waveform
   for exposure, RGB Parade for cast-checking, Vectorscope for skin
   tones/saturation — plus at least one HSL Secondary correction (Module
   7).
4. Drop the .mogrt title into the timeline and customize its exposed
   controls per shot/section.
5. Export the final video via Export Media at a realistic delivery spec.

## Step 5 — Build the print piece

1. In InDesign, build a companion print piece (poster, one-pager, or
   small brochure) using the campaign's Team Library colors/styles, and
   the CMYK-exported photos from Step 3.
2. Run Preflight against a custom profile checking RGB-in-CMYK-document
   issues and low effective PPI, fixing every flagged issue.
3. Package the finished document with fonts and links, then export as
   Adobe PDF (Print) with bleed and printer's marks enabled per the
   vendor-style settings from Module 8.

## Step 6 — Deliver and archive

1. Assemble a labeled final delivery folder (Module 9) with clear
   subfolders for video and print, containing only final flattened
   deliverables — not working files.
2. Run a Collect Files / Package archival pass on both the Premiere and
   InDesign projects, labeled with a completion date, as a separate
   snapshot from the delivery folder.
3. Write a short portfolio case-study paragraph for the campaign,
   describing the pipeline decisions (what stayed linked vs. what
   flattened, and why) as much as the finished look.

## Step 7 — Full campaign review

Lay the video's final frame, the print piece, and the photo set side by
side one more time and confirm:

- The logo, brand colors, and any shared type/character styles are
  pixel-identical everywhere they appear, because they trace back to one
  Team Library rather than being rebuilt per app.
- The video's grade (checked via scopes) and the print piece's CMYK
  conversion both represent the same intended color, accounting for the
  expected shift between an emissive screen and a printed page.
- Every linked/live element used during production (Dynamic Link comp,
  .mogrt, InDesign image links) is fully resolved in the final delivered
  files, with no orphaned link warnings remaining.

## Cheat sheet — capstone touchpoints

| Deliverable | App(s) | Level 4 skills reused |
|---|---|---|
| Pipeline plan | — | Module 1 asset/link mapping |
| Shared brand assets | Team Library | Module 4 |
| Photo set (sRGB + CMYK) | Lightroom, Photoshop | Module 3, Module 5 (export automation) |
| Hero video | After Effects, Premiere | Module 2 (Dynamic Link), Module 6 (.mogrt), Module 7 (scopes) |
| Print piece | InDesign | Module 8 (preflight, package, PDF export) |
| Delivery + archive | — | Module 9 |

## How It Actually Works

- **Every check in Step 7 is verifying a different link/reference mechanism
  from across this whole level resolved correctly, not just that things
  happen to look similar.** "Pixel-identical brand assets" tests the Team
  Library's per-asset ID/version sync (Module 4); "the same intended color"
  tests whether both the Rec. 709/sRGB video pipeline and the CMYK print
  conversion started from one color-managed source and diverged only by
  the expected, physically-grounded gamut difference (Module 3); "no
  orphaned link warnings" tests that Dynamic Link, `.mogrt` exposure, and
  InDesign's Links panel all successfully resolved their references into
  final flattened data at export (Modules 2, 6, 8, 9). None of these are
  independent "spot the difference" checks — they're all instances of the
  same reference-resolution pattern this whole course keeps returning to,
  applied at the scale of a full production.
- **The video and print color match is bounded by physics, not tooling,
  which is why "accounting for the expected shift" is in the review
  checklist rather than "confirming an exact match."** As established in
  Module 3, CMYK's gamut is a real subset of what RGB/Rec. 709 can display
  — no amount of correct color management makes a saturated screen blue
  reproduce identically in ink. The review step is checking that the
  *intended* color direction and mood survive the conversion (a
  correctly-managed pipeline), not chasing an impossible pixel-for-pixel
  match across two different physical color-reproduction systems.
- **A Dynamic Link element and a `.mogrt` title represent the two opposite
  points on the same live-versus-packaged spectrum this level has been
  building toward, and using both in one hero video is a deliberate
  demonstration of choosing the right one per use case.** Dynamic Link
  keeps a live connection to a specific `.aep` file for content still under
  active revision within *this* project; the `.mogrt` packages a finished,
  reusable design into a portable, self-contained file safe to hand to
  other editors or reuse across other projects without depending on the
  source project's continued existence — the campaign uses each exactly
  where its trade-offs fit.
- **The archive-versus-delivery-folder split exists because flattening is
  irreversible (Module 9): the delivery folder holds only the end state of
  every reference resolved to final output, while the archive is the last
  point at which every link (Team Library assets, Dynamic Link comps,
  InDesign image links) is still live and re-editable.** Only the archived,
  pre-flattened project can actually support a future revision request —
  which is the concrete, practical reason this capstone treats "delivered"
  and "archived" as two genuinely different snapshots rather than one
  folder serving both purposes.

## Stretch goals

- Extend the pipeline to a second language version of the print piece
  using InDesign's layer-based translation approach (a hidden alternate
  text layer per language), keeping the same master pages and styles.
- Build a second .mogrt variant (alternate color) and A/B it in two cuts of
  the same video to compare which reads better against the final grade.
- Set up a full InDesign Data Merge (Module 5) generating a batch of
  personalized versions of the print piece (e.g. per-retailer or
  per-region variants) from one template and a CSV.
- Document the entire pipeline as a one-page process diagram (in
  Illustrator or InDesign) suitable for onboarding a new team member onto
  this exact workflow on a future campaign.
