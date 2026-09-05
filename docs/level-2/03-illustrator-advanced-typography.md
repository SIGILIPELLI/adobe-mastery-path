# 03 · Illustrator Advanced Typography

Level 1 (Module 7) covered basic character formatting and text-on-a-path.
Real typographic work goes further: **OpenType features** that unlock a
font's built-in alternate glyphs, **paragraph styles** that keep long-form
text consistent the way character styles keep short runs consistent, and
**outlining type** to turn letterforms into editable vector paths for
custom logotype and wordmark effects.

## 1. OpenType features and alternate glyphs

Many professional fonts ship with extra characters beyond the standard
alphabet — swashes, ligatures, old-style figures — that don't appear unless
you explicitly turn them on.

1. Select some text with the **Type tool** (**T**), then open **Window >
   Type > OpenType** to see which features the current font supports (any
   feature not supported by that specific font appears grayed out).
2. **Standard Ligatures** joins letter pairs that collide at their default
   spacing — most commonly "fi" and "fl" — into a single, better-fitted
   glyph. **Discretionary Ligatures** adds more decorative joins (e.g. "st",
   "ct") where the font provides them, for a more stylized setting.
3. **Swash** replaces standard letterforms with decorative script-style
   alternates, typically only available at the start or end of a word.
   **Stylistic Alternates** and numbered **Stylistic Sets** (**Set 1**,
   **Set 2**, ...) group whole families of alternate letterforms a type
   designer bundled together — turn on one set at a time and compare rather
   than stacking several, since sets are usually designed to coordinate as a
   unit, not layer with each other.
4. **Old Style figures** draws numerals with varying heights and descenders
   (blending into a paragraph of text more quietly), versus default
   **Lining figures**, which are all cap-height (better for figures inside
   an all-caps headline or a table of numbers that needs to align).
5. For a specific single character rather than a feature applied to a whole
   selection, open **Window > Type > Glyphs**, double-click a font in the
   list to filter, and double-click any glyph to insert it at the cursor —
   or, with the Type tool active, hover over a character that has
   alternates until a small triangle appears beneath it, then click and hold
   to pick from a pop-up row of alternates for just that letter.

!!! info "Not every font supports every feature"
    OpenType features are baked into the font file itself — a system font
    with a small glyph set may gray out most of the OpenType panel entirely.
    Professional/premium typefaces (and most fonts licensed specifically for
    branding work) tend to have the fullest feature sets.

## 2. Paragraph styles

A **Character Style** (Level 1, Module 7) applies to a run of selected
text. A **Paragraph Style** applies to whole paragraphs at once — indents,
spacing before/after, alignment, and hyphenation — and can reference a
Character Style inside it, so one click sets both.

1. Format one paragraph exactly the way you want a repeating block of text
   to look (body copy, a caption, a pull-quote).
2. Open **Window > Type > Paragraph Styles**, click the panel menu (top-right
   ≡ icon) and choose **New Paragraph Style** — or click the **New Style**
   icon at the bottom of the panel to base a new style directly on your
   formatted paragraph.
3. In the style's options, set a **Based On** style if you're building a
   family of related styles (e.g. `Body Copy` as the base, `Body Copy —
   Indent` based on it with only the indent changed) — editing the base
   style later cascades the shared properties down to anything based on it.
4. Click a saved Paragraph Style's name in the panel while a paragraph (or
   multiple paragraphs) is selected to apply every property at once.
5. If a style's name shows a **+** after applying it, the selected text has
   manual overrides on top of the style — click the panel menu's **Clear
   Override** (or Option/Alt-click the style name) to strip local formatting
   back to exactly what the style defines.

## 3. Outlining type and vector type effects

Converting text to paths trades away further text-editing for full vector
control — reshaping individual letterforms, combining them with Pathfinder,
or distorting them as a group the same way any other artwork can be
distorted.

1. Select a text object with the **Selection tool** (**V**), then **Type >
   Create Outlines** (**Shift+⌘/Ctrl+O**). Each character becomes its own
   compound vector path, grouped together — the text is no longer editable
   as text, so do this on a duplicate (**⌘/Ctrl+C**, **⌘/Ctrl+F** to paste
   in front) and keep the original live text layer hidden as a backup.
2. With letters outlined, use **Pathfinder** (Level 1, Module 7) to fuse a
   wordmark's letters into an icon shape, or **Minus Front** to cut a
   letterform's outline out of a solid background shape (a common
   badge/emblem technique).
3. For non-destructive distortion instead of outlining, select the live
   text object and use **Object > Envelope Distort > Make with Warp**
   (choose a shape like **Arc** or **Flag** and set **Bend** percentage) to
   curve or flex the whole text block while it's still editable — double-
   click the enveloped object later to edit the underlying text, or
   **Object > Envelope Distort > Release** to undo it entirely.
4. **Effect > Warp** (e.g. **Warp > Arc**) applies a similar distortion as a
   live, undoable **Appearance** effect (Module 4 of this level) rather than
   baking it into the object's geometry — visible and editable in the
   **Appearance panel**, removable at any time by deleting that effect
   entry.
