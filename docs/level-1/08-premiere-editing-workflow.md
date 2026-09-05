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

## How It Actually Works

- **A Cross Dissolve needs overlapping frames because it's an alpha
  crossfade between two decoded frame buffers, not a re-cut of the edit
  points.** For every frame of the transition's duration, Premiere decodes
  the outgoing clip's frame *and* the incoming clip's frame at that same
  moment, then blends them with a linearly-changing opacity ramp (0% to
  100% incoming). Both source clips have to actually have frames available
  past the visible cut point for that math to run — that's precisely what
  the "needs trim handles" warning is reporting: there is no frame data left
  to decode beyond the hard cut, so there is nothing to blend into.
- **White balance correction is a per-channel gain calculation, not a
  filter or preset.** Clicking a spot with the WB Selector reads that
  pixel's RGB values and works out what gain multipliers would need to be
  applied to red, green, and blue to make that sample neutral gray (equal
  R=G=B); Lumetri then applies that same per-channel multiplier to every
  pixel in the frame. This is why it's sensitive to *what* you click — a
  slightly tinted "white" object gives a slightly wrong correction, since
  the whole calculation assumes the sampled point should have been neutral.
- **Loudness (LUFS) and peak level (dBFS) measure two different things,
  which is why Auto-Match and the Audio Meters can disagree.** Peak meters
  report the single loudest instantaneous sample; LUFS integrates perceived
  loudness over time using a psychoacoustic weighting curve that
  approximates how human hearing responds to different frequencies. Two
  clips can have identical peak levels but sound very differently loud if
  one has more sustained mid-frequency energy — Auto-Match is normalizing
  toward a target LUFS value, not toward a target peak, which is why
  watching only the Audio Meters' peak display doesn't fully verify what
  Auto-Match just did.
- **2-pass VBR encoding is literally two full passes over the footage.**
  Pass one analyzes the entire sequence's frame-by-frame complexity (motion,
  detail, scene changes) without writing final output; pass two then
  allocates the target bitrate non-uniformly, spending more bits on
  complex/high-motion sections and fewer on static or simple ones, guided by
  what pass one measured. 1-pass VBR estimates bit allocation as it goes,
  frame by frame, with no foreknowledge of what's coming — faster because
  it only decodes/encodes once, but less efficient at distributing a fixed
  total bitrate across a sequence with uneven complexity.
- **A platform re-compressing your upload is real transcoding, not a
  display setting.** When a delivered file doesn't match a platform's
  expected specs (resolution, frame rate, bitrate, codec profile), the
  platform's own ingest pipeline decodes your file and re-encodes it to its
  internal target — a second lossy compression pass stacked on top of
  yours. Generation loss compounds with each re-encode, which is the actual
  mechanical reason matching a platform's documented specs exactly produces
  a visibly cleaner result than uploading something "close enough."

## Exercise

Take the rough cut from Module 4's exercise (or build a new short sequence
from a few clips). Add at least one Cross Dissolve transition between two
clips. Use the Essential Sound panel's Auto-Match on any clip with
dialogue or voice. Apply a basic Lumetri Color correction (white balance +
one or two tone sliders) to one clip, then copy that correction to another
clip from the same source using Paste Attributes. Export the result at
1080p using H.264 with a 2-pass VBR bitrate around 10 Mbps.
