# 08 · InDesign-to-Print Production Workflow

Level 3 built long documents with styles and grids. Getting a document
from a finished layout to an actual printed piece — without a costly
misprint — needs a specific pre-flight and export process. This module
covers preflight checking, packaging, and exporting a genuinely
print-ready PDF.

## 1. Preflight: catching problems before export

1. **Window > Output > Preflight** opens the Preflight panel; it runs
   continuously against the active **Preflight Profile** (dropdown at the
   panel's top), flagging issues live as you work — a red icon in the
   document window's status bar (bottom-left) means at least one error is
   currently present.
2. The default **[Basic]** profile checks for things like overset text
   (text that doesn't fit its frame), missing/modified links, and low-
   resolution images. Load or build a custom profile (panel menu >
   **Define Profiles...**) for stricter print-specific checks — e.g.
   flagging any RGB image intended for CMYK output, or text under a
   minimum point size.
3. Fix every flagged issue (or consciously accept it, if it's a false
   positive for your case) before exporting — the Preflight panel doubles
   as a checklist, not just a warning.

## 2. Links, resolution, and image color mode

1. **Window > Links** lists every placed image/file with its status;
   a yellow warning triangle means the link is out of date (source file
   changed since placement) — select it and click **Update Link** (the
   circular arrows icon at the panel's bottom) to refresh.
2. Click a link and check its **Effective PPI** in the Links panel's info
   section (or Link Info) — print generally needs **300 PPI effective
   resolution** at final printed size; an image scaled up significantly in
   InDesign will show a much lower effective PPI than its native
   resolution, a common cause of print blur that Preflight can also flag.
3. Confirm placed images intended for CMYK print output are actually in
   CMYK mode (check in Photoshop before placing, or via the Links panel's
   color space info) — an RGB image placed and printed without proper
   conversion can shift color unpredictably (tying back to Module 3's
   color management).

## 3. Bleed, slug, and trim marks

1. Confirm the document's **bleed** was set at creation (**File > Document
   Setup...** to check/adjust after the fact) and that every background
   element meant to run to the edge of the page actually extends past the
   trim edge into the bleed area, not just up to it.
2. The **slug** area (also in Document Setup) holds information meant for
   the print shop but not for the final trimmed piece — job name, date,
   color bars — positioned outside even the bleed.
3. When exporting, printer's/trim marks and bleed are controlled from the
   **Marks and Bleeds** section of the Export/Print dialog (Section 5) —
   they're not baked into the document itself.

## 4. Packaging for handoff to a print vendor or another designer

1. **File > Package...** gathers the document, every linked image/font,
   and a summary report into one self-contained folder — click through
   the Package dialog's summary screen (which surfaces any unresolved
   Preflight issues one more time) before confirming.
2. Choose which fonts to include (subject to font licensing — some fonts
   restrict redistribution; check before including) and whether to copy
   linked graphics and update graphic links in the package copy.
3. Hand the packaged folder to a print vendor instead of just the `.indd`
   file — a copy without its fonts/linked images is nearly useless to
   anyone without the exact same files already on their machine.

## 5. Exporting a print-ready PDF

1. **File > Export...**, choose **Adobe PDF (Print)** as the format —
   distinct from **Adobe PDF (Interactive)**, which is meant for on-screen
   PDFs with digital-only features and is not appropriate for a press.
2. In the Export Adobe PDF dialog, choose a **Preset** matching the
   destination if the print vendor specifies one (e.g. **PDF/X-1a:2001**
   for a common press-safe standard, which forces CMYK/spot-only color
   and flattens transparency), or **[High Quality Print]** as a solid
   general default.
3. On **Marks and Bleeds**, enable **All Printer's Marks** if the vendor
   wants trim/registration marks, and set **Use Document Bleed Settings**
   (or enter matching custom bleed values) so bleed is included in the
   exported PDF.
4. On **Output**, confirm **Color Conversion** and the destination
   **Profile** match what the vendor requested (e.g. converting everything
   to a specific CMYK profile at export, if the source document mixed RGB
   and CMYK content).
5. After export, open the PDF and zoom into corners/edges to confirm
   bleed extends correctly and no unexpected white gap appears at the
   trim line — a final visual check the automated preflight and export
   settings can't fully substitute for.

## Worked example: preparing a brochure for print

1. Run Preflight against a profile checking for RGB images and sub-300 PPI
   effective resolution; fix every flagged image (recolor to CMYK in
   Photoshop, or replace a low-res placement with a higher-resolution
   source).
2. Confirm bleed is set and background panels extend into it, then Package
   the document, including fonts and updated links, into a
   `Brochure_Final_Package` folder.
3. Export **Adobe PDF (Print)** using the vendor's supplied PDF/X preset,
   with printer's marks and document bleed enabled, then open the exported
   PDF and zoom into each bleed edge to confirm no white gap.

## Cheat sheet — print production

| Task | Where |
|---|---|
| Live preflight checking | Window > Output > Preflight |
| Check/update image links | Window > Links |
| Check effective resolution | Links panel > Link Info / Effective PPI |
| Confirm/adjust bleed and slug | File > Document Setup... |
| Bundle fonts + links + report | File > Package... |
| Export print-ready PDF | File > Export... > Adobe PDF (Print) |
| Include trim/registration marks | Export dialog > Marks and Bleeds |
| Set output color conversion | Export dialog > Output |

## How It Actually Works

- **Effective PPI is a real, computed ratio, not a fixed image property —
  it's the image's native pixel dimensions divided by the physical size
  it's actually been scaled to on the page.** A 3000×3000px photo at
  native size delivers 300 PPI on a 10-inch-wide frame, but scaling that
  same frame up to 20 inches spreads the identical 3000 pixels across
  double the physical area, halving the effective PPI to 150 — the pixel
  data hasn't changed, but the density it needs to cover per inch has. This
  is exactly why Preflight can flag "low resolution" on an image whose
  original file was perfectly high-res: the problem is the placement scale,
  not the source file.
- **Preflight runs its checks continuously by re-evaluating the document's
  current state against the active profile's rule set on every relevant
  change**, rather than only when manually invoked — a rule like "flag any
  RGB image" is a real test applied to every placed image's actual color
  mode metadata, and a rule like "flag overset text" is checking whether
  the text composition engine (the same story/frame flow model from Level
  3) actually placed every character within a visible frame boundary or
  has leftover unplaced text. This live, rule-based checking is why the
  status-bar indicator updates the moment an issue appears or gets fixed,
  with no separate "run preflight" step required.
- **A PDF/X preset works by constraining PDF export to a restricted,
  standardized feature subset the press's RIP (raster image processor)
  software is guaranteed to interpret correctly** — forcing CMYK/spot-only
  color output, flattening transparency into fully composited pixels, and
  embedding all fonts. Transparency flattening specifically resolves
  InDesign's live, order-dependent compositing (drop shadows, blend modes,
  opacity — the same mechanisms from earlier compositing modules) down into
  final, non-interactive rendered output ahead of time, because many
  print RIPs cannot correctly interpret live transparency effects the way
  a screen-rendering engine can.
