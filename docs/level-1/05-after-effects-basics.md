# 05 · After Effects Basics

After Effects is Adobe's motion graphics and compositing tool — where
Premiere Pro arranges whole clips in sequence, After Effects animates
individual properties (position, opacity, scale, and more) of layers over
time, frame by frame. This module covers the workspace, the
timeline/keyframe concept, and building one simple animation: a text layer
that fades and moves in.

## 1. Workspace tour

1. Open After Effects and create a new project: **File > New > New
   Project**, then **Composition > New Composition** (⌘/Ctrl+N).
2. In the Composition Settings dialog, set a **Preset** (e.g. HDTV
   1080p 25 or 29.97), a **Duration** (e.g. 5 seconds), and click **OK**.
   A **composition** ("comp") is After Effects' unit of work — similar to a
   Premiere sequence, but built for layering and animating rather than
   cutting between long clips.
3. The default workspace has:
   - **Project panel** (top-left) — imported footage and comps, like
     Premiere's Project panel.
   - **Composition viewer** (top-center) — the visual preview of your comp.
   - **Timeline panel** (bottom) — layers stacked vertically, time running
     left to right, with a **keyframe** track for each animated property.
   - **Effects & Presets / other panels** (right) — searchable list of
     effects you drag onto layers.
4. **Window** menu shows/hides any panel; **Window > Workspaces > Reset
   "Standard" to Saved Layout** restores the default arrangement.

## 2. The timeline and keyframes concept

This is the core idea that makes After Effects different from Premiere:
**every property of a layer — position, scale, rotation, opacity, and much
more — can be animated by setting keyframes**, which are snapshots of that
property's value at a specific point in time. After Effects automatically
calculates ("interpolates") the in-between values, producing smooth motion.

1. Select a layer in the timeline, then press a shortcut to reveal one
   property directly under it: **P** for Position, **S** for Scale, **R**
   for Rotation, **T** for Opacity. (Press the same letter again to hide
   it; Shift-click a second letter to reveal multiple properties at once.)
2. Move the **playhead** (drag the blue marker along the timeline ruler, or
   click a specific timecode) to the point in time where you want a
   keyframe.
3. Click the **stopwatch icon** next to the property name to enable
   keyframing and place your first keyframe at the current value and time.
4. Move the playhead to a later point, then simply change the property's
   value (drag the number, or type a new one) — After Effects
   automatically adds a new keyframe there, since keyframing is already
   enabled for that property.
5. Scrub the playhead back and forth (or press **Spacebar** to play) to
   preview the animation between your keyframes.

!!! info "A minimum of two keyframes"
    A single keyframe just sets a fixed value with no motion — you need at
    least two keyframes on the same property, at two different points in
    time and with two different values, for anything to actually animate.

## 3. Building a simple animation: fade and move a text layer

1. **Layer > New > Text** (or press **T** for the Type tool and click on
   the composition viewer), then type your text. A new text layer appears
   in the timeline.
2. Set the layer's starting state: move the playhead to time `0:00`, select
   the layer, press **P** to reveal Position and drag the text off to one
   side in the viewer; press **T** to reveal Opacity and set it to `0%`.
3. Enable keyframing on both properties at this starting point by clicking
   each stopwatch icon — this places your "before" keyframes.
4. Move the playhead forward (e.g. to `1:00`, one second in). Drag the text
   to its final on-screen position, and set Opacity back to `100%`. Because
   keyframing is already enabled, both changes automatically create a
   second keyframe at this new time.
5. Scrub the playhead from `0:00` to `1:00` — the text should fade in while
   sliding into place. If the motion feels linear/robotic, select both
   keyframes on a property (drag a box around them in the timeline), then
   right-click > **Keyframe Assistant > Easy Ease** (or **F9**) to smooth
   the acceleration at the start and end of the motion.
