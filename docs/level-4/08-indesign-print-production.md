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

## Exercise

Take a multi-page document with at least one full-bleed image and run it
through the full pipeline: fix every Preflight-flagged issue, confirm
every image's effective PPI is at least 300 at its printed size, Package
the finished file with fonts and links included, and export an Adobe PDF
(Print) with printer's marks and bleed enabled. Open the exported PDF and
verify the bleed and trim look correct at every edge.
