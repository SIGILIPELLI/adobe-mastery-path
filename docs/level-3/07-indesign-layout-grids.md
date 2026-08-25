# 07 · InDesign Layout & Grids Basics

This module moves into **InDesign**, Adobe's page-layout app for anything
with real structure across multiple pages — brochures, magazines, reports,
books. This module covers document setup, master pages, and the grid
systems (margins/columns and baseline grid) that keep a multi-page layout
consistent.

## 1. Creating a new document

1. **File > New > Document...** opens the New Document dialog. Choose an
   **Intent** (**Print** for physical output with bleed, **Web** or
   **Mobile** for on-screen work with pixel units).
2. Set **Page Size** (e.g. Letter, A4, or a custom size), **Orientation**,
   **Pages** (starting page count — more can be added later), and
   **Facing Pages** (checked for a spread-based document like a magazine
   where left/right pages mirror each other, unchecked for single
   independent pages like flyers).
3. Under **Columns**, set an initial column count and gutter, and under
   **Margins**, set Top/Bottom/Inside/Outside (or Left/Right if Facing
   Pages is off).
4. For print, expand **Bleed and Slug** and set a bleed (commonly 0.125in
   / 3mm) so background elements can extend past the trim edge without a
   white sliver appearing after trimming.

## 2. Master pages

1. The **Pages** panel (**Window > Pages**) shows master page spreads at
   the top and document pages below. Double-click **A-Master** to edit it.
2. Anything placed on a master page — a running header/footer, page
   numbers, a consistent background element — appears on every document
   page based on that master, and stays locked from accidental editing on
   document pages unless deliberately overridden.
3. Insert an automatic page number: **Type tool**, click a text frame on
   the master, **Type > Insert Special Character > Markers > Current Page
   Number** — this placeholder updates to the correct number on every page
   that uses the master.
4. To override a single master item on one document page (e.g. move the
   header slightly on a chapter-opening page), **Ctrl/Cmd+Shift+click** the
   item on that document page to detach a local copy for editing there
   only, leaving the master and every other page unaffected.
5. Create additional masters (panel menu > **New Master...**) for pages
   with a different structure (e.g. a `B-Master` for a two-column body
   layout vs. `A-Master` for single-column chapter openers), and apply a
   master to a range of pages by dragging its icon onto them in the Pages
   panel.

## 3. Margins, columns, and the layout grid

1. Adjust margins/columns after initial setup via **Layout > Margins and
   Columns...** (applies to the currently selected pages/spread).
2. **View > Grids & Guides > Show Baseline Grid** displays a horizontal
   grid tuned to your body text's leading — set its increment in
   **Preferences > Grids** to match your primary paragraph style's leading
   so lines of text across multiple columns/pages align to the same
   horizontal rhythm.
3. **Layout > Create Guides...** generates evenly spaced ruler guides
   across rows/columns for a page — useful for setting up a modular grid
   system (e.g. a 12-column grid for flexible image/text placement) beyond
   the basic Columns setting.
4. Enable **View > Snap to Guides** (and **Snap to Grid** for the baseline
   grid) so dragged frames lock to the structure instead of landing at
   arbitrary positions.

## 4. Text and graphic frames

1. **Type tool**, drag to create a text frame; **Rectangle Frame tool**
   (or Ellipse/Polygon Frame) to create a placeholder graphic frame, then
   **File > Place...** (**Ctrl/Cmd+D**) with a frame selected to import
   an image directly into it.
2. **Object > Fitting** submenu (or the Control panel's fitting buttons)
   controls how a placed image fills its frame: **Fit Content
   Proportionally**, **Fill Frame Proportionally**, **Fit Frame to
   Content**, or **Center Content**.
3. Link text frames into a flowing story by clicking the small red **+**
   outport at a full frame's bottom-right corner, then clicking (or
   drag-clicking) to create the next linked frame — text flows
   automatically from one into the next as it's edited.

## 5. Layers for organization

1. **Window > Layers** works like Photoshop/Illustrator layers, but at the
   whole-document level — useful for separating, say, a background-image
   layer from a text layer, or an English-text layer from a
   translated-text layer for a multi-language version of the same layout.
2. Lock or hide a layer to protect it while working on another (e.g. lock
   a finished background layer while placing new text on top).

## Worked example: a 4-page brochure shell

1. New document: Letter size, Facing Pages off (a standalone trifold),
   0.125in bleed, 3 columns, 0.1875in margins.
2. Build an `A-Master` with a footer text frame containing an automatic
   page number and a small logo placeholder.
3. Enable the baseline grid at an increment matching your body paragraph
   style's leading, and use **Create Guides** for a secondary 2-row split
   on the inside pages.
4. Place a text frame threaded across two panels for a longer article, and
   a separate graphic frame with **Fill Frame Proportionally** fitting for
   a hero image on the cover panel.

## Cheat sheet — InDesign layout & grids

| Task | Where |
|---|---|
| New document | File > New > Document... |
| Edit/create a master page | Pages panel, double-click / New Master... |
| Auto page number | Type > Insert Special Character > Markers > Current Page Number |
| Override one master item locally | Ctrl/Cmd+Shift+click the item |
| Adjust margins/columns | Layout > Margins and Columns... |
| Show baseline grid | View > Grids & Guides > Show Baseline Grid |
| Evenly spaced row/column guides | Layout > Create Guides... |
| Place an image | File > Place... (Ctrl/Cmd+D) |
| Image fitting options | Object > Fitting |
| Thread text frames | Click the outport (+), then click next frame |

## Exercise

Build a multi-page document (at least 4 pages) with a master page carrying
an automatic page number and a repeating footer element. Set up a column
grid and an aligned baseline grid, thread at least one text story across
two frames, and place an image using a specific fitting option. Override
one master item locally on a single page and confirm every other page
using that master is unaffected.
