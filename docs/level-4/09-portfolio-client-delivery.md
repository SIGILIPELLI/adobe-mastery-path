# 09 · Portfolio & Client Delivery Workflows

The pipeline work in this level (Modules 1-8) has all been about getting
color, assets, and links right *during* production. This module covers the
other end: packaging finished work for a client, and presenting it in a
portfolio — the final, flattened, no-longer-linked stage of the pipeline
from Module 1.

## 1. Final delivery packages: flattening the pipeline

1. By delivery time, every linked/live element from earlier modules
   (Dynamic Link comps, Library graphics, InDesign image links) should be
   resolved into final flattened output — a rendered MP4, a print-ready
   PDF, final exported images — per Module 1's rule of keeping things
   linked during production and flattening only at the end.
2. For video, **File > Export > Media** in Premiere with a preset matching
   the delivery spec (codec, resolution, frame rate — confirm against
   whatever the client/platform specifies, e.g. a specific bitrate cap for
   a streaming platform's upload requirements).
3. For print, deliver the **Packaged** InDesign folder (Module 8) alongside
   the final export PDF — the package serves as an editable-source
   handoff, the PDF as the client-facing proof/press file.
4. Organize final deliverables into a clearly labeled folder structure
   (e.g. `Client_Final_Delivery/Video`, `/Print`, `/Source_Files`) rather
   than handing over a flat folder mixing intermediate and final files.

## 2. Client review and approval rounds

1. For video review, use **Frame.io** (deeply integrated into Premiere via
   the **Frame.io** panel, or the standalone web app) to share a review
   link — clients comment directly on specific timecodes/frames, and
   those comments sync back into Premiere as markers on the timeline via
   the Frame.io panel.
2. For print/design review, share a PDF through **Acrobat's** commenting
   tools (or InDesign's own **Share for Review** for a cloud-based
   commenting link) so feedback lands as specific, positioned annotations
   rather than a vague email describing "the logo on page 3."
3. Track approval status explicitly (a simple version log: `v1 sent for
   review`, `v2 — logo size feedback addressed`, `v3 — approved`) so it's
   clear which version a client actually signed off on, especially across
   multiple revision rounds.

## 3. Building a portfolio piece

1. A portfolio case study should show **process, not just the final
   frame** — before/after grading comparisons (Lightroom's before/after
   view, **Window > Before/After**, or **Y** for a quick side-by-side
   toggle in Loupe), a few seconds of behind-the-scenes/raw footage next
   to the graded result, or a wireframe/early layout next to the finished
   InDesign piece.
2. For video work, export a **portfolio reel** — short cuts of your best
   3-6 second moments across projects, sequenced with quick cuts and a
   consistent look, rather than full unedited pieces end to end.
3. Keep portfolio exports at genuinely representative quality — export at
   full delivered resolution/bitrate rather than an overly compressed web
   preview that undersells the actual finished work's sharpness and color.

## 4. Rights, licensing, and client ownership

1. Confirm what's actually owned/licensed before including client work in
   a public portfolio: check the original contract/agreement for whether
   showcase use was permitted, and get explicit written permission if
   it wasn't addressed upfront — this applies to both the final piece and
   any raw/BTS material shown alongside it.
2. Stock assets (photos, fonts, templates, music) used in the delivered
   work carry their own license terms — confirm the license covers the
   client's actual use case (e.g. broadcast vs. web-only, print run size
   limits) before final delivery, not after the piece has shipped.
3. If a font was packaged into a print delivery (Module 8) or a .mogrt
   (Module 6), double check that font's license permits redistribution in
   that specific form — many commercial fonts explicitly prohibit
   embedding/sharing outside the licensed seat.

## 5. Archiving a finished project

1. Archive the full project (source files, linked assets, final exports)
   as one package once a project is fully approved and delivered — using
   **Collect Files** (Premiere: **File > Project Manager...** or **Collect
   Files** depending on version) or **Package** (InDesign) one more time
   as a *final* snapshot, separate from any earlier in-progress packages.
2. Store the archive with a clear naming convention including the
   completion date and final version number, so a future revision request
   (a common real-world occurrence — a client wanting a re-cut months
   later) can start from the exact delivered state rather than a
   half-finished working file.

## Worked example: delivering and archiving a client video

1. Export the final graded sequence via Export Media at the client's
   specified codec/resolution, and share a Frame.io review link for final
   sign-off.
2. Once approved, deliver the final MP4 plus a short portfolio cut (best
   10-15 seconds) into a labeled `Client_Final_Delivery` folder.
3. Confirm the stock music track's license covers the client's actual
   distribution (e.g. paid social ad use, not just organic posting, if
   that's the license tier purchased).
4. Run Collect Files on the finished Premiere project for archival,
   labeled with the completion date, before removing the project from
   active working storage.

## Cheat sheet — delivery & portfolio

| Task | Where |
|---|---|
| Final video export | File > Export > Media |
| Final print export | Package (Module 8) + Adobe PDF (Print) |
| Timecode-specific client video review | Frame.io panel in Premiere |
| Cloud commenting on a design file | InDesign Share for Review / Acrobat commenting |
| Before/after comparison for portfolio | Lightroom Y (Loupe before/after toggle) |
| Archive a finished project | Collect Files (Premiere) / Package (InDesign) |

## Exercise

Take one finished piece from an earlier module (video or print) and run a
full delivery pass: export at final delivery spec, organize it into a
clearly labeled delivery folder, and archive the complete project (source
+ linked assets) as a separate dated snapshot. Write a one-paragraph
portfolio case-study description for it that highlights process, not just
the final result.
