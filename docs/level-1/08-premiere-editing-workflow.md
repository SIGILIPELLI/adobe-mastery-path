# 08 · Premiere Editing Workflow

Module 4 got a rough cut on the timeline and out the door. This module
covers the pass that turns a rough cut into something presentable:
**transitions** between clips, **basic audio leveling**, **basic color
correction**, and choosing the right **export/render settings** for the
destination the video is actually going to (web, social, client review).

## 1. Transitions

A transition smooths the visual change from one clip to the next, instead
of a hard cut.

1. Open **Window > Effects** and search for "Cross Dissolve" in the
   **Video Transitions > Dissolve** bin.
2. Drag it directly onto the boundary between two clips on the timeline —
   it snaps into place centered on the cut point, overlapping the tail of
   the first clip with the head of the second.
3. Double-click the transition on the timeline to open its settings and
   change its **Duration** (default is usually 1 second) — shorter reads as
   snappier, longer as more deliberate/emotional.
4. **Constant Power** (the default audio crossfade, found in **Audio
   Transitions > Crossfade**) works the same way for audio clips — drag it
   onto a boundary between two audio clips to fade one out as the other
   fades in, avoiding an abrupt volume jump.
5. Use transitions sparingly — a hard cut is still the right choice most of
   the time; reach for a dissolve mainly at scene changes or time/location
   jumps where an instant cut would feel jarring.

!!! warning "Transitions need trim handles"
    A Cross Dissolve needs extra frames beyond the visible cut point on
    both clips to overlap into. If a clip has been trimmed to its exact
    absolute limit (no extra frames before/after what's showing), applying
    a transition will show a red warning triangle — trim the cut slightly
    less tightly, or shorten the transition's duration, to fix it.

## 2. Basic audio leveling

1. Select a clip on the timeline, open **Window > Essential Sound**, and
   click a category tag (e.g. **Dialogue**) — Premiere applies a relevant
   preset panel of easy sliders instead of raw effect parameters.
2. The **Loudness** section has an **Auto-Match** button that analyzes the
   clip and adjusts it toward a target loudness automatically — a fast
   first pass across multiple clips with inconsistent recording levels.
3. For manual control, each clip's audio has a horizontal **volume line**
   overlaid on its waveform in the timeline (expand the track's height with
   the track-height control at the track head to see it clearly) — drag
   the line up/down to change overall clip volume, or Option/Alt-drag to
   add a keyframe for volume that changes over time (e.g. fading music down
   under dialogue).
4. A quick sanity check before final export: open **Window > Audio Meters**
   and watch levels during playback — dialogue should generally peak
   around -12 to -6 dB, with brief peaks never slamming into 0 dB (clipping/
   distortion).

## 3. Basic color correction

1. Select a clip, open **Window > Lumetri Color**, and check **Basic
   Correction** at the top of the panel.
2. **White Balance** — use the eyedropper next to **WB Selector** and click
   something in the shot that should be neutral gray or white; Premiere
   shifts the whole clip's color temperature/tint to correct for that,
   fixing footage that looks too orange or too blue.
3. **Tone** sliders — **Exposure**, **Contrast**, **Highlights**,
   **Shadows**, **Whites**, **Blacks** — adjust brightness and contrast
   range; a light touch usually reads better than large moves on any single
   slider.
4. **Saturation** — controls overall color intensity; pull it down slightly
   if footage looks oversaturated/artificial, or push it up slightly for a
   more vivid look, but extremes get unnatural fast.
5. Once one clip looks right, right-click it and choose **Copy**, select
   other clips shot under the same lighting, right-click > **Paste
   Attributes**, and check just the Lumetri/video-effects box — this
   applies the same correction across every clip from that scene in one
   step instead of redoing sliders per clip.

## 4. Export/render settings

The right export settings depend entirely on where the video is going —
there is no single universal "best" setting.

1. **File > Export > Media** (⌘/Ctrl+M) opens the Export Settings dialog
   covered in Module 4. This time, look closely at:
   - **Format**: **H.264** for nearly everything web/social; keep the
     source's original **Frame Rate** unless you have a specific reason to
     change it (changing frame rate can introduce stutter).
   - **Resolution**: match your sequence's resolution for a general
     deliverable (e.g. 1920×1080), or use a platform's documented
     recommended size if targeting a specific one — vertical 1080×1920 for
     Stories/Reels/Shorts-style formats, for instance.
   - **Bitrate** (under the Video tab, **Bitrate Settings**): higher
     bitrate = better quality at a larger file size. **VBR, 2 pass** with a
     **Target Bitrate** around 8–12 Mbps is a reasonable default for 1080p
     web delivery; go higher (16–20+ Mbps) for detailed/high-motion footage
     or when a platform explicitly recommends it.
2. For a client-review cut, prioritize fast turnaround over squeezing file
   size — a **Match Source - High bitrate** preset with 1-pass VBR renders
   faster than a 2-pass encode, at the cost of a somewhat larger file.
3. For final delivery to a specific platform (YouTube, a client's CMS,
   etc.), check that platform's documented recommended resolution, frame
   rate, and bitrate rather than guessing — mismatched specs are a common
   cause of a platform re-compressing your export and visibly degrading it
   further.

## Cheat sheet

| Action | Where |
|---|---|
| Add a video transition | Window > Effects > Video Transitions > Dissolve |
| Add an audio crossfade | Window > Effects > Audio Transitions > Crossfade |
| Essential Sound panel | Window > Essential Sound |
| Audio Meters | Window > Audio Meters |
| Lumetri Color panel | Window > Lumetri Color |
| White balance eyedropper | Lumetri Color > Basic Correction > WB Selector |
| Copy a color correction to other clips | Right-click clip > Copy, then Paste Attributes |
| Export Media dialog | ⌘/Ctrl+M |
| Reasonable 1080p web bitrate | VBR 2-pass, 8-12 Mbps target |

## Exercise

Take the rough cut from Module 4's exercise (or build a new short sequence
from a few clips). Add at least one Cross Dissolve transition between two
clips. Use the Essential Sound panel's Auto-Match on any clip with
dialogue or voice. Apply a basic Lumetri Color correction (white balance +
one or two tone sliders) to one clip, then copy that correction to another
clip from the same source using Paste Attributes. Export the result at
1080p using H.264 with a 2-pass VBR bitrate around 10 Mbps.
