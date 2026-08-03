# 07 · Photoshop Automation (Actions & Batch Processing)

Repeating the same sequence of edits across dozens or hundreds of photos by
hand is slow and error-prone. This module covers recording an **Action** —
a saved, replayable sequence of Photoshop steps — and running it
unattended across a whole folder with **Batch** or the **Image Processor**.

## 1. Recording an Action

1. Open **Window > Actions** (**Option/Alt+F9**). Click the **Create New
   Action** icon at the bottom of the panel, name it something descriptive
   (e.g. `Web Export — Resize + Watermark`), and click **Record** — the
   panel's record button (a red circle) turns solid red, meaning every
   subsequent step is now being captured.
2. With a sample file already open, perform the edits you want repeated —
   for example: **Image > Image Size** to resize, **File > Place Embedded**
   to drop in a logo watermark at a consistent position, then **File >
   Export > Export As** to save the result. Each step appears as its own
   line in the Actions panel as you go.
3. Click the **Stop Playing/Recording** icon (a square) when finished. The
   Action now appears fully expanded in the panel, listing every recorded
   step in order.
4. To insert a manual pause — useful for a step that needs different input
   per file, like repositioning a crop — select a step, open the panel
   menu (top-right ≡), and choose **Insert Stop...**; add a short message
   describing what to do, and check **Allow Continue** so playback can
   resume after the pause instead of halting the batch entirely.
5. Double-click any recorded step's name to reopen its exact settings and
   edit them without re-recording from scratch; drag a step up/down in the
   list to reorder it, or drag it to the trash icon to delete just that
   step.

!!! warning "Don't record File > Open inside an action meant for Batch"
    If you plan to run the action via **Batch** (Section 2), avoid
    recording your *own* **File > Open** step at the start — Batch opens
    each source file automatically and feeds it through the action. An
    extra Open step recorded into the action itself is redundant and can
    open the wrong file when the action runs unattended. A **File > Place
    Embedded** step for a fixed asset (like a watermark logo) is unrelated
    to this and is fine to include.

## 2. Playing back an Action

1. Select the Action (or a specific step within it, to start partway
   through) in the Actions panel and click the **Play** icon (a right-
   pointing triangle) at the bottom of the panel to run it once on the
   currently open file.
2. Group related actions into an **Action Set** (the folder-style **Create
   New Set** icon) to keep the panel organized once you have several — one
   set for web export variants, another for print prep, for example.
3. Actions can be saved to disk (panel menu > **Save Actions...**) as a
   portable `.atn` file and loaded on another machine (panel menu > **Load
   Actions...**) — useful for sharing a studio's standard export action
   with a collaborator.

## 3. Batch processing

**File > Automate > Batch** runs one Action across every file in a folder
automatically, without opening and closing each one by hand.

1. Choose **File > Automate > Batch...**. Under **Play**, pick the **Set**
   and **Action** to run.
2. Under **Source**, choose **Folder** and click **Choose...** to point at
   the folder of files to process. Check **Override Action "Open"
   Commands** only if your action does contain its own Open step you want
   Batch to ignore in favor of opening each source file directly.
3. Under **Destination**, choose **Folder** and pick where processed files
   should save, rather than **None** (which just leaves files open,
   unsaved) or **Save and Close** (which overwrites the originals in
   place — a safer choice than overwriting your only copies of the source
   files is almost always a separate destination folder).
4. Check **Override Action "Save As" Commands** so each file saves into
   *this* destination folder rather than wherever the recorded action's
   Save/Export step originally pointed.
5. Under **File Naming**, optionally set a naming pattern (e.g. appending
   `-web` before the extension) if you want processed files distinguishable
   from originals at a glance.
6. Click **OK** — Photoshop opens, processes, and saves each file in the
   source folder in turn, with no further input needed unless the action
   contains an **Insert Stop** (Section 1).

## 4. Image Processor

For simpler jobs — just resizing and/or converting file format across a
folder, without a custom sequence of edits — **File > Scripts > Image
Processor** is faster to set up than recording an Action first.

1. Choose **File > Scripts > Image Processor...**. Pick the source folder
   (or use currently open files) and a destination folder for the output.
2. Check one or more file types to save as (**JPEG**, **PSD**, **TIFF**),
   each with its own **Resize to Fit** width/height and quality/compression
   settings.
3. Optionally check **Run Action** and pick a saved Action to apply to
   every file in addition to the resize/format conversion — combining a
   custom Action with the Image Processor's batch resize/export step in one
   pass.
4. Click **Run** — progress displays in a small status window, and the
   dialog reports how many files completed when finished.

## 5. Worked example: batch resize, watermark, and export

1. Open one sample photo. Record a new Action: **Image > Image Size** to a
   target width (e.g. 2000px, with **Resample** on), **File > Place
   Embedded** to add a logo watermark positioned in a corner, **Layer >
   Flatten Image**, then **File > Export > Export As** as a JPEG. Stop
   recording.
2. Run **File > Automate > Batch**, selecting this Action, with **Source:
   Folder** pointed at a folder of raw photos and **Destination: Folder**
   pointed at a new, empty output folder, with **Override "Save As"
   Commands** checked.
3. Confirm every file in the output folder is resized, watermarked
   identically, and named as expected.

## Cheat sheet

| Action | Where |
|---|---|
| Actions panel | Window > Actions (Option/Alt+F9) |
| New Action / Record / Stop | Actions panel icons (folder+ / red circle / square) |
| Insert a manual pause in an action | Panel menu > Insert Stop... |
| Save/Load actions as a file | Panel menu > Save Actions... / Load Actions... |
| Run an action across a folder | File > Automate > Batch |
| Quick resize + format conversion across a folder | File > Scripts > Image Processor |
| Make a droplet (drag-and-drop mini app for one action) | File > Automate > Create Droplet |

## Exercise

Record an Action that resizes a photo to a fixed width, places a watermark
logo in a corner, flattens, and exports as a JPEG. Run it across a folder of
at least three sample photos using File > Automate > Batch, saving results
to a separate destination folder with a distinguishing filename suffix.
Confirm all output files are resized and watermarked consistently.
