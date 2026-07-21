# 04 · Premiere Pro Basics

Premiere Pro is Adobe's video editor: you import footage, arrange it on a
timeline, trim it into a sequence, and export a finished file. This module
covers the workspace, importing footage, the timeline itself, basic
cuts/trims, and exporting a rough cut — the exact loop you'll repeat in
every editing session.

## 1. Workspace tour

1. Open Premiere Pro and create a new project: on the Home screen click
   **New Project**, name it, and choose a save location.
2. The default **Editing** workspace layout has four areas:
   - **Project panel** (bottom-left) — every imported file lives here as a
     clip you can drag into a sequence.
   - **Source Monitor** (top-left) — previews a clip *before* it's placed on
     the timeline, and lets you set in/out trim points on the raw clip.
   - **Program Monitor** (top-right) — previews the sequence as it will
     actually play, i.e. what's currently on the timeline.
   - **Timeline panel** (bottom) — where clips are arranged in sequence.
3. If a panel goes missing, **Window** menu lists every panel; **Window >
   Workspaces > Reset to Saved Layout** restores the default arrangement if
   things get rearranged.

## 2. Importing footage

1. **File > Import** (⌘/Ctrl+I), or double-click empty space in the Project
   panel, and select your video/audio/image files.
2. Imported files appear as clips in the Project panel — this is just a
   reference to the file on disk, not a copy, so don't move or rename
   source files after importing without relinking (**Right-click clip >
   Link Media** if a file goes missing, shown as a red offline warning).
3. Organize the Project panel with bins: **Right-click > New Bin** (or the
   folder icon at the bottom of the panel) to group clips, exactly like
   folders — useful once a project has more than a handful of files.
4. Double-click a clip in the Project panel to load it into the **Source
   Monitor** for previewing before you commit it to the timeline.

## 3. The timeline and creating a sequence

1. Drag your first clip from the Project panel directly onto empty
   timeline space — Premiere automatically creates a new **Sequence**
   matching that clip's resolution and frame rate.
2. A sequence has numbered **video tracks** (V1, V2, ...) stacked with
   higher tracks drawn on top, and **audio tracks** (A1, A2, ...) below,
   mixed together on playback.
3. Drag additional clips onto tracks to place them in time; drag a clip
   left/right along its track to reposition it. Use the **Selection tool**
   (**V**) for this — it's the default tool and the one you'll use most.
4. Zoom the timeline in/out with **=`/`-** (or the zoom slider at the
   timeline's bottom edge) to see more detail or the whole sequence at
   once.
5. Press **Spacebar** to play/pause the Program Monitor from the playhead's
   current position; drag the playhead (the blue marker at the top of the
   timeline ruler) to scrub to a specific point.

## 4. Basic cuts and trims

1. **Razor tool** (**C**) — click anywhere on a clip in the timeline to cut
   it into two separate clips at that point, which you can then
   move/delete/replace independently.
2. **Ripple Delete** — select an unwanted clip segment and press
   **Shift+Delete** (or right-click > Ripple Delete) to remove it *and*
   close the resulting gap by shifting everything after it left. A plain
   **Delete** just leaves a blank gap in its place.
3. **Trimming a clip's length** — hover over a clip's left or right edge
   with the Selection tool until the cursor shows a trim icon (a bracket),
   then drag inward/outward to shorten or lengthen that clip's in/out
   points without affecting other clips.
4. **Setting in/out points before placing a clip** — in the Source Monitor,
   press **I** at the desired start frame and **O** at the desired end
   frame; only that trimmed range is inserted when you then drag the clip
   (or press the **Insert**/**Overwrite** buttons below the monitor) onto
   the timeline.
5. **Insert vs. Overwrite** onto the timeline: **Insert** (comma key, `,`)
   pushes existing clips at the playhead position rightward to make room;
   **Overwrite** (period key, `.`) replaces whatever is already there at
   that position with the new clip.

## 5. Exporting a rough cut

1. With the sequence you want to export active (click its tab), go to
   **File > Export > Media** (⌘/Ctrl+M).
2. In the Export Settings dialog:
   - **Format**: choose **H.264** for a standard shareable MP4 — the most
     universally playable choice for a rough cut review.
   - **Preset**: **Match Source - High bitrate** keeps your sequence's
     existing resolution/frame rate, which is usually right for an internal
     review cut.
   - **Output Name**: click the blue filename link to choose where it saves
     and what it's called.
3. Click **Export** to render immediately, or **Queue** to send it to
   **Adobe Media Encoder** (a separate app for batch/background exports) if
   you want to keep editing in Premiere while it renders.
4. A progress bar appears (in Premiere or in Media Encoder); once complete,
   the exported file opens in your OS's default video player if you leave
   "Open when complete" enabled, or you can find it at the path you chose
   in step 2.

!!! info "\"Rough cut\" means good enough to review, not final"
    A rough cut is for checking pacing and story, not polish — don't worry
    yet about color correction, audio leveling, or transitions between
    clips. Those are covered in Module 8, once you're comfortable with the
    basic cut/trim/export loop from this module.

## Cheat sheet

| Tool/Action | Shortcut |
|---|---|
| New project | (Home screen) New Project |
| Import media | ⌘/Ctrl+I |
| New bin (Project panel) | Right-click > New Bin |
| Selection tool | V |
| Razor tool (cut a clip) | C |
| Ripple Delete (remove + close gap) | Shift+Delete |
| Set in point / out point (Source Monitor) | I / O |
| Insert onto timeline at playhead | , (comma) |
| Overwrite onto timeline at playhead | . (period) |
| Play/pause | Spacebar |
| Export Media dialog | ⌘/Ctrl+M |

## Exercise

Import at least two video clips (or download short stock/sample clips if
you don't have any on hand). Build a sequence that cuts between them at
least twice, using the Razor tool to trim unwanted footage and Ripple
Delete to close the resulting gaps. Set in/out points on a third clip in
the Source Monitor before inserting just that trimmed range onto the
timeline. Export the result as an H.264 MP4 rough cut using **File >
Export > Media**.
