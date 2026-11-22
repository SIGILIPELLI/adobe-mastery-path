---
title: "Final Quiz"
description: "Test what you have learned across all four levels of Adobe Creative Cloud Mastery Path with a 20-question final quiz."
---

# Final Quiz

20 questions drawn from all four levels of this course. You need **70% (14 out of 20)** to pass —
you can retake it as many times as you like. Your best result is saved in this browser.

<div id="mp-quiz-root"></div>

<script type="application/json" id="mp-quiz-data">
[
  {
    "question": "What timecode is frame 2,160 at 24 fps?\n```python\nf=2160;fps=24\ns=f//fps\nprint(f'{s//3600:02d}:{s//60%60:02d}:{s%60:02d}:{f%fps:02d}')\n```\n",
    "options": [
      "01:30:00:00",
      "00:02:00:00",
      "00:00:90:00",
      "00:01:30:00"
    ],
    "correctIndex": 3,
    "explanation": "Divide frames by the frame rate to get seconds. (A Python check of the arithmetic behind the technique; the Adobe applications themselves were not run.) Verified by running it."
  },
  {
    "question": "How much does +6 dB change amplitude, and how many dB is a halving of amplitude?\n```python\nimport math\nprint(round(10**(6/20),2), round(20*math.log10(0.5),2))\n```\n",
    "options": [
      "2.0 -6.02",
      "1.5 -6.02",
      "6.0 -3.0",
      "2.0 -3.01"
    ],
    "correctIndex": 0,
    "explanation": "Amplitude ratio = 10^(dB/20); halving is about -6 dB. (A Python check of the arithmetic behind the technique; the Adobe applications themselves were not run.) Verified by running it."
  },
  {
    "question": "What is the effective resolution of a 2,400 px wide photo placed 100 mm wide, and at 150% scale?\n```python\nprint(round(2400/(100/25.4)), round(2400/(150/25.4)))\n```\n",
    "options": [
      "240 160",
      "254 254",
      "610 406",
      "61 41"
    ],
    "correctIndex": 2,
    "explanation": "Enlarging an image lowers its effective ppi. (A Python check of the arithmetic behind the technique; the Adobe applications themselves were not run.) Verified by running it."
  },
  {
    "question": "A 210x297 mm page with 3 mm bleed needs what document size, and an 8 Mbps video lasting 60 s is roughly how large (MB)?\n```python\nprint((210+6,297+6), 8*60/8)\n```\n",
    "options": [
      "(216, 303) 480.0",
      "(213, 300) 60.0",
      "(216, 303) 60.0",
      "(210, 297) 7.5"
    ],
    "correctIndex": 2,
    "explanation": "Add bleed on both sides; size = bitrate x time / 8. (A Python check of the arithmetic behind the technique; the Adobe applications themselves were not run.) Verified by running it."
  },
  {
    "question": "What is the contrast ratio of mid grey (119) on white, and does it reach the WCAG AA threshold of 4.5?\n```python\ndef lin(c):\n    c/=255\n    return c/12.92 if c<=0.04045 else ((c+0.055)/1.055)**2.4\nL=lambda v: lin(v)\nr=(1+0.05)/(L(119)+0.05)\nprint(round(r,2), r>=4.5)\n```\n",
    "options": [
      "2.0 False",
      "4.48 False",
      "4.48 True",
      "7.0 True"
    ],
    "correctIndex": 1,
    "explanation": "Mid grey #777 is a famous near-miss for AA on white. (A Python check of the arithmetic behind the technique; the Adobe applications themselves were not run.) Verified by running it."
  },
  {
    "question": "Which setting extends artwork beyond the trim edge so no white slivers show after cutting?",
    "options": [
      "Slug",
      "Margin",
      "Gutter",
      "Bleed (typically 3 mm or 0.125 in)"
    ],
    "correctIndex": 3,
    "explanation": "Set it in the document setup."
  },
  {
    "question": "What is the difference between Assign Profile and Convert to Profile?",
    "options": [
      "Assign reinterprets numbers without changing them; Convert changes the numbers to preserve appearance in a new space",
      "Convert only labels",
      "Assign converts",
      "Same"
    ],
    "correctIndex": 0,
    "explanation": "Choose deliberately."
  },
  {
    "question": "What do parent (master) pages do in InDesign?",
    "options": [
      "Export",
      "Print",
      "Colour",
      "Hold repeating elements such as grids, margins and page numbers for many pages"
    ],
    "correctIndex": 3,
    "explanation": "Edit once, update everywhere."
  },
  {
    "question": "Why use paragraph styles with 'Based On' relationships?",
    "options": [
      "Speed",
      "Colour",
      "Changes cascade through a hierarchy so documents stay consistent",
      "Law"
    ],
    "correctIndex": 2,
    "explanation": "Never format by hand."
  },
  {
    "question": "What does Easy Ease do to a keyframe?",
    "options": [
      "Locks it",
      "Smooths acceleration and deceleration instead of constant speed",
      "Deletes it",
      "Colours it"
    ],
    "correctIndex": 1,
    "explanation": "Edit in the Graph Editor."
  },
  {
    "question": "What does the speed graph show compared with the value graph in After Effects?",
    "options": [
      "Time",
      "How quickly the value changes, whereas the value graph shows the value itself",
      "Colours",
      "Audio"
    ],
    "correctIndex": 1,
    "explanation": "Steep speed means fast change."
  },
  {
    "question": "What is an After Effects expression?",
    "options": [
      "A JavaScript snippet on a property that computes its value, for example wiggle() or loopOut()",
      "A plug-in",
      "A mask",
      "A preset"
    ],
    "correctIndex": 0,
    "explanation": "Pick-whip links properties."
  },
  {
    "question": "What is the right way to attach a graphic to a moving subject?",
    "options": [
      "Precompose",
      "Track the motion and apply the data to a null or the layer's position, rotation or scale (or a corner pin)",
      "Keyframe by eye",
      "Blend"
    ],
    "correctIndex": 1,
    "explanation": "Tracking automates the matching."
  },
  {
    "question": "What does Dynamic Link let you do?",
    "options": [
      "Sync audio",
      "Import fonts",
      "Update Premiere and After Effects compositions without intermediate renders",
      "Export"
    ],
    "correctIndex": 2,
    "explanation": "Replace With After Effects Composition."
  },
  {
    "question": "What is a Motion Graphics Template for?",
    "options": [
      "Editable animated titles that editors adjust in Premiere's Essential Graphics panel without opening After Effects",
      "A video",
      "A LUT",
      "A preset"
    ],
    "correctIndex": 0,
    "explanation": "Master Properties control what is editable."
  },
  {
    "question": "What does the vectorscope help you judge?",
    "options": [
      "Timecode",
      "Brightness",
      "Hue and saturation, including whether skin tones sit near the skin-tone line",
      "Audio"
    ],
    "correctIndex": 2,
    "explanation": "The waveform judges luma."
  },
  {
    "question": "Why use Creative Cloud Libraries in a team?",
    "options": [
      "Shared brand colours, styles and assets stay current across apps and people",
      "Colour",
      "Law",
      "Speed"
    ],
    "correctIndex": 0,
    "explanation": "One source of truth."
  },
  {
    "question": "When should you script rather than record an action?",
    "options": [
      "When you need loops, conditions or logic that a recorded action cannot express",
      "Always",
      "Never",
      "Simple tasks"
    ],
    "correctIndex": 0,
    "explanation": "Test on copies first."
  },
  {
    "question": "What should a client delivery package contain?",
    "options": [
      "Nothing",
      "Final files in the agreed formats, specifications and, if contracted, organised source files",
      "Only source",
      "Only a screenshot"
    ],
    "correctIndex": 1,
    "explanation": "Agree deliverables upfront."
  },
  {
    "question": "What makes a pipeline robust across apps?",
    "options": [
      "Fancy plug-ins",
      "Agreed colour spaces, formats, naming and hand-offs documented before production starts",
      "Luck",
      "Speed"
    ],
    "correctIndex": 1,
    "explanation": "A pipeline is agreements as much as software."
  }
]
</script>

