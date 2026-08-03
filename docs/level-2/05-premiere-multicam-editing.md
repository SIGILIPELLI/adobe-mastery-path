# 05 · Premiere Multi-Cam Editing

Level 1 (Modules 4 & 8) cut a single stream of footage. Multi-camera work —
an interview with two angles, a live event shot on several cameras at
once — needs a way to sync those angles together and cut between them in
real time rather than manually aligning and trimming each cut by hand. This
module covers Premiere's **Multi-Camera Source Sequence** feature end to
end.

## 1. Preparing and syncing footage

1. Import every camera angle's footage (Level 1, Module 4) and organize it
   into a **bin** per setup if you're working with more than one scene.
2. Select all the clips that cover the *same* moment in time from different
   cameras (and, ideally, a separate reference audio recording if your
   cameras' built-in mics are lower quality) in the Project panel.
3. Right-click the selection and choose **Create Multi-Camera Source
   Sequence...**. In the dialog, set **Synchronization Point** to whichever
   the footage supports best:
   - **Audio** — Premiere analyzes each clip's waveform and aligns them by
     matching sound, the most reliable option if every angle recorded audio
     (even just a camera's scratch track), since it doesn't depend on
     matching timecode or a manual clap.
   - **Timecode** — aligns by embedded timecode, accurate only if every
     camera was jam-synced or genlocked before recording.
   - **Clip Markers** — aligns by a marker you've placed manually at a
     shared reference point in each clip (e.g. a clapperboard clap or a
     camera flash), useful when audio sync isn't reliable.
4. Click **OK** — Premiere creates a new nested sequence in the Project
   panel (named after the first clip, suffixed "Multi-Camera1") containing
   every angle pre-aligned in time, ready to edit as one unit.

!!! info "Keep a reference audio track if you can"
    Even a rough scratch-audio recording from a single boom mic or a phone
    placed in-frame makes Audio-based sync dramatically more reliable than
    trying to line up multiple cameras' built-in mics against each other,
    especially across a room with echo or distance-related delay.

## 2. Building and viewing a multi-cam sequence

1. Drag the multi-camera source sequence from the Project panel onto a new
   or existing timeline, exactly like a regular clip — it appears as one
   clip, nested, containing every synced angle inside it.
2. In the **Program Monitor**, enable **multi-camera view**: click the
   **Toggle Multi-Camera View** button in the monitor's button bar (if it's
   not visible, click the **+** / wrench icon at the bottom-right of the
   monitor, drag **Toggle Multi-Camera View** into the visible row, then
   click **Close**, and it stays available going forward).
3. Multi-camera view splits the Program Monitor into a grid of every synced
   angle on the left and the currently active (recorded) angle full-size on
   the right.
4. Confirm sync visually before cutting anything: scrub the playhead and
   check that action/audio lines up across every tile in the grid — fix a
   misaligned angle now by selecting it in the Camera panel and nudging it,
   rather than after cuts have already been recorded on top of it.

## 3. Cutting between angles

1. With multi-camera view active and the playhead at the sequence's start,
   press **Spacebar** to play — while it plays, click a camera tile in the
   grid (or press the matching number key, **1**-**9**) to cut to that angle
   live, the same instinct as switching a live broadcast feed. Premiere
   records each switch as an actual cut on the timeline as you go.
2. You don't have to cut live during playback — with playback paused, park
   the playhead where you want a cut and click a different camera tile to
   set that angle starting at the playhead position.
3. To change an angle you've already cut to, select that segment on the
   timeline (still shown as one multi-cam clip) and, with multi-camera view
   open, click a different tile at that point in the timeline — it swaps
   the active angle for that segment without disturbing the cuts around it.
4. Trim, ripple-delete, and add transitions on a multi-cam clip's segments
   using the exact same tools as any other clip (Level 1, Modules 4 & 8) —
   a multi-cam edit behaves like a normal sequence of cuts once angles are
   assigned, it just draws its content from multiple synced sources.

## 4. Flattening a finished multi-cam edit

1. Once the cut is locked, right-click the multi-camera clip on the
   timeline and choose **Flatten**. This converts the single nested
   multi-cam clip into a normal sequence of separate clip segments — one
   per cut, each referencing its original camera angle directly.
2. Flattening makes per-cut work easier afterward: Lumetri color correction
   (Level 1, Module 8) or audio leveling (Module 6 of this level) applied
   per segment, without reopening the nested multi-cam clip each time.
3. Keep the original un-flattened multi-camera sequence in the Project
   panel untouched as a backup — if you need to swap an angle on a cut you
   already flattened, it's easier to redo that section from the nested
   version than to hand-align raw footage again from scratch.

## Cheat sheet

| Action | Where |
|---|---|
| Create a multi-camera source sequence | Right-click selected clips > Create Multi-Camera Source Sequence |
| Sync by audio waveform | Multi-Camera dialog > Synchronization Point > Audio |
| Toggle multi-camera grid view | Program Monitor button bar (add via the + / wrench icon if missing) |
| Cut to a camera angle during playback | Click its tile, or press its number key (1-9) |
| Reassign an already-cut segment's angle | Select segment, click a different tile |
| Convert to a normal per-cut sequence | Right-click multi-cam clip > Flatten |

## Exercise

Record (or use existing) footage of the same short moment from two angles —
even two phones recording the same few seconds works for practice. Import
both, select them, and create a Multi-Camera Source Sequence using Audio
sync. Enable multi-camera view in the Program Monitor and cut between the
two angles at least three times while it plays back. Flatten the result and
apply a basic Lumetri color correction (Level 1, Module 8) to one of the
resulting segments.
