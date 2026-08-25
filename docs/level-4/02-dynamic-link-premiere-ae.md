# 02 · Dynamic Link: Premiere ↔ After Effects

This module covers **Dynamic Link**, the live connection between Premiere
Pro and After Effects that skips the render-export-import cycle entirely —
edit a composition in AE and the change appears in Premiere's timeline
(and vice versa) the moment you switch back, with no intermediate file.

## 1. Sending a Premiere sequence to After Effects

1. In Premiere, select a sequence in the Project panel (or right-click a
   clip/selection on the timeline) and choose **Edit > Replace with After
   Effects Composition...** (or right-click a sequence > **Replace with
   After Effects Composition**).
2. Premiere creates a new After Effects project (or adds to one, if
   prompted) containing a composition that mirrors the sequence, and
   replaces that clip in the Premiere timeline with a Dynamic Link
   placeholder pointing at the new AE comp.
3. This is the direction to use when a shot needs After Effects-only work
   — heavy compositing, tracking, or an expression-driven effect that
   Premiere's Essential Graphics can't do — without leaving Premiere's
   edit permanently to work in a separate render pipeline.

## 2. Importing an After Effects composition into Premiere

1. Alternatively, build the composition entirely in After Effects first,
   save the AE project, then in Premiere use **File > Import...** and
   select the `.aep` project file.
2. Choose the specific composition(s) to import from the dialog that
   appears — each selected comp is added to the Premiere Project panel as
   a Dynamic Link item, and can be dragged onto a Premiere timeline
   exactly like a regular clip.
3. This direction suits motion graphics built independently of a specific
   edit (a title template, a lower-third system, an animated logo sting)
   meant to be reused across multiple Premiere projects.

## 3. Editing the linked composition

1. Double-click the Dynamic Link clip on the Premiere timeline (or
   right-click > **Edit Original**) — After Effects opens (or comes to the
   front if already running) directly on that composition.
2. Make any edit in After Effects — keyframes, effects, text, timing — and
   save the AE project (**Ctrl/Cmd+S**).
3. Switch back to Premiere: the timeline clip updates automatically to
   reflect the AE changes, generally within a few seconds as Dynamic Link
   re-renders a preview in the background — no manual re-import or
   re-render step.

## 4. Performance considerations

1. Dynamic Link clips are computationally heavier to preview than native
   Premiere clips, since Premiere is asking After Effects to render frames
   live in the background — expect slower playback on longer or more
   complex compositions, especially with multiple Dynamic Link clips in
   one sequence.
2. For final delivery, **File > Export Media** in Premiere renders the
   Dynamic Link content in fully, so temporary Dynamic Link playback
   slowness has no effect on final output quality — it's a working-preview
   cost, not a quality cost.
3. If working on a slower machine, render a **preview** of the Dynamic
   Link clip (right-click > **Render and Replace**, or use a Preview
   render) to substitute a temporary flattened file for smooth scrubbing
   while editing the surrounding sequence, then revert to the live link
   before final delivery if further AE changes might still be needed.

## 5. Consolidating and troubleshooting links

1. **Edit > Preferences > Media** (or **Media Cache** preferences) affects
   how Dynamic Link previews are cached; clearing the media cache can
   resolve a Dynamic Link clip that's stuck showing an outdated preview.
2. If After Effects doesn't launch or the link breaks (e.g. the `.aep`
   file was moved), right-click the Dynamic Link clip in Premiere >
   **Restore Media...** to relink to a valid `.aep` file/composition.
3. Keep the linked `.aep` project and the Premiere project in a stable,
   shared project folder (per Module 1's folder conventions) — moving the
   AE project file independently is the most common cause of a broken
   Dynamic Link.

## Worked example: an AE title sting inside a Premiere cut

1. In After Effects, build a 3-second animated title sting (reusing the
   parenting/easing/expression techniques from Level 3) and save the
   project into the campaign's shared project folder.
2. In Premiere, **File > Import...** the `.aep` file and select the title
   sting composition, then drag it onto the sequence at the intro point.
3. Play through the edit; if the title's timing feels off against the cut,
   double-click the Dynamic Link clip to jump into AE, retime the
   keyframes, save, and confirm the Premiere timeline updates without
   re-importing.
4. Once locked, export the full sequence via Export Media — Premiere
   renders the AE content into the final file at full quality.

## Cheat sheet — Dynamic Link

| Task | Where |
|---|---|
| Send a Premiere sequence to AE | Edit > Replace with After Effects Composition... |
| Bring an AE comp into Premiere | File > Import... the .aep file, pick composition(s) |
| Jump into AE to edit a linked clip | Double-click the clip, or right-click > Edit Original |
| Speed up scrubbing on a heavy link | Right-click > Render and Replace |
| Fix a broken link | Right-click clip > Restore Media... |
| Final full-quality render | File > Export Media (Premiere renders AE content in) |

## Exercise

Build a short composition in After Effects, import it into a Premiere
sequence via Dynamic Link, and edit the sequence around it. Double-click
back into After Effects, change the timing or a keyframe, save, and
confirm the Premiere timeline reflects the change without a manual
re-import. Export the final sequence and confirm the Dynamic Link content
renders at full quality in the output file.