6. Preview the full composition with **Spacebar**, or press **0** on the
   numeric keypad to RAM Preview it at full speed with audio if present.

## 4. Getting your comp out of After Effects

For now, the simplest path is **Composition > Add to Render Queue**, then
in the Render Queue panel click the blue **Output Module** link to choose a
format (e.g. H.264 for a shareable MP4) and click **Render**. Deeper
render-settings control, and passing a comp directly into Premiere via
Dynamic Link, are covered later in this series (Level 4, Module 2) — for
this module, a rendered preview file is all you need.

## Cheat sheet

| Action | Shortcut |
|---|---|
| New composition | ⌘/Ctrl+N |
| New text layer | T (Type tool), or Layer > New > Text |
| Reveal Position property | P |
| Reveal Scale property | S |
| Reveal Rotation property | R |
| Reveal Opacity property | T |
| Reveal multiple properties at once | Shift-click additional letter keys |
| Enable keyframing on a property | Click its stopwatch icon |
| Smooth a keyframe's ease | F9 (Easy Ease) |
| Play from playhead | Spacebar |
| RAM Preview (full speed) | 0 (numeric keypad) |
| Add comp to Render Queue | Composition > Add to Render Queue |

## How It Actually Works

- **Interpolation is curve-fitting between numeric values, and "linear" is
  the default curve.** With two keyframes set, After Effects doesn't
  actually store any of the in-between frames — it computes each one on the
  fly by evaluating a function of time between the two keyframe values.
  With no easing applied, that function is linear: equal time steps produce
  equal changes in value, which is exactly why default motion feels robotic
  — it starts and stops instantly at full speed with no acceleration or
  deceleration, unlike real-world motion.
- **Easy Ease reshapes the velocity curve, not the position values you
  set.** Pressing F9 doesn't move your keyframes' values or timing; it
  changes each keyframe's incoming/outgoing tangent handles on the
  underlying Bézier interpolation curve so velocity approaches zero near the
  keyframe instead of holding constant — visible directly in the Graph
  Editor as the value curve flattening out at both ends into an S-shape
  instead of a straight diagonal line.
- **Composited layers are evaluated top-down, per frame, through each
  layer's full property stack.** For every frame you scrub to, After
  Effects walks the layer stack from top to bottom, evaluates each layer's
  animated transform properties and effects at that exact time, rasterizes
  each into an intermediate buffer, then composites them together according
  to blend mode and opacity — which is why stacking order matters
  identically to Photoshop layers, and why RAM Preview (numeric 0) exists
  separately from Spacebar: it pre-renders every frame into memory first so
  playback isn't bottlenecked by that per-frame composite math happening
  live.
- **A composition is itself a kind of layer, which is why nesting works.**
  Internally, a comp is just another asset with a duration and a rendered
  output — when you drag one comp into another as a "precomp" layer
  (a pattern you'll use heavily from Level 3 onward), After Effects treats
  it exactly like any footage layer: it evaluates the entire nested comp's
  stack first to produce a flattened frame, then composites that frame into
  the parent, same as it would a video clip.
- **The Render Queue is a separate, deterministic re-evaluation pass, not a
  recording of your preview.** Rendering doesn't capture what you saw while
  scrubbing; it walks the composition frame-by-frame from time zero,
  re-evaluating every layer's properties and effects at each exact frame
  time and encoding the result directly to the output format — which is why
  a render can look different from a rough RAM Preview if a property
  depends on something view-dependent (like a resolution/quality setting)
  that differs between the interactive viewer and the Output Module
  settings.

## Exercise

Create a new 5-second composition. Add a text layer with your name or a
short phrase. Animate it to fade in from 0% to 100% opacity while sliding
in from off-screen, using at least two keyframes each on Position and
Opacity, starting at `0:00` and ending by `1:00`. Apply Easy Ease (F9) to
all four keyframes and compare the motion before and after. Add the comp to
the Render Queue and render it as an H.264 MP4.
