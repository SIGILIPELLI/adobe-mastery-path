# 09 · Premiere Titles & Essential Graphics

Level 1 covered cutting, correcting, and mixing footage. This module covers
putting text and graphics on screen properly using the **Essential
Graphics** panel — building a title, keeping it positioned correctly at any
output size with **Responsive Design**, and packaging a finished title as a
reusable **Motion Graphics Template (.mogrt)**.

## 1. Essential Graphics panel basics

1. Open **Window > Essential Graphics**. The panel has two tabs: **Browse**
   (installed templates, covered in Section 3) and **Edit** (building a new
   graphic on the current sequence).
2. With the playhead positioned where you want a title to start, click
   **New Layer** at the bottom of the Edit tab (or use the **Graphics**
   menu) and choose **Text** to add an editable text layer directly on the
   Program Monitor, or **Rectangle**/**Ellipse**/**Line** for a supporting
   shape behind it.
3. Every graphic layer you add appears both in the Essential Graphics
   panel's layer list and as its own clip on a new video track above your
   footage — select a layer in either place to edit its properties in the
   Edit tab (font, size, color, alignment) or reposition it directly in the
   Program Monitor.
4. Use **Align** controls in the Edit tab to snap a layer to the frame's
   center, edges, or to another selected layer — faster and more precise
   than dragging by eye.
5. To keep a headline style consistent across multiple titles, format one
   text layer the way you want it, then in the **Effect Controls** panel's
   **Text** section use the **Master Text Styles** dropdown to save it —
   apply that saved style to any other text layer in one click, the same
   idea as an Illustrator Character Style (Level 1, Module 7).

## 2. Responsive Design

A title built for one frame size can end up misplaced or oddly sized if the
sequence's resolution changes, or if the clip's duration gets trimmed.
**Responsive Design** solves both problems.

1. **Responsive Design — Position**: with a graphic layer (or a whole group
   of layers, e.g. a background shape plus its text) selected, check
   **Responsive Design — Position** in the Edit tab and set **Pin To** —
   e.g. pinning a lower-third to the bottom-left of frame keeps it anchored
   there and correctly scaled even if the sequence is later reframed to a
   different aspect ratio or resolution.
2. **Responsive Design — Time**: check this option and set **Roll In** /
   **Roll Out** durations so that a title reveals and clears gracefully
   whenever the graphic clip is trimmed shorter or longer on the timeline,
   instead of a static graphic just appearing/disappearing at whatever
   frame the clip happens to start/end.
3. Group related layers (select them, then **Graphics > Group**) before
   applying Responsive Design so a background shape and its text move,
   scale, and pin together as one unit rather than needing the same
   settings applied to each layer separately.

## 3. Motion Graphics Templates (.mogrt)

A finished graphic can be packaged as a **Motion Graphics Template** — a
single portable file that exposes just the properties you choose (text,
color, a logo placeholder) for someone to edit later without touching the
underlying layer structure.

1. With a graphic clip selected on the timeline (or its layers built in the
   Essential Graphics Edit tab), click **Export Motion Graphics Template...**
   (also reachable by right-clicking the clip on the timeline).
2. Choose a destination: **Local Templates Folder** (available to Browse on
   this machine), a **Creative Cloud Library** (shareable across your
   Adobe account and collaborators, same mechanism as Level 1, Module 9),
   or **Local Drive** to save a standalone `.mogrt` file.
3. In the Essential Graphics Edit tab before exporting, decide which
   properties should stay editable in the packaged template (text content,
   a specific color swatch, a logo placeholder layer) versus which should
   be locked — this is what keeps a template safe to hand to someone
   without design authority to restructure it.
4. To reuse a saved template: open the Essential Graphics panel's **Browse**
   tab, find it under **Local Templates** or your Creative Cloud Library,
   and drag it directly onto the timeline — it drops in as a graphic clip
   with only its exposed properties editable in the Edit tab, exactly as
   configured when it was exported.

## 4. Basic keyframed motion on a title

1. Select the graphic clip on the timeline and open **Effect Controls**.
   Twirl open its **Motion** properties (**Position**, **Scale**) or
   **Opacity**.
2. Move the playhead to the point where the animation should start, click
   the **stopwatch** icon next to the property (e.g. Opacity) to enable
   keyframing and set the first keyframe automatically at the current
   value.
3. Move the playhead further along the clip and change the property's
   value (e.g. Opacity from 0 to 100) — Premiere adds a second keyframe
   automatically, and interpolates smoothly between the two.
4. This is the same underlying keyframe mechanism used for audio volume in
   Level 1, Module 8 — just applied to a visual property instead of volume.

## 5. Worked example: a reusable lower-third

1. Add a **Rectangle** graphic layer as a solid background bar near the
   bottom of frame, then a **Text** layer on top for a name/title.
2. Set the rectangle's color from your brand palette (matching a Creative
   Cloud Library swatch, Level 1 Module 9, by hex value if Libraries colors
   aren't directly exposed in your Premiere version's color picker), and
   apply a saved **Master Text Style** to the text layer.
3. Group both layers, check **Responsive Design — Position** and pin to
   bottom-left, and check **Responsive Design — Time** with a short **Roll
   In**/**Roll Out** so it animates cleanly regardless of clip length.
4. Keyframe **Opacity** from 0 to 100 over the first half-second for a
   gentle fade-in, mirroring the fade-out at the clip's end.
5. Export it as a **Motion Graphics Template** to your Creative Cloud
   Library, exposing just the name text and the bar's color as editable
   properties, then confirm it appears under **Browse** and drops onto a
   new timeline correctly.

## Cheat sheet

| Action | Where |
|---|---|
| Essential Graphics panel | Window > Essential Graphics |
| Add a new text/shape layer | Essential Graphics (Edit tab) > New Layer |
| Save a reusable text style | Effect Controls > Text > Master Text Styles |
| Pin a graphic's position | Edit tab > Responsive Design — Position |
| Auto roll-in/out on trim | Edit tab > Responsive Design — Time |
| Export a Motion Graphics Template | Right-click graphic clip > Export Motion Graphics Template |
| Browse/reuse saved templates | Essential Graphics > Browse tab |
| Keyframe a property (Position/Scale/Opacity) | Effect Controls > stopwatch icon next to the property |

## Exercise

Build a lower-third title with a background shape and a text layer in
Essential Graphics. Apply Responsive Design — Position (pinned to a
corner) and Responsive Design — Time with a short roll-in/roll-out. Add an
opacity fade-in using keyframes in Effect Controls. Export the result as a
Motion Graphics Template, then confirm it appears in the Browse tab and can
be dragged onto a different sequence with its text still editable.