## Coding challenges

Try these on your own computer, then compare your output. Nothing you write is sent anywhere.

### Timecode, easing curves and expression-style motion

Model the maths behind keyframed motion in plain Python: frame-to-timecode (including 29.97 drop-frame), linear / ease-in-out / ease-out / cubic-bezier easing between keyframes, a loopOut('cycle') style repeat and a seeded, bounded wiggle. This reproduces the arithmetic After Effects performs; it does not run After Effects or Premiere.

**Starter code**

```python
import math, random

# TODO: to_timecode(frames, fps=24) -> "HH:MM:SS:FF"
# TODO: to_dropframe(frames) -> NTSC 29.97 drop-frame "HH:MM:SS;FF" (skip frame numbers 00 and 01 each minute except every 10th minute)
# TODO: easing functions linear, ease_in_out (3t^2 - 2t^3), ease_out (1 - (1-t)^3), and bezier(x1,y1,x2,y2) solved by bisection on x
# TODO: animate(keys, t, ease) interpolating between (time, value) keyframes, clamped outside the range
# TODO: loop_cycle(keys, t) - like loopOut("cycle"); wiggle(freq, amp, t, seed) - smooth, seeded, bounded by amp
# Print, in order: timecodes, the four easing rows at t = 0.25, 0.5, 1.0, 1.5 for keys [(0,0),(1,100),(2,40)], the loop cycle values,
# the wiggle samples and two checks (bounded by amp, repeatable with the same seed)
keys = [(0, 0), (1, 100), (2, 40)]
```

