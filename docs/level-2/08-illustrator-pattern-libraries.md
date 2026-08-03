# 08 · Illustrator Pattern & Asset Libraries

Level 1's Creative Cloud Libraries (Module 9) shared colors, character
styles, and single graphics across apps. This module covers building
**repeatable pattern swatches** for backgrounds and packaging-style
artwork, the **Symbols** panel for reusable repeated instances within a
single file, and organizing a growing set of swatches and assets so a
larger project stays manageable.

## 1. Building a pattern swatch

1. Draw the artwork for one repeating tile — a small motif, a simple icon,
   or a few shapes — keeping it modest in size and detail, since it will
   repeat many times at whatever scale you apply it.
2. Select the artwork and choose **Object > Pattern > Make**. Illustrator
   adds the pattern to your Swatches panel immediately and enters a
   special pattern-editing mode (a gray "Pattern Editing Mode" bar appears
   at the top of the window) where you can see a live preview of the tile
   repeating around your original artwork.
3. The **Pattern Options** panel (**Window > Pattern Options** if it
   doesn't appear automatically) controls the tile type:
   - **Grid** — tiles repeat directly above/below and side-by-side, the
     simplest repeat.
   - **Brick by Row** / **Brick by Column** — offsets alternating rows or
     columns by half a tile, avoiding an obvious grid seam.
   - **Hex by Column** / **Hex by Row** — a honeycomb-style offset, good for
     organic or scale-like motifs.
4. Adjust **H Spacing**/**V Spacing** to add gaps between repeats, and
   **Overlap** to control which copy sits on top where tiles touch.
5. Click **Save a Copy** (or **Done**) in the gray bar at the top to exit
   pattern-editing mode and commit the swatch — it's now a regular entry in
   your **Swatches** panel (**Window > Swatches**), applicable to any
   object's fill like any other swatch.

## 2. Applying and scaling a pattern fill

1. Select any object and click the saved pattern swatch in the Swatches
   panel to fill it — the pattern tiles automatically to cover the
   object's shape.
2. To scale or rotate the pattern *without* changing the object's own
   size/rotation, select the **Scale tool** (**S**) or **Rotate tool**
   (**R**), and double-click its icon in the Toolbar to open the numeric
   dialog — uncheck **Transform Objects** and check **Transform Patterns**
   before applying, so only the tile inside the shape scales/rotates.
3. For a live, by-eye adjustment instead of the numeric dialog: hold **~**
   (tilde) while dragging with the Scale, Rotate, or Selection tool — the
   pattern transforms independently of the object's outline in real time,
   which is faster for judging a tile size visually against the object's
   actual dimensions.
4. A pattern-filled object can still have Appearance-panel effects (Module
   4) layered on top of it, exactly like a flat fill or gradient.

## 3. Symbols for repeated instances within a file

Where a pattern repeats a tile automatically to fill a shape, a **Symbol**
is a single reusable piece of artwork you place multiple times by hand —
useful for scattered repeated elements (icons across an infographic, trees
across a map) that a pattern's regular grid can't represent.

1. Select artwork and drag it into **Window > Symbols** (**Shift+⌘/Ctrl+F11**),
   or click the panel's **New Symbol** icon — name it and leave the type
   default unless you're specifically targeting Adobe Animate.
2. Drag the symbol out of the panel onto the canvas as many times as
   needed — each placed instance is linked back to the master symbol.
3. Double-click any placed instance to enter **Symbol Editing Mode** and
   edit the artwork directly — every other instance across the document
   updates to match once you exit, the same one-to-many update behavior as
   a Library Graphic asset (Level 1, Module 9), but scoped to this one file
   rather than shared across apps/documents.
4. The **Symbol Sprayer** tool (**Shift+S**) scatters multiple instances of
   the active symbol across the canvas in one dragging motion — useful for
   quickly populating a busy scene, with companion tools in the same
   toolbar group (Symbol Shifter, Sizer, Spinner, Stainer) to then vary
   their position, size, rotation, and tint by hand afterward.

## 4. Organizing swatches and sharing across apps

1. In the Swatches panel, select several related swatches (Shift-click or
   ⌘/Ctrl-click) and click the **New Color Group** folder icon to bundle
   them — useful once a project accumulates a full palette of patterns,
   solid colors, and gradients side by side.
2. Rename any swatch by double-clicking it — a pattern named "Pattern" by
   default becomes unmanageable fast across a file with several tiles; name
   each one for what it depicts (`Diagonal Stripe — Brand Blue`, not
   `Pattern 3`).
3. To make a pattern available in your Creative Cloud Library (Level 1,
   Module 9) rather than just this one document, drag the swatch from the
   Swatches panel directly into the **Libraries** panel — it saves as a
   **Graphic** asset representing that tile, which you can then drag onto a
   canvas in another Illustrator document (or as a Smart Object into
   Photoshop) and re-apply as a fill there.
4. Symbols don't carry across documents automatically the way Library
   assets do — if a symbol needs to be reused in a *different* file, save
   it into the Library as a Graphic asset as well (Section 3's linked-
   instance behavior only applies within one document).

## 5. Worked example: a packaging background pattern

1. Draw a small two-color motif (e.g. a leaf, a dot, a simple geometric
   mark) sized well below your final artwork's dimensions.
2. **Object > Pattern > Make**, set the tile type to **Brick by Row** with
   moderate spacing so the repeat doesn't read as an obvious grid, and save
   the swatch.
3. Fill a background rectangle with the new pattern swatch, then hold **~**
   while dragging with the Selection tool to scale the pattern down until
   the motif reads at an appropriate density for the rectangle's size.
4. Rename the swatch descriptively, group it with your brand's color
   swatches using **New Color Group**, and drag it into your Creative Cloud
   Library so the same background pattern is available for a matching
   Photoshop poster.

## Cheat sheet

| Action | Where |
|---|---|
| Create a pattern from selected artwork | Object > Pattern > Make |
| Pattern tile-type options | Window > Pattern Options (Grid/Brick/Hex) |
| Exit pattern-editing mode | "Save a Copy" / "Done" in the gray top bar |
| Scale/rotate pattern only, not the object | Double-click Scale/Rotate tool > uncheck Transform Objects |
| Live pattern-only transform while dragging | Hold ~ (tilde) while dragging |
| Symbols panel | Window > Symbols (Shift+⌘/Ctrl+F11) |
| Symbol Sprayer tool | Shift+S |
| Group related swatches | Swatches panel > New Color Group |
| Share a pattern across apps/documents | Drag swatch into the Libraries panel |

## Exercise

Design a small repeating motif and turn it into a pattern swatch using
Object > Pattern > Make, trying at least two different tile types (e.g.
Grid vs. Brick by Row) before picking one. Apply it to a background shape,
then scale the pattern independently of the shape using the tilde-drag
technique. Rename the swatch descriptively, group it with at least one
other swatch, and drag it into your Creative Cloud Library.
