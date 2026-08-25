# 04 · After Effects Expressions Basics

Keyframes are hand-placed. **Expressions** are small pieces of JavaScript
that drive a property's value with code instead — useful for motion that
follows a rule (wiggle, loop, link to another layer) rather than a fixed
set of keyframes. This module covers writing, linking, and reusing basic
expressions.

## 1. Adding an expression to a property

1. Alt-click (Windows) / Option-click (Mac) the **stopwatch** icon next to
   any property — this doesn't add a keyframe, it opens an expression
   editor field directly beneath that property in the Timeline.
2. Type or paste an expression into the field, then click elsewhere (or
   press Enter on the numeric keypad) to apply it. A red expression icon
   (`=`) replaces the stopwatch to show the property is now
   expression-driven.
3. While an expression is active on a property, manual keyframes and the
   expression can coexist: use `value` inside the expression to reference
   the property's own keyframed value and modify it further (e.g. add a
   wiggle on top of an existing keyframed move).

## 2. The pick whip for linking properties

1. Every expression field has its own **pick-whip** spiral icon. Drag it
   onto another layer's property (or another property on the same layer)
   to auto-generate the correct reference code — for example, dragging
   from one layer's Position expression onto another layer's Rotation
   generates `thisComp.layer("LayerName").transform.rotation`.
2. This is the fastest way to link two properties without memorizing exact
   syntax, and it's how most real-world expressions get started even by
   experienced users.

## 3. Common built-in expressions

1. **`wiggle(freq, amp)`** — applied to Position, Rotation, or Scale, adds
   randomized jitter: `freq` is wiggles per second, `amp` is the amount of
   change. E.g. `wiggle(3, 20)` on Position gives a subtle handheld-camera
   feel.
2. **`loopOut()`** — repeats the existing keyframes on that property
   indefinitely after the last one. Common types: `loopOut("cycle")`
   (repeat identically), `loopOut("pingpong")` (repeat forward then
   backward). Useful for a looping background element without duplicating
   keyframes manually.
3. **`time`** — the current comp time in seconds; used to drive continuous
   motion, e.g. `rotation + time * 30` spins a layer 30 degrees per second
   forever without any keyframes at all.
4. **Linking Opacity to audio** — apply the **Audio Amplitude** effect
   (Effect > Audio > Audio Amplitude) to an audio layer, then pick-whip a
   Scale or Opacity property to `thisComp.layer("Audio").effect("Audio
   Amplitude")("Left Channel")` for basic audio-reactive motion.

## 4. Expression controllers

1. **Effect > Expression Controls** contains several utility effects —
   **Slider Control**, **Angle Control**, **Checkbox Control**, **Color
   Control** — that add no visible effect on their own but expose a single
   value in Effect Controls meant purely to be pick-whipped into other
   expressions.
2. This lets you build one adjustable "master control" (e.g. a Slider
   Control named `Wiggle Amount`) that several other layers' expressions
   reference, so changing one slider retunes an entire animated group at
   once instead of editing each expression by hand.

## 5. Cleaning up and troubleshooting expressions

1. A broken expression shows a warning triangle next to the property in
   the Timeline; click it to see the JavaScript error message, most
   commonly a mistyped layer/effect name (expressions are case- and
   spelling-sensitive to the exact name shown in the Timeline/Effect
   Controls).
2. To remove an expression, Alt/Option-click its stopwatch icon again
   (toggling it off), or delete the text in the expression field and click
   away.
3. Keep expressions short and named clearly — a project handed to another
   editor with unexplained pick-whipped expressions everywhere is much
   harder to hand off than one with a few clearly labeled Expression
   Controls driving things.

## Worked example: an auto-looping background element

1. In the composited title card from Module 3, add a small decorative
   shape layer meant to loop subtly behind the headline.
2. Keyframe one full rotation (0° to 360°) over 2 seconds using Easy Ease
   linear (no easing, so the loop is seamless).
3. Alt-click the Rotation stopwatch and add `loopOut("cycle")` after the
   existing keyframes so the rotation repeats indefinitely for the rest of
   the composition without needing extra keyframes.
4. Add a Slider Control named `Wiggle Amount` to the same layer, and set
   its Position expression to `wiggle(2, sliderControlValue)` (pick-whipped
   to the Slider Control's value) for an adjustable amount of drift.

## Cheat sheet — expressions

| Task | Where |
|---|---|
| Add expression to a property | Alt/Option-click its stopwatch |
| Link to another property | Drag the pick-whip spiral icon |
| Randomized jitter | `wiggle(freq, amp)` |
| Repeat existing keyframes | `loopOut("cycle")` / `loopOut("pingpong")` |
| Continuous motion without keyframes | Use `time` in the expression |
| Adjustable helper value | Effect > Expression Controls > Slider/Angle/Checkbox/Color Control |
| Remove an expression | Alt/Option-click the stopwatch again |

## Exercise

Add `loopOut("cycle")` to a rotating or moving decorative element so it
loops indefinitely from a short keyframed cycle, then add a Slider Control
pick-whipped into a `wiggle()` expression on the same or another layer so
the wiggle amount is adjustable from one place. Confirm both expressions
show no warning triangle and the loop repeats seamlessly on playback.
