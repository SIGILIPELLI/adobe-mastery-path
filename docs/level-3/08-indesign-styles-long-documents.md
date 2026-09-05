# 08 · InDesign Styles & Long Documents

A brochure shell (Module 7) is small enough to format by hand. A 40-page
report or a book isn't — every heading, caption, and body paragraph needs
to look identical without retyping formatting each time, and a long
document needs a table of contents and page numbering that stays correct
as content shifts. This module covers paragraph/character styles, the TOC,
and multi-file books.

## 1. Paragraph and character styles

1. **Window > Styles > Paragraph Styles** — format one paragraph by hand
   first (font, size, leading, space before/after, alignment), then with
   the cursor in it, click the panel's **Create New Style** button (or Alt/
   Option-click it to name it immediately), and it captures every
   attribute as a reusable style.
2. Apply a style to any paragraph by clicking into it and clicking the
   style name in the panel — every paragraph using that style updates
   instantly if the style itself is later edited (double-click the style
   name > adjust settings > OK).
3. **Character Styles** work the same way but for a run of selected text
   within a paragraph (e.g. bold for an inline emphasis, or a specific
   color for a pull-quote's lead word) rather than the whole paragraph.
4. Build a **style hierarchy**: set a paragraph style's **Next Style** (in
   its options dialog) so pressing Enter after, say, a Heading
   automatically switches the next paragraph to Body Text — speeds up
   flowing a long manuscript into styled structure.
5. **Based On** (also in style options) lets a style inherit from a parent
   style and only override specific attributes — change the parent and
   every style based on it updates too, unless that attribute was
   explicitly overridden locally.

## 2. Object styles and nested styles

1. **Window > Styles > Object Styles** captures frame-level formatting
   (fill, stroke, text frame inset, drop shadow) as a reusable style for
   consistent boxes/callouts/image frames throughout a document.
2. **Nested Styles** (inside a paragraph style's options, under **Drop
   Caps and Nested Styles**) automatically apply a character style to the
   first N words/characters/up-to-a-character of every paragraph using
   that style — e.g. auto-bolding the first three words of every body
   paragraph as a run-in lead, without manually selecting text each time.

## 3. Table of contents

1. Apply a consistent paragraph style to every heading level throughout
   the document first (e.g. `Heading 1`, `Heading 2`) — the TOC is built
   from style usage, not from manually typed text.
2. **Layout > Table of Contents...** opens the TOC dialog: add each
   heading style from **Other Styles** into **Include Paragraph Styles**,
   choose a TOC entry style/formatting for each, and set options like
   including page numbers and a tab leader.
3. Click **OK**, then click to place the generated TOC as a new story on a
   page — it's a live, regeneratable object: after edits shift content or
   page numbers, select the TOC frame and **Layout > Update Table of
   Contents** refreshes it without a full rebuild.

## 4. Books: linking multiple documents

1. **File > New > Book...** creates a `.indb` file that manages a set of
   separate InDesign documents (chapters) as one unit — useful when a
   long publication is split into multiple files for manageable file size
   or multi-author workflows.
2. In the **Book** panel, **+** adds existing `.indd` files as chapters,
   drag to reorder them, and the panel menu's **Synchronize Options...**
   lets you designate a "style source" chapter whose styles, master pages,
   and swatches propagate to every other chapter on **Synchronize**.
3. **Update Numbering > Update Page & Section Numbering** keeps page
   numbers continuous across chapter files (so chapter 2 correctly starts
   where chapter 1 left off), and **Output Book > Print Book / Export Book
   to PDF** processes every chapter file as one combined job.

## 5. Cross-references and footnotes

