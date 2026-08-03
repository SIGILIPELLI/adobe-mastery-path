# 06 · Premiere Audio Mixing & Sound Design

Level 1 (Module 8) covered per-clip volume and the Essential Sound panel's
quick presets. This module goes further into **multi-track mixing** with
the Audio Track Mixer, **submixes and sends**, and basic **sound design** —
layering ambience/SFX and ducking music under dialogue — the pass that
makes a video sound as polished as it looks.

## 1. The Audio Track Mixer

Where the Essential Sound panel works clip-by-clip, the **Audio Track
Mixer** (**Window > Audio Track Mixer**) gives you one full channel strip
per *track*, mirroring a physical mixing console — the right tool once a
sequence has several tracks that need to be balanced against each other as
a whole.

1. Open **Window > Audio Track Mixer** — it shows one vertical strip per
   audio track in the active sequence, each with a volume **fader**, a
   **pan** knob, and **Mute (M)** / **Solo (S)** / **Record-enable (R)**
   buttons matching the equivalent controls on that track's header in the
   Timeline panel.
2. Drag a track's fader up/down during playback to adjust its overall
   level; the same fader also appears (in miniature) on the track header in
   the Timeline panel itself if the mixer isn't open.
3. Each strip's **automation mode** dropdown (top of the strip: **Off /
   Read / Latch / Touch / Write**) controls whether moving the fader during
   playback records a volume change over time as keyframes: **Write**
   records continuously while you move it, **Touch** records only while
   you're actively dragging and snaps back to the previous level once
   released, and **Read** just plays back whatever keyframes already exist
   without recording new ones.
4. Solo (**S**) individual tracks to check dialogue clarity, music, and SFX
   in isolation before judging how they sit together in the full mix.

## 2. Submixes and sends

A **submix track** groups several regular tracks so they can be adjusted,
processed, or muted together as one — for example, three separate SFX
tracks all routed to one "SFX Submix" so a single fader controls their
combined level.

1. In the Timeline panel, right-click any track header and choose **Add
   Track...**. In the dialog, set **Track Type** to **Submix** rather than
   **Standard**, and choose its channel routing (**Stereo** is typical for
   most projects).
2. On each regular track you want grouped, set its **output routing**
   (available in the Audio Track Mixer strip, near the bottom) to point to
   the new submix instead of the sequence's **Master** — audio from that
   track now passes through the submix's fader before reaching Master.
3. Adjust the submix strip's single fader in the Audio Track Mixer to raise
   or lower every routed track together, in the same proportion — useful
   for a fast "all SFX down 3dB" type change without touching several
   individual track faders one at a time.
4. A **send** (also visible per-strip in the Audio Track Mixer) forwards a
   copy of a track's signal to another track or submix at an independently
   adjustable level, without removing it from its original track — used
   less often in basic video sound design than direct output routing, but
   useful for feeding a shared reverb or effect submix from several tracks
   at once.

## 3. Sound design basics

1. Add ambience/room tone and sound effects as their own clips on dedicated
   tracks (e.g. A2 for ambience, A3 for SFX), separate from dialogue (A1) —
   keeping categories on separate tracks is what makes track-level mixing
   (Sections 1-2) and per-category adjustments practical.
2. Fade a clip in/out cleanly using the small circular **fade handles** at
   its top-left/top-right corners in the timeline (drag inward from the
   corner) rather than a hard cut, for anything ambient that shouldn't start
   or stop abruptly.
3. Open **Window > Essential Sound**, select a music clip, tag it as
   **Music**, and check **Duck Against Dialogue** — Premiere automatically
   lowers that music clip's volume wherever dialogue-tagged clips play, and
   raises it back afterward. Click **Generate Keyframes** to bake the
   ducking in as adjustable keyframes on the clip rather than a live,
   recalculated effect.
4. For deeper repair (removing background noise, hiss, or a persistent
   hum) beyond what Essential Sound's Repair section handles, right-click a
   clip and choose **Edit Clip in Adobe Audition** (if Audition is
   installed) — it opens the original audio in Audition for detailed
   restoration tools, and saving there updates the clip back in Premiere
   automatically, the same round-trip logic as a Photoshop Smart Object
   (Level 2, Module 1).
5. Check final levels with **Window > Audio Meters** (Level 1, Module 8):
   dialogue peaking around -12 to -6 dB, music sitting noticeably lower
   under dialogue (a duck of roughly -15 to -20 dB is a common starting
   point), and nothing clipping at 0 dB across the full mix.

## 4. Worked example: dialogue with music and ambience

1. Place a dialogue clip on A1, a low room-tone/ambience clip on A2 running
   underneath the whole scene, and a music bed on A3.
2. Tag the dialogue clip as **Dialogue** and the music clip as **Music** in
   Essential Sound; check **Duck Against Dialogue** on the music clip and
   click **Generate Keyframes**.
3. Fade the ambience clip in and out at the scene's edges using its corner
   fade handles so it doesn't start/stop abruptly.
4. Route A2 and A3 to a shared **Ambience/Music Submix** track, and use that
   submix's single fader in the Audio Track Mixer to balance the whole
   non-dialogue layer against the dialogue track in one move.
5. Solo A1 to confirm dialogue reads cleanly on its own, then un-solo and
   check the full mix on Audio Meters for any clipping.

## Cheat sheet

| Action | Where |
|---|---|
| Audio Track Mixer | Window > Audio Track Mixer |
| Add a submix track | Right-click track header > Add Track > Track Type: Submix |
| Route a track to a submix | Audio Track Mixer strip > output routing |
| Automation mode (record fader moves) | Track Mixer strip > mode dropdown (Read/Latch/Touch/Write) |
| Duck music under dialogue | Essential Sound > Music clip > Duck Against Dialogue |
| Bake ducking into keyframes | Essential Sound > Generate Keyframes |
| Fade a clip in/out | Drag the corner fade handles on the clip |
| Edit audio in Adobe Audition | Right-click clip > Edit Clip in Adobe Audition |
| Check final levels | Window > Audio Meters |

## Exercise

Build a short sequence with dialogue on one track, ambience on a second,
and music on a third. Tag the clips in Essential Sound, enable Duck Against
Dialogue on the music, and generate keyframes. Route the ambience and music
tracks to a shared submix and balance them against dialogue using the
submix's fader in the Audio Track Mixer. Confirm on Audio Meters that
dialogue peaks around -12 to -6 dB with no clipping anywhere in the mix.
