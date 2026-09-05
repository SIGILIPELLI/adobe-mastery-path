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

## How It Actually Works

- **Interpolation between two keyframes is literally curve-fitting a
  function through two (value, time) points, and every interpolation type
  is just a different family of curve.** Linear connects them with a
  constant-slope straight line — equal time steps yield equal value
  changes, hence uniform speed and the "robotic" feel. Easy Ease fits a
  Bézier curve whose tangent (first derivative, i.e. velocity) is forced to
  zero at the keyframe, so the value's rate of change genuinely approaches
  zero as it nears that point — this is a real velocity calculation, not a
  cosmetic ease.
- **The Speed Graph is the literal first derivative of the Value Graph,
  which is why it's more intuitive for tuning ease.** The Value Graph plots
  the property's value over time; differentiating that curve with respect
  to time gives instantaneous velocity, which is exactly what the Speed
  Graph displays directly. A flat zero on the Speed Graph at a keyframe
  means the Value Graph's slope is zero there (motion has actually stopped,
  not just slowed near-imperceptibly), and dragging a Bézier handle on
  either graph reshapes the same underlying curve — you're just looking at
  two different derivatives of one mathematical object.
- **A spatial motion path is the Position property's value curve rendered
  directly in 2D/3D space instead of on a time axis** — because Position
  has two or three simultaneous numeric channels (x, y, [z]), After Effects
  draws the parametric curve those channels trace through space rather than
  a single value-over-time line, with per-frame dot spacing encoding speed:
  since frames are evenly spaced in time, dots bunched close together
  mean the position curve is covering less distance per frame, i.e. moving
  slower at that point in the path.
- **Roving keyframes solve a real timing-distribution problem: without
  them, each keyframe's *time* is fixed, so an intermediate point on a
  curved path forces a deceleration/acceleration at that exact frame
  regardless of the path's shape.** Marking a keyframe as roving tells
  After Effects to treat its *value* (spatial position on the path) as
  fixed but let its *timing* float, then redistributes timing across all
  roving keyframes so that equal path-distance is covered in equal time —
  a numeric solve, not a preset, over the arc length of the spatial curve
  between the fixed endpoint keyframes.
- **Motion Sketch works by recording your mouse's position at the
  application's frame rate while you drag, and writing one keyframe per
  sampled frame.** That's why freehand Motion Sketch output tends to be
  noisy/jittery compared to hand-placed keyframes — every small mouse
  tremor becomes a literal keyframe — and why a Smoother pass (Keyframe
  Assistant) afterward is standard: it's a real curve-smoothing algorithm
  reducing the keyframe count and fitting a gentler curve through the
  captured points, not just relabeling the same data.

## Exercise

Animate the title card's entrance with at least three eased properties
(Position, Opacity, and one more — Scale or Rotation). Use the Graph
Editor's Speed Graph to confirm every property ramps in and/or out
smoothly with no linear (robotic) segments, and stagger the logo's entrance
slightly after the text using Sequence Layers or manual retiming.