5. Once outlined and finalized, group the result (**Object > Group**,
   **⌘/Ctrl+G**) and consider saving it as a **Graphic** asset in your
   Creative Cloud Library (Level 1, Module 9) if it's a logotype you'll
   reuse.

!!! warning "Outlining is a one-way door for that copy"
    Once a path is outlined, there is no menu command to turn it back into
    live, re-editable text with its original font reference — you'd have to
    retype it from scratch. Always outline a duplicate, never your only
    copy of the live text.

## 4. Worked example: a stylized wordmark

1. Set a short word (a brand name, 4-8 letters) in a heavier display
   weight, using a **Stylistic Set** if the font offers one that changes the
   look meaningfully (Section 1).
2. Duplicate the text object, then **Create Outlines** (**Shift+⌘/Ctrl+O**)
   on the duplicate, keeping the original hidden underneath as a fallback.
3. Select two adjacent letters that visually connect well (e.g. a
   descender that could tuck under the next letter) and use **Pathfinder >
   Unite** to fuse them into one custom ligature shape.
4. Apply **Effect > Warp > Arc** with a small **Bend** value (5-10%) for a
   subtle curve across the whole wordmark, rather than a flat baseline.
5. Group the result and save it into your Library as a **Graphic** asset
   (Level 1, Module 9), the same mechanism the Level 1 capstone used for a
   logo.

## Cheat sheet

| Action | Where |
|---|---|
| OpenType panel | Window > Type > OpenType |
| Glyphs panel (pick one alternate character) | Window > Type > Glyphs |
| Paragraph Styles panel | Window > Type > Paragraph Styles |
| Character Styles panel | Window > Type > Character Styles |
| Create Outlines | Shift+⌘/Ctrl+O |
| Envelope Distort with Warp | Object > Envelope Distort > Make with Warp |
| Release Envelope Distort | Object > Envelope Distort > Release |
| Live (editable) warp effect | Effect > Warp > [shape] |
| Clear a paragraph style override | Option/Alt-click the style name |

## How It Actually Works

- **OpenType features are lookup tables baked into the font binary, applied
  by substitution rules — not separate glyph shapes Illustrator draws
  itself.** An OpenType font stores its glyphs plus a set of GSUB
  (glyph substitution) rules keyed to feature tags like `liga` (standard
  ligatures), `swsh` (swashes), or numbered `ss01`-`ss20` (stylistic sets).
  Turning on a feature tells Illustrator's text engine to apply that rule
  table during layout: wherever the input glyph sequence matches a rule's
  trigger pattern (e.g. "f" followed by "i"), it substitutes the single
  pre-drawn ligature glyph the font author designed for that pair. A font
  with no such tables simply has nothing for the feature checkbox to
  trigger, which is the real reason it grays out rather than doing nothing
  visually.
- **A Paragraph Style cascading from a "Based On" parent works through
  property inheritance, not a copy made at creation time.** A child style
  stores only the properties that differ from its parent, plus a reference
  to the parent style; when Illustrator renders text using the child style,
  it resolves any unset property by walking up to the parent. That's
  mechanically why editing the base style's shared properties later
  propagates to every style built on it — you're editing the one place
  those inherited values actually live, not many independent copies.
- **The "+" override indicator exists because styles and direct formatting
  are stored in separate layers of the same text object.** Applying a style
  writes a reference to that style's property set; manually changing a
  property afterward (bolding one word inside a styled paragraph, say)
  writes a *local override* on top, without altering the style reference
  itself. Clear Override deletes only that local-override layer, which is
  why the text snaps back to exactly what the named style defines rather
  than to some undo history state.
- **Create Outlines converts each glyph's own internal contour data into
  ordinary Illustrator paths — it isn't approximating the letterform, it's
  extracting the literal outline the font already stores.** Every glyph in
  a font (TrueType or OpenType) is itself defined as one or more closed
  Bézier or quadratic contours (the same math from Module 3's "How It
  Actually Works" on paths) plus advance-width metadata for spacing. Create
  Outlines copies those exact contours into your document as compound
  paths and discards the font reference and its layout metadata (kerning
  tables, ligature rules, style hierarchy) — which is precisely why the
  result is pixel-for-pixel identical in shape to the live text, and
  precisely why it can never be reversed back into an editable font
  reference: that reference was deleted, not hidden.
- **Envelope Distort and live Warp effects reshape the *rendered* output
  through a mesh or arc transform applied at display time, leaving the
  original object's data untouched underneath.** An Envelope wraps the
  object in a deformation mesh whose control points bend the coordinate
  space the object is drawn into; Illustrator recalculates the object's
  appearance against that warped mesh on every redraw, without altering the
  object's own stored geometry (or, for live text, its font reference) at
  all. That's the structural reason double-clicking through an envelope
  still finds fully live, re-editable text, and why Release simply discards
  the mesh with nothing left to reconcile.

## Exercise

Set a short headline and turn on at least one OpenType feature the font
supports (a ligature or stylistic set) via the OpenType panel. Build a
Paragraph Style from a formatted body-copy paragraph and apply it to two
separate paragraphs so both update together. Then duplicate a short
wordmark, create outlines on the copy, fuse two letters with a Pathfinder
operation, and apply a live Warp or Envelope Distort effect to the group.