**Expected output**

```text
00:01:30:00 01:00:05:07 00:01:00;02 00:10:00;00
linear               [25.0, 50.0, 100.0, 70.0]
ease in/out          [15.6, 50.0, 100.0, 70.0]
ease out             [57.8, 87.5, 100.0, 47.5]
bezier(.42,0,.58,1)  [12.9, 50.0, 100.0, 70.0]
loopOut cycle: [50.0, 50.0, 50.0, 100.0]
wiggle(2,30): [-10.7, -14.9, -21.8, -20.4, -5.6, 3.6, 5.6, 9.0, 6.6, -10.4, -21.0] | stays within amp: True
same seed repeats: True
```

<details><summary>Show solution and explanation</summary>

<pre><code>import math, random

# --- timecode -------------------------------------------------------------
def to_timecode(frames, fps=24):
    f = frames % fps
    s = frames // fps
    return f&quot;{s // 3600:02d}:{s // 60 % 60:02d}:{s % 60:02d}:{f:02d}&quot;

def to_dropframe(frames):
    &quot;&quot;&quot;29.97 fps drop-frame: skip frame numbers 00 and 01 at the start of every minute except every tenth minute.&quot;&quot;&quot;
    d, m = divmod(frames, 17982)              # frames per 10 minutes
    frames += 18 * d + (2 * ((m - 2) // 1798) if m &gt; 2 else 0)
    f = frames % 30
    s = frames // 30
    return f&quot;{s // 3600:02d}:{s // 60 % 60:02d}:{s % 60:02d};{f:02d}&quot;

print(to_timecode(90 * 24), to_timecode(24 * 3600 + 5 * 24 + 7), to_dropframe(1800), to_dropframe(17982))

# --- keyframe interpolation and easing ------------------------------------
def linear(t): return t
def ease_in_out(t): return 3 * t ** 2 - 2 * t ** 3            # smoothstep, like Easy Ease
def ease_out(t): return 1 - (1 - t) ** 3

def bezier(x1, y1, x2, y2):
    &quot;&quot;&quot;CSS-style cubic-bezier easing solved with bisection on x.&quot;&quot;&quot;
    def curve(a, b, t): return 3 * a * (1 - t) ** 2 * t + 3 * b * (1 - t) * t ** 2 + t ** 3
    def ease(x):
        lo, hi = 0.0, 1.0
        for _ in range(40):
            mid = (lo + hi) / 2
            if curve(x1, x2, mid) &lt; x: lo = mid
            else: hi = mid
        return curve(y1, y2, (lo + hi) / 2)
    return ease

def animate(keys, t, ease=linear):
    &quot;&quot;&quot;keys: [(time, value), ...] sorted by time; ease applies between keys.&quot;&quot;&quot;
    if t &lt;= keys[0][0]: return keys[0][1]
    if t &gt;= keys[-1][0]: return keys[-1][1]
    for (t0, v0), (t1, v1) in zip(keys, keys[1:]):
        if t0 &lt;= t &lt;= t1:
            return v0 + (v1 - v0) * ease((t - t0) / (t1 - t0))

keys = [(0, 0), (1, 100), (2, 40)]
for name, e in [(&quot;linear&quot;, linear), (&quot;ease in/out&quot;, ease_in_out), (&quot;ease out&quot;, ease_out), (&quot;bezier(.42,0,.58,1)&quot;, bezier(.42, 0, .58, 1))]:
    print(f&quot;{name:20}&quot;, [round(animate(keys, t, e), 1) for t in (0.25, 0.5, 1.0, 1.5)])

# --- expressions: loopOut(&quot;cycle&quot;) and a seeded wiggle ----------------------
def loop_cycle(keys, t, ease=ease_in_out):
    start, end = keys[0][0], keys[-1][0]
    return animate(keys, start + (t - start) % (end - start), ease)

print(&quot;loopOut cycle:&quot;, [round(loop_cycle(keys, t), 1) for t in (0.5, 2.5, 4.5, 5.0)])

def wiggle(freq, amp, t, seed=7):
    &quot;&quot;&quot;smooth value noise: random values at 1/freq intervals, cosine-interpolated&quot;&quot;&quot;
    def at(i):
        return random.Random(seed * 1000 + i).uniform(-1, 1)
    x = t * freq
    i = math.floor(x); f = x - i
    f = (1 - math.cos(f * math.pi)) / 2
    return amp * (at(i) * (1 - f) + at(i + 1) * f)

vals = [round(wiggle(2, 30, t / 10), 1) for t in range(0, 21, 2)]
print(&quot;wiggle(2,30):&quot;, vals, &quot;| stays within amp:&quot;, all(abs(v) &lt;= 30 for v in vals))
print(&quot;same seed repeats:&quot;, wiggle(2, 30, 0.37) == wiggle(2, 30, 0.37))
</code></pre>

<p>Easing remaps normalised time before interpolation, so the same keyframes give different in-between values. Drop-frame timecode skips frame numbers (not real frames) to stay in step with 29.97 fps video. The wiggle uses seeded noise so it repeats, which is why After Effects&#x27; wiggle is deterministic per property. Verified by running the Python solution.</p>
</details>

### Print, colour and delivery calculators

Write the calculators a designer or editor keeps reaching for: bleed sizes, effective resolution of placed images, total ink coverage against a 300% limit, a naive RGB-to-CMYK conversion, WCAG contrast, loudness gain and delivery file sizes. The naive CMYK conversion ignores ICC profiles, which real prepress uses; this models the arithmetic only, not InDesign, Photoshop or Premiere.

**Starter code**

```python
import math

# TODO: with_bleed(w, h, bleed=3); effective_ppi(pixels_w, placed_mm_w, scale_percent=100); tac(c, m, y, k); naive_cmyk(r, g, b)
# TODO: lin(c), lum(rgb), contrast(a, b) (WCAG relative luminance); gain_to_target(measured_lufs, target_lufs) -> (dB, amplitude ratio);
#       file_size_mb(video_mbps, audio_kbps, seconds)
# Print: bleed sizes for A5 (148x210) and A4, effective ppi verdicts (>= 250 print, >= 150 soft, else screen) for three placements,
#        TAC verdicts against a 300% limit for rich black (60,40,40,100), a heavy mix (80,70,60,90) and plain K,
#        a naive CMYK for orange/black/grey, two contrast ratios, the loudness gain and two delivery file sizes
```

**Expected output**

```text
A5 trim with bleed: (154, 216) | A4: (216, 303)
hero 3000px on 210mm: 363 ppi -> ok for print
logo 600px on 60mm: 254 ppi -> ok for print
photo enlarged 150%: 406 ppi -> ok for print
rich black TAC 240% within 300% limit
heavy mix  TAC 300% within 300% limit
plain K    TAC 100% within 300% limit
orange RGB(255,128,0) -> CMYK (0, 50, 100, 0) | black (0, 0, 0, 100) | mid grey (0, 0, 0, 50)
contrast white/#1a1a2e: 17.1 | yellow on white: 1.35
gain to reach -14 LUFS from -20.5: +6.5 dB (x2.11 amplitude)
90 s social cut at 8 Mbps + 192 kbps audio: 92.2 MB
4 min master at 50 Mbps + 320 kbps audio: 1510 MB
```

<details><summary>Show solution and explanation</summary>

<pre><code>import math

# --- print production ------------------------------------------------------
def with_bleed(w, h, bleed=3):
    return (w + 2 * bleed, h + 2 * bleed)

def effective_ppi(pixels_w, placed_mm_w, scale_percent=100):
    return pixels_w / (placed_mm_w * scale_percent / 100 / 25.4)

def tac(c, m, y, k):
    return c + m + y + k

def naive_cmyk(r, g, b):
    &quot;&quot;&quot;textbook RGB -&gt; CMYK (no ICC profile); real conversions use profiles and rendering intents&quot;&quot;&quot;
    r, g, b = r / 255, g / 255, b / 255
    k = 1 - max(r, g, b)
    if k == 1: return (0, 0, 0, 100)
    return tuple(round(100 * v) for v in ((1 - r - k) / (1 - k), (1 - g - k) / (1 - k), (1 - b - k) / (1 - k), k))

print(&quot;A5 trim with bleed:&quot;, with_bleed(148, 210), &quot;| A4:&quot;, with_bleed(210, 297))
for label, px, mm, sc in [(&quot;hero 3000px on 210mm&quot;, 3000, 210, 100), (&quot;logo 600px on 60mm&quot;, 600, 60, 100), (&quot;photo enlarged 150%&quot;, 2400, 100, 150)]:
    ppi = effective_ppi(px, mm, sc)
    print(f&quot;{label}: {ppi:.0f} ppi -&gt; {&#x27;ok for print&#x27; if ppi &gt;= 250 else &#x27;too soft for print&#x27; if ppi &gt;= 150 else &#x27;screen only&#x27;}&quot;)
for name, ink in [(&quot;rich black&quot;, (60, 40, 40, 100)), (&quot;heavy mix&quot;, (80, 70, 60, 90)), (&quot;plain K&quot;, (0, 0, 0, 100))]:
    t = tac(*ink)
    print(f&quot;{name:10} TAC {t}% {&#x27;over 300% limit&#x27; if t &gt; 300 else &#x27;within 300% limit&#x27;}&quot;)
print(&quot;orange RGB(255,128,0) -&gt; CMYK&quot;, naive_cmyk(255, 128, 0), &quot;| black&quot;, naive_cmyk(0, 0, 0), &quot;| mid grey&quot;, naive_cmyk(128, 128, 128))

# --- colour contrast, audio gain and delivery size --------------------------
def lin(c):
    c /= 255
    return c / 12.92 if c &lt;= 0.04045 else ((c + 0.055) / 1.055) ** 2.4

def lum(rgb):
    r, g, b = map(lin, rgb)
    return 0.2126 * r + 0.7152 * g + 0.0722 * b

def contrast(a, b):
    la, lb = sorted((lum(a), lum(b)), reverse=True)
    return (la + 0.05) / (lb + 0.05)

print(&quot;contrast white/#1a1a2e:&quot;, round(contrast((255, 255, 255), (0x1a, 0x1a, 0x2e)), 1), &quot;| yellow on white:&quot;, round(contrast((255, 221, 0), (255, 255, 255)), 2))

def gain_to_target(measured_lufs, target_lufs):
    db = target_lufs - measured_lufs
    return db, 10 ** (db / 20)

db, ratio = gain_to_target(-20.5, -14)
print(f&quot;gain to reach -14 LUFS from -20.5: +{db:.1f} dB (x{ratio:.2f} amplitude)&quot;)

def file_size_mb(video_mbps, audio_kbps, seconds):
    return (video_mbps * 1000 + audio_kbps) * seconds / 8 / 1000

print(&quot;90 s social cut at 8 Mbps + 192 kbps audio:&quot;, round(file_size_mb(8, 192, 90), 1), &quot;MB&quot;)
print(&quot;4 min master at 50 Mbps + 320 kbps audio:&quot;, round(file_size_mb(50, 320, 240)), &quot;MB&quot;)
</code></pre>

<p>Effective ppi falls as an image is enlarged; TAC adds the four ink percentages; contrast uses relative luminance from linearised sRGB; a gain of +6.5 dB is an amplitude factor of about 2.1. File size is bitrate times duration divided by eight. Verified by running the Python solution.</p>
</details>