- **Bleed exists to cover the same real-world cutting-tolerance problem
  covered in Level 1's Illustrator module — a press's physical trim cannot
  guarantee zero-error alignment — and the PDF's Marks and Bleeds settings
  are what actually embed that extra margin (and any registration marks) as
  literal extra content in the exported page boundary**, beyond the
  document's own trim size. This is why bleed has to be both set correctly
  in Document Setup *and* explicitly enabled at export — Document Setup
  defines how much of the artwork extends past trim in the working file,
  while the export dialog's own setting controls whether that same margin
  is actually included in the delivered PDF's page geometry.
- **Package performs the identical link-graph traversal described in this
  level's pipeline-overview module — walking every Links panel entry and
  every font reference used anywhere in the document — and copies each
  resolved file into the new folder, then (optionally) repoints the
  packaged copy's own link paths at the copies.** A link that's offline or
  a font that can't be located produces exactly the same class of warning
  in Package's summary screen as Preflight's missing-link check, because
  both are querying the same underlying link-resolution data — Package
  just acts on it by copying files rather than merely flagging them.

## Exercise

Take a multi-page document with at least one full-bleed image and run it
through the full pipeline: fix every Preflight-flagged issue, confirm
every image's effective PPI is at least 300 at its printed size, Package
the finished file with fonts and links included, and export an Adobe PDF
(Print) with printer's marks and bleed enabled. Open the exported PDF and
verify the bleed and trim look correct at every edge.
