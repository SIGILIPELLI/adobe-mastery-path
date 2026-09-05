# 01 · Multi-App Production Pipelines Overview

Levels 1-3 covered each Creative Cloud app largely on its own, with
occasional handoffs (a Library graphic dragged into Photoshop, an exported
PNG placed in InDesign). Level 4 is about treating the whole Creative Cloud
suite as **one pipeline**: files, colors, and assets that flow between
apps with as little manual re-export/re-import as possible. This module
maps that pipeline before the following modules dig into each connection.

## 1. Why pipelines matter at production scale

1. A single freelance piece can survive ad hoc exports. A real campaign —
   dozens of photos, a video, a print piece, all needing to match — breaks
   down fast if every handoff between apps is a flattened, disconnected
   file, because a late client change means re-exporting and re-placing
   everything by hand.
2. A pipeline replaces one-way exports with **live links** wherever
   possible: a Photoshop Smart Object placed in a video edit that updates
   when the source file changes, a Creative Cloud Library asset shared
   across every app in the campaign, a Dynamic Link between Premiere and
   After Effects that skips rendering entirely between them.
3. The trade-off is setup complexity: a pipeline needs consistent file
   organization, shared naming conventions, and — critically — consistent
   **color management** (Module 3) so a color that looks right leaving one
   app doesn't shift when it lands in the next.

## 2. Mapping a typical campaign pipeline

A common structure for a photo + video + print campaign:

1. **Lightroom** — ingest and grade all photography once, as the single
   source of truth for color on every photo asset used anywhere else.
2. **Illustrator / Photoshop** — build reusable graphic assets (logos,
   textures, title cards) saved to a shared **Creative Cloud Library**
   (Module 4) rather than as one-off files per deliverable.
3. **Premiere + After Effects** — cut video using Dynamic Link (Module 2)
   for any motion graphics element built in AE, so a title change in AE
   updates the Premiere timeline without a manual re-render/re-import.
4. **InDesign** — assemble the print deliverable, linking (not embedding)
   the same graded photos and Library graphics used in video/social, so a
   later color tweak in Lightroom or Illustrator can be picked up with
   **Links panel > Update Link** rather than re-placing files.
5. **Team Libraries** (Module 4) make every one of these shared assets
   visible to collaborators in real time instead of passed around as
   loose exported files.

## 3. Choosing links vs. embeds vs. flattened exports

1. **Linked** (Illustrator/Photoshop Smart Objects placed in another app,
   InDesign Place, Premiere/AE footage import) — the placing app stores a
   reference to the original file; editing the original and updating the
   link propagates the change. Best for anything likely to be revised.
2. **Embedded** (a Library graphic dropped in as a linked Smart Object vs.
   an old-style pasted/rasterized embed) — a copy lives inside the host
   file; safer for final archival delivery where the source shouldn't be
   able to change unexpectedly, but loses the live-update convenience.
3. **Flattened export** (a rendered MP4, a flattened JPEG/PDF) — the end
   of the pipeline, not a link in the middle of it; once flattened, further
   changes require regenerating and re-placing it.
4. A well-run pipeline keeps assets **linked** as long as they're still in
   production, and only flattens at final delivery (Module 9).

## 4. Naming, versioning, and folder conventions

1. Keep one project root folder per campaign with consistent subfolders —
   e.g. `01_Source`, `02_Working`, `03_Library_Assets`, `04_Exports` — so
   every app's file browser (Place, Import, Link) points at predictable
   locations rather than scattered desktop files.
2. Version working files with a clear suffix (`_v01`, `_v02`) rather than
   overwriting, especially for any file other collaborators are also
   linking to — an overwritten linked file with the same name can silently
   break another app's understanding of what changed.
3. Use **File > Package** (InDesign) or **File > Collect Files** (Premiere)
   at delivery time to gather every linked asset into one self-contained
   folder — this is the point where "linked for flexibility during
   production" converts into "portable for handoff."

