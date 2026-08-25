# 02 · After Effects Keyframing & Easing

Module 1 set static Transform values. Real motion graphics work is about
values that *change over time* — a title sliding in, a logo scaling up, an
element fading out — and about making those changes feel natural rather
than robotic. This module covers keyframing any property and shaping its
motion with the Graph Editor and easing presets.

## 1. Setting your first keyframes

1. Select a layer, move the playhead to where the animation should start,
   twirl open the property to animate (e.g. press **P** for Position), and
   click the **stopwatch** icon next to the property name — this creates
   the first keyframe at the current value and time, and switches the
   property into "animated" mode.
2. Move the playhead forward (e.g. 1 second later), then simply change the
   property's value — After Effects automatically adds a second keyframe
   at the new time/value; you do **not** need to click the stopwatch
   again once it's enabled.
3. Keyframes appear as small icons on the property's row in the Timeline.
   Drag them left/right to retime, or select and **Delete** to remove.
4. Use **K** and **J** to jump the playhead forward/backward to the next
   or previous keyframe on the selected layer.

## 2. Keyframe interpolation types

1. Right-click a keyframe > **Keyframe Interpolation...** for full control,
   or use the quick shortcuts:
   - Default new keyframes are **Linear** (constant speed, straight line
     in the graph, and a visually "robotic" start/stop).
   - **F9** applies **Easy Ease** to the selected keyframe(s) — speed
     ramps smoothly in and/or out, the standard default for natural
     motion.
   - **Shift+F9 / Ctrl+Shift+F9** apply **Easy Ease In / Easy Ease Out**
     to only one side of a keyframe.
   - **Hold** interpolation (right-click > Toggle Hold Keyframe) makes a
     value jump instantly at the keyframe with no interpolation at all —
     useful for stop-motion-style or strobing effects.

## 3. The Graph Editor

1. Click the **Graph Editor** button (the small chart icon) at the top of
   the Timeline panel to switch the keyframe view into a value or speed
   graph.
2. Switch between **Edit Value Graph** and **Edit Speed Graph** from the
   graph's panel menu (the icon at bottom-right of the Graph Editor) —
   the Speed Graph is usually more intuitive for easing since it plots
   velocity directly: a flat line at zero at a keyframe means the motion
   fully stops there, a tall smooth hump means fast motion through the
   middle.
3. Drag the Bezier handles that extend from an eased keyframe to fine-tune
   exactly how sharply or gently speed ramps in and out — a short, steep
   handle gives a snappy start; a long, shallow handle gives a slow,
   gentle one.
4. Click **Snap** and **Auto-Zoom Graph Height** (icons along the graph's
   toolbar) to keep the curve readable while adjusting.

## 4. Spatial keyframes and motion paths

1. For a spatial property like Position, keyframes also draw a **motion
   path** directly in the Composition panel — a dotted line with a dot per
   frame, closer-together dots meaning slower motion.
2. Drag the path's Bezier handles at a keyframe point to curve the motion
   itself (not just its speed) — useful for an arc instead of a straight
   line between two points.
3. **Roving keyframes** (right-click a middle keyframe on the motion path
   > **Rove Across Time**) let After Effects redistribute timing along a
   path automatically for constant speed through a curve, rather than
   easing/slowing at every intermediate point.

## 5. The Motion Sketch and Keyframe Assistant helpers

1. **Window > Motion Sketch** lets you drag the layer live in the
   Composition panel while recording, generating a full set of position
   keyframes from the drag in real time — fast for organic, hand-drawn
   motion.
2. **Animation > Keyframe Assistant > Easy Ease** (same as F9) and **>
   Sequence Layers** (auto-offsets a set of selected layers' in/out points
   one after another, handy for staggering multiple text layers) live in
   the same menu.

## Worked example: easing the title card

1. Open the `Title_Card` composition from Module 1.
2. Set a Position keyframe on the text+logo group off-frame left at 0:00,
   and a second Position keyframe at its on-frame resting spot at 0:01:00.
3. Select both keyframes and press **F9** for Easy Ease.
4. Open the Graph Editor, switch to **Edit Speed Graph**, and drag the
   handle on the second (arrival) keyframe outward to make the deceleration
   longer and gentler, so the group settles into place rather than
   stopping abruptly.
5. Add an Opacity fade-in over the same range (0 to 100) for a combined
   slide + fade entrance.

## Cheat sheet — keyframing & easing

| Task | Where |
|---|---|
| Enable keyframing on a property | Click the stopwatch icon |
| Jump to next/previous keyframe | K / J |
| Apply Easy Ease | F9 |
| Easy Ease In only / Out only | Shift+F9 / Ctrl+Shift+F9 |
| Hold keyframe (instant jump) | Right-click keyframe > Toggle Hold Keyframe |
| Open Graph Editor | Graph Editor button, top of Timeline |
| Rove keyframes for constant speed | Right-click path keyframe > Rove Across Time |
| Freehand keyframes from a live drag | Window > Motion Sketch |

## Exercise

Animate the title card's entrance with at least three eased properties
(Position, Opacity, and one more — Scale or Rotation). Use the Graph
Editor's Speed Graph to confirm every property ramps in and/or out
smoothly with no linear (robotic) segments, and stagger the logo's entrance
slightly after the text using Sequence Layers or manual retiming.
