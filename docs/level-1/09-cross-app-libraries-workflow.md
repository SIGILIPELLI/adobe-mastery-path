# 09 · Cross-App Creative Cloud Libraries Workflow

Module 1 set up a Creative Cloud Library. This module puts it to real use:
sharing one consistent set of brand colors, a character style, and a
graphic across Photoshop, Illustrator, and Premiere Pro — so a color you
pick once in Illustrator shows up identically, and stays editable, in the
other two apps. This is the exact mechanism the Module 10 capstone builds
on.

## 1. Why a shared Library beats manual copy-paste

Copying a hex color code by hand into three different apps' color pickers
works, until the color changes — then you're hunting down every place it
was pasted and updating each one manually, and a typo in any single app
throws the whole set out of sync. A Library asset is a **live reference**:
update the swatch once, and (depending on the asset type) every place it's
been used can be refreshed to match, all from one source of truth.

## 2. Setting up brand colors as shared swatches

1. In Illustrator (or Photoshop — the panel is identical), open **Window >
   Libraries** and select the Library you created in Module 1 (`Mastery
   Path Brand Kit`) from the dropdown at the top.
2. Pick or define your brand colors in the **Color** panel (**Window >
   Color**), then drag each swatch directly from the Color panel into the
   Libraries panel — or use the eyedropper tool inside the Libraries panel
   to sample a color straight off an existing shape.
3. Name each swatch meaningfully (double-click its name in the Libraries
   panel) — e.g. `Brand Primary`, `Brand Accent`, `Brand Neutral` — rather
   than leaving default names like "Untitled Color 1."
4. Switch to Photoshop, open **Window > Libraries**, and select the same
   Library — the same named swatches appear immediately, synced through
   your Adobe account rather than copied by hand.
5. In Premiere Pro, Libraries assets appear inside the **Essential
   Graphics** panel (**Window > Essential Graphics**) when you're editing a
   graphic/text layer's fill color — click the color swatch on a graphic's
   properties, and your Library's swatches are available there too under
   its color picker's Libraries tab (availability can vary slightly by
   Premiere version; if you don't see them there, apply the color manually
   using the same hex value shown in the Libraries panel).

## 3. Sharing a character style

1. In Illustrator, format a piece of text the way you want your brand's
   headline style to always look — font family, size, tracking, and color
   (using one of your Library color swatches for the fill, so the two stay
   linked).
2. With that text selected, click the **+ (Text)** button at the bottom of
   the Libraries panel — this saves the full formatting as a **Character
   Style** asset in your shared Library.
3. In Photoshop or Illustrator later, select any other text layer/object
   and click that Library Character Style asset to apply the exact same
   font, size, tracking, and color in one click, instead of resetting each
   property by hand.

## 4. Sharing a graphic across apps

1. In Illustrator, select a logo, icon, or shape group (**Object > Group**,
   ⌘/Ctrl+G, if it's multiple objects) you want reusable everywhere.
2. Drag it directly from the artboard into the Libraries panel — it's
   saved as a **Graphic** asset, still editable, not a flattened raster.
3. In Photoshop, drag that same Graphic asset out of the Libraries panel
   onto a canvas — it's placed as a **Smart Object**, linked back to the
   original Library asset. Double-click the Smart Object's thumbnail to
   edit the underlying artwork in Illustrator; save, and the placed
   instance in Photoshop updates.
4. In Premiere Pro, drag the Graphic asset from **Window > Libraries**
   directly onto the timeline — it's placed as a linked graphic clip you
   can position and scale like any other clip, and which can likewise be
   updated if the source Library asset changes.

## 5. Keeping everything in sync

1. Libraries sync automatically whenever you're signed in and online — a
   small sync-status icon on the Libraries panel (top-right) shows whether
   it's up to date, syncing, or has a conflict to resolve.
2. If you edit an asset (e.g. update a swatch's exact hex value) in one
   app, that change propagates to every other app's Libraries panel once
   sync completes — but instances of a **Graphic** already placed on a
   canvas need an explicit refresh: right-click the placed instance and
   look for an **Update** or **Relink** option if it doesn't refresh
   automatically.
3. Libraries are also how you hand off brand assets to a collaborator —
   share the Library itself (the Libraries panel dropdown has an **Invite
   People** / share option) rather than exporting and emailing individual
   files, so both people always work from the same current version.

## Cheat sheet

| Action | Where |
|---|---|
| Open Libraries panel | Window > Libraries |
| Select which Library is active | Libraries panel > top dropdown |
| Save a color swatch | Drag from Color panel, or use the eyedropper, into Libraries |
| Save a character/text style | Select text > Libraries panel > + (Text) |
| Save a graphic | Drag a shape/group into the Libraries panel |
| Use a Library graphic in Photoshop | Drag from Libraries onto canvas (becomes a Smart Object) |
| Use a Library graphic in Premiere | Drag from Libraries onto the timeline |
| Access Library colors in Premiere | Window > Essential Graphics > color swatch > Libraries tab |
| Share a Library with a collaborator | Libraries panel dropdown > Invite People |

## Exercise

Using the `Mastery Path Brand Kit` Library from Module 1: add two more
named color swatches (a primary and an accent), one saved character style,
and one saved graphic (a simple shape or icon from Illustrator). Confirm
all three appear in Photoshop's Libraries panel. Drag the graphic asset
onto a new Photoshop canvas as a Smart Object, then double-click it to
confirm it opens the source artwork in Illustrator for editing. You'll
reuse this exact Library, unchanged, in the Module 10 capstone.
