# 09 · After Effects Motion Tracking Basics

Back in After Effects, this module covers **tracking** — locking a layer
(a graphic, text, or blur) onto motion that already exists in footage, such
as a screen insert that needs to stick to a moving phone, or a logo that
should ride along a moving object. This covers the **Tracker** panel's 2D
point tracking and the simpler **Track Camera** for 3D scenes.

## 1. The Tracker panel and 2D Point Tracking

1. Select the footage layer with the motion to track, then open
   **Window > Tracker**. Click **Track Motion** to enter tracking mode —
   the layer opens in its own Layer panel with a **track point** overlay.
2. A track point has two boxes: the inner **feature region** (the exact
   visual pattern to follow — pick a high-contrast, distinct area like a
   corner or sticker) and the outer **search region** (how far AE looks
   for that pattern in the next frame — wider for fast/erratic motion).
3. Choose a **Track Type** in the Tracker panel: **Transform** (Position
   and/or Rotation/Scale from one point, or two points for Rotation/Scale),
   **Perspective corner pin** (four points, for a screen/sign insert that
   needs to follow a surface's perspective), or **Raw** (data only, for
   custom expression use).
4. Position the track point over the chosen feature at the layer's first
   frame, then click the **Analyze forward** button (the right-pointing
   play icon in the Tracker panel) to track frame-by-frame automatically.
5. Watch playback as it analyzes — if the track point visibly drifts off
   the intended feature partway through, stop, manually correct the point
   at that frame, and re-analyze forward from there rather than letting a
   bad track continue.

## 2. Applying the track

1. Once analysis finishes and looks clean scrubbing through, select the
   layer that should follow the track (e.g. a logo or text layer) and
   click **Edit Target...** in the Tracker panel to confirm it, then click
   **Apply**.
2. For a Transform track, AE writes Position (and Rotation/Scale, if
   tracked) keyframes directly onto the target layer, matching the tracked
   motion frame-for-frame.
3. For a Corner Pin track, AE applies the **Corner Pin** effect to the
   target layer with its four corners keyframed to the four tracked
   points — used for a screen replacement (e.g. compositing a new UI onto
   a phone/monitor visible in the shot).

## 3. Track Camera (3D scenes)

1. **Track Camera** (also in the Tracker panel, or **Animation > Track
   Camera in Composition**) analyzes an entire shot for camera movement
   and scene depth, generating a cloud of 3D **track points** across the
   footage rather than a single 2D point.
2. Once analysis completes, click on a well-tracked point in the scene
   (ideally one on a flat, stable surface) and choose **Create Null and
   Camera** (or **Create Text/Solid**) from the right-click menu on a
   selected track point — this creates a 3D-tracked null/camera that any
   new layer can be parented to for it to sit convincingly in the 3D scene,
   respecting perspective as the camera moves.
3. Track Camera works best on footage with plenty of fixed, high-contrast
   detail throughout the frame and a camera that moves with some
   parallax (not a purely static locked-off shot, which gives it no depth
   information to solve).

## 4. Stabilizing footage (the inverse use of tracking)

1. **Warp Stabilizer VFX** (Effect > Distort > Warp Stabilizer VFX, or
   drag from Effects & Presets) analyzes shaky handheld footage and
   smooths it automatically — no manual track point placement needed.
2. Key settings in Effect Controls: **Result** (Smooth Motion keeps some
   original camera move; No Motion locks it fully static),
   **Smoothness** (percentage of shake removed), and **Method**
   (Position, Position/Scale/Rotation, Perspective, or Subspace Warp for
   the most aggressive correction).
3. Warp Stabilizer needs to fully analyze the clip (shown as "Analyzing"
   then "Stabilizing" in the Effect Controls and directly on the layer)
   before playback reflects the final result — this can take real time on
   longer clips.

## Worked example: a phone screen insert

1. Import a clip of a hand holding a phone that moves/tilts during the
   shot, with the phone's screen visible.
2. Apply a **Perspective corner pin** track: place the four track points
   at the phone screen's four corners on frame 1, and Analyze forward.
3. Import the new screen graphic as a solid/still, Edit Target it to the
   phone footage's track, and Apply — the Corner Pin effect keyframes now
   follow the phone's screen perspective throughout the shot.
4. If the source footage itself is a little shaky, apply Warp Stabilizer
   VFX to the phone footage *first*, before tracking, so the track has less
   erratic motion to follow.

## Cheat sheet — motion tracking

| Task | Where |
|---|---|
| Open Tracker panel | Window > Tracker |
| Start a 2D point track | Track Motion button |
| Choose Transform / Corner Pin / Raw | Track Type dropdown in Tracker panel |
| Run automatic tracking | Analyze forward/backward buttons |
| Apply tracked motion to another layer | Edit Target... then Apply |
| 3D camera + scene solve | Track Camera |
| Attach a new layer to the 3D solve | Right-click a track point > Create Null and Camera |
| Smooth shaky footage | Effect > Distort > Warp Stabilizer VFX |

## Exercise

Track a moving element in a handheld or phone-screen clip using a
Transform or Corner Pin track, apply it to a new graphic/text layer, and
confirm the graphic sticks to the tracked feature throughout playback with
no visible drift. If the source footage is shaky, apply Warp Stabilizer
VFX before tracking and compare tracking accuracy with and without it.