## Worked example: planning a campaign pipeline

Sketch (on paper or in a doc, no app work yet) the pipeline for a product
launch: product photography graded once in Lightroom; a logo and two
graphic motifs built in Illustrator and saved to a Team Library; a 30-
second promo video cut in Premiere with an AE-built animated logo sting
brought in via Dynamic Link; and a print one-pager in InDesign linking the
same graded photos and Library logo. Note, for each arrow between apps,
whether it should be a live link or a one-time flattened export.

## Cheat sheet — pipeline concepts

| Concept | Where it shows up |
|---|---|
| Single color source of truth for photography | Lightroom Develop grade |
| Reusable shared graphics | Creative Cloud Library / Team Library |
| Live cross-app video/motion link | Dynamic Link (Premiere ↔ After Effects) |
| Live cross-app print link | InDesign Links panel |
| End-of-pipeline flatten | Rendered MP4, flattened PDF/JPEG |
| Portable handoff snapshot | Package (InDesign) / Collect Files (Premiere) |

## How It Actually Works

- **Every "live link" in this pipeline is the same underlying mechanism
  applied at different scopes: a stored reference (path or asset ID) plus a
  version marker, resolved fresh whenever the host file needs to render.**
  A Smart Object stores a source path/asset-ID; InDesign's Links panel
  stores a file path plus a last-known-modified timestamp; a Creative Cloud
  Library asset stores a cloud asset ID and version number; Dynamic Link
  (Module 2) stores a reference to an AE project and composition name. In
  every case, "updating a link" means the same operation: re-resolving that
  reference against the current state of the source and re-rendering from
  it — which is why understanding one of these mechanisms deeply (as
  Level 1's Libraries module did) transfers directly to reasoning about all
  the others.
- **A flattened export is irreversible precisely because it discards the
  reference, not because the file format itself is somehow "final."** An
  MP4 or flattened JPEG contains only rendered pixel/sample data with no
  stored pointer back to source layers, Develop parameters, or a Library
  asset ID — there is no data left in the file for any app to resolve back
  to an editable original. This is a strictly one-way data loss, which is
  exactly why the pipeline convention is to keep everything linked through
  production and flatten only once, at the very end, when no further
  revision is expected.
- **File > Package / Collect Files works by walking every stored link
  reference in the project and copying the referenced file into a new,
  self-contained folder, then rewriting the project's link paths to point
  at the copies.** This is a literal graph traversal of the project's
  reference structure (every Place, every linked footage item) — which is
  why a project with a missing or offline link produces a warning during
  packaging: the tool found a reference it could not resolve to an actual
  file to copy.
- **Consistent naming/versioning matters mechanically, not just as tidiness,
  because most linking mechanisms resolve by file path plus modification
  signal, not by content-aware identity.** Overwriting `logo_final.ai` in
  place changes the file at a path every linking app is already watching,
  which is usually the desired live-update behavior — but if two
  collaborators both save different content to the identical path
  concurrently, whichever save happens last silently becomes what every
  linked app resolves to next, with no merge and no built-in warning beyond
  what each app's own link-status indicator shows.
- **Color management (Module 3) is what makes "linked" and "matches
  visually" two different guarantees, which is the deeper reason a
  pipeline needs it explicitly.** A link mechanism guarantees the *same
  underlying data* reaches every app; it says nothing about whether that
  data renders identically once decoded through each app's own color
  space and rendering intent — an RGB photo linked identically into a video
  edit and a CMYK print layout is guaranteed to be the same source pixels,
  not guaranteed to look the same once each pipeline stage's color
  conversion is applied.

## Exercise

Write out the full asset pipeline for a hypothetical campaign of your own
choosing (photo + video + print), naming which app each asset originates
in, which apps it flows into, and whether each handoff should be a live
link or a flattened export. You'll build pieces of this exact pipeline in
the next several modules.