1. **Type > Hyperlinks & Cross-References > Insert Cross-Reference...**
   inserts a live reference to another paragraph (e.g. "see Figure 4 on
   page 12") that updates its page number automatically if content moves.
2. **Type > Insert Footnote** places a numbered footnote reference at the
   cursor and creates a matching numbered entry at the bottom of that
   column/page, renumbering automatically as footnotes are added or
   removed elsewhere in the flow.

## Worked example: styling a 20-page report

1. Define a style hierarchy: `Heading 1` (based on nothing, defines the
   base look) → `Heading 2` (Based On Heading 1, smaller size) → `Body
   Text` set as both headings' Next Style.
2. Apply an Object Style to every pull-quote/callout box for a consistent
   fill and inset across the report.
3. Build a Table of Contents pulling in Heading 1 and Heading 2, placed on
   page 2 right after the cover.
4. Split the report into two `.indd` files (front matter + body) linked
   via a Book file, with the front-matter file set as the style source,
   and run Synchronize followed by Update Numbering.

## Cheat sheet — styles & long documents

| Task | Where |
|---|---|
| Paragraph / Character styles panel | Window > Styles > Paragraph Styles / Character Styles |
| Auto-switch style on Enter | Style options > Next Style |
| Inherit from a parent style | Style options > Based On |
| Object-level reusable formatting | Window > Styles > Object Styles |
| Auto-style start of each paragraph | Paragraph style > Drop Caps and Nested Styles |
| Build/refresh a TOC | Layout > Table of Contents... / Layout > Update Table of Contents |
| Link multiple files as one publication | File > New > Book... |
| Sync styles/masters across chapters | Book panel menu > Synchronize Options... |
| Live "see page X" reference | Type > Hyperlinks & Cross-References > Insert Cross-Reference... |

## How It Actually Works

- **A Table of Contents is generated by scanning the document for text
  formatted with specific paragraph styles and extracting it into a new
  story, not by reading whatever text visually looks like a heading.** When
  you run Layout > Table of Contents, InDesign walks every paragraph in
  the (or a selected range of) document, checks each one's assigned
  paragraph style against your "Include Paragraph Styles" list, and for
  every match records that paragraph's text plus the page number it
  currently sits on into the generated TOC story. This is exactly why
  bold-and-large text that was never actually assigned the `Heading 1`
  style is invisible to the TOC — the mechanism keys on the style
  assignment metadata, not on visual appearance.
- **Update Table of Contents re-runs that same scan against the document's
  current state and rewrites the TOC story, rather than patching individual
  numbers in place.** Content shifting earlier in the document changes
  which page a heading now falls on; since page number lookup happens fresh
  at update time (the style-tagged paragraph's *current* page, read live),
  the regenerated entry reflects wherever that heading actually landed —
  the TOC has no independent memory of "what page this used to be," only a
  rule for finding out what page it is now.
- **Style cascading (Based On, and paragraph style inheritance generally)
  works through the same property-inheritance chain described for
  Illustrator Paragraph Styles: a child style stores only its deltas from
  the parent, and unset properties resolve by walking up the chain at
  render time.** Editing `Heading 1`'s base properties therefore
  automatically changes every paragraph rendered through `Heading 2` (which
  is Based On it) for any property `Heading 2` didn't explicitly override —
  there's no separate "propagation" step; every style read is simply
  resolved through the same live inheritance chain every time text is
  displayed.
- **Nested Styles apply a character style by counting characters/words in
  the paragraph's actual text stream at composition time, re-evaluated
  every time the paragraph's content or the nested-style rule changes.**
  "Bold the first three words" is stored as a rule (character style +
  word-count boundary), not as a one-time selection-and-format action;
  InDesign's text composition engine re-applies that rule to whatever text
  currently occupies the start of any paragraph using that style, which is
  why editing the opening words of a paragraph keeps the correct portion
  bolded automatically rather than leaving stale formatting behind.
- **A Book file's Synchronize step literally copies the style-source
  chapter's style/master/swatch definitions into each target chapter's own
  document, overwriting same-named definitions there** — it is a one-time,
  explicit copy operation triggered by clicking Synchronize, not a live
  link between chapter files. This is the structural reason chapters stay
  editable and shippable as independent `.indd` files day to day, but also
  why a style edited directly in a non-source chapter gets silently
  overwritten the next time someone runs Synchronize from the style-source
  chapter.

## Exercise

Build a style hierarchy of at least three paragraph styles (with Next
Style and Based On relationships) plus one Object Style, apply them
throughout a multi-page document, and generate a Table of Contents from
the heading styles. Confirm updating a parent style cascades to every
style based on it, and that Update Table of Contents correctly reflects a
page-number change after adding a page earlier in the flow.
