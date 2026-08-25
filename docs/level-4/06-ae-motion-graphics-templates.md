# 06 · After Effects Motion Graphics Templates (Mogrts)

Level 2 built titles directly in Premiere's Essential Graphics panel. This
module covers the more powerful direction: building a title/graphic in
**After Effects** with exposed, editable controls, then exporting it as a
**Motion Graphics Template (.mogrt)** that a Premiere editor (with no AE
experience or even without After Effects installed) can drop in and
customize safely.

## 1. Building a template-ready composition in AE

1. Build the animated element normally (text, shapes, keyframed motion,
   per Level 3), but plan which properties an editor should be able to
   change later — typically headline text, a color or two, and maybe a
   duration/timing control — versus everything else, which should stay
   locked.
2. Open **Window > Essential Graphics**, choose the composition from its
   dropdown at the top, and it lists every layer in that comp on the left.
3. Select a layer (or a specific property on it, twirled open in the
   Timeline) and click **Add Property** in the Essential Graphics panel
   (or drag the property directly into the panel) to expose it as an
   editable control.

## 2. Choosing and organizing exposed controls

1. Exposed properties appear in the Essential Graphics panel's controls
   list with editable UI matching their type: a text field for a text
   layer's **Source Text**, a color swatch for a **Fill Color**, a slider
   for a numeric value, a checkbox for a boolean.
2. Rename each exposed control (double-click its label in the panel) to
   something clear for whoever uses the template later — `Headline`
   rather than `Text Layer 3`, `Accent Color` rather than `Fill Color`.
3. Reorder controls by dragging them in the panel's list — put the most
   commonly changed items (usually headline text) at the top.
4. Group related controls together with **Add Comment** entries (panel
   menu) as simple section labels if the template has many controls, e.g.
   separating "Text" controls from "Color" controls visually.

## 3. Exporting as a .mogrt

1. With the composition and its exposed controls set, click **Export
   Motion Graphics Template...** at the bottom of the Essential Graphics
   panel.
2. Choose a destination: **Local Templates Folder** (appears immediately
   in Premiere's own Essential Graphics browser on the same machine) or a
   specific file location/Creative Cloud Library (for sharing with a team,
   tying back into Module 4).
3. If the composition uses fonts, choose whether to **package the fonts**
   with the template (recommended for fonts that might not be installed on
   the editor's machine) — note that some licensed fonts restrict this, so
   check font licensing before bundling.

## 4. Using a .mogrt in Premiere

1. In Premiere, **Window > Essential Graphics > Browse** tab lists
   available templates (Local Templates Folder, Creative Cloud Libraries,
   and any linked online source); drag one directly onto the timeline like
   any clip.
2. Select the placed template on the timeline, switch to the **Edit** tab
   in Essential Graphics, and every control exposed back in AE (Module 2's
   list) appears here — headline text, colors, sliders — editable without
   ever opening After Effects.
3. **Master Properties**: if the same .mogrt is placed multiple times with
   different local edits, Premiere still allows per-instance overrides —
   each placed instance keeps its own values independently unless
   deliberately reset to the template's master.

## 5. Updating a template after it's already used

1. If the source AE project (with the same Essential Graphics setup) is
   edited and re-exported as a .mogrt with the same name/replacing the
   same file, existing Premiere projects using it can pick up the update
   via **right-click the placed template > Update Motion Graphics
   Template...** if prompted, or by re-browsing and re-placing it.
2. For an actively-used shared template (via a Team Library, Module 4),
   this means a designer can fix or refine a title system mid-project and
   push the update to every editor using it, similar in spirit to Dynamic
   Link but packaged as a portable, no-AE-required file rather than a live
   link.

## Worked example: a reusable lower-third template

1. In After Effects, build a lower-third: a background bar, a name text
   layer, and a title/role text layer, animated with an eased slide-in and
   fade (Level 3 techniques).
2. In Essential Graphics, expose the name text (`Name`), the role text
   (`Role`), and the bar's fill color (`Accent Color`) as controls; leave
   the animation timing itself locked (not exposed) so editors can't
   accidentally break the timing.
3. Export as a .mogrt to the Team Library from Module 4, so every editor
   on the project can drop it into their own Premiere sequence and fill in
   different names/roles while the animation and brand color system stay
   consistent.
4. In Premiere, place it three times for three different interview
   subjects, editing each instance's Name/Role/Accent Color independently
   via Master Properties overrides.

## Cheat sheet — Motion Graphics Templates

| Task | Where |
|---|---|
| Open Essential Graphics (AE) | Window > Essential Graphics |
| Expose a property as an editable control | Select property, Add Property (or drag into panel) |
| Rename an exposed control | Double-click its label |
| Export as .mogrt | Export Motion Graphics Template... button |
| Browse/place a template (Premiere) | Window > Essential Graphics > Browse tab |
| Edit a placed template's controls | Essential Graphics > Edit tab |
| Per-instance overrides on repeated placements | Master Properties |

## Exercise

Build a lower-third or title element in After Effects, expose at least
three controls (one text, one color, one numeric/slider) via Essential
Graphics, and export it as a .mogrt. Place it in a Premiere sequence at
least twice with different values on each instance, confirming both
instances animate identically while showing different text/color content.
