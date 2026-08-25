# 05 · Automating Workflows with Actions & Scripts

Level 2 covered Photoshop Actions and Batch for simple repetitive edits.
At production scale, automation extends further: multi-app scripting,
Lightroom's publish/export automation, and Premiere's macro-style tools —
all aimed at the same goal, doing a repeated task once correctly instead
of by hand every time.

## 1. Beyond Batch: Photoshop's Image Processor and droplets

1. **File > Scripts > Image Processor...** batch-converts a whole folder
   of images to one or more output formats/sizes in a single pass (JPEG,
   PSD, and TIFF simultaneously if needed) — faster to set up than Batch
   for a straightforward format/size conversion with no Action needed.
2. **File > Automate > Create Droplet...** packages a recorded Action into
   a standalone mini-application (an `.exe`/`.app` file) — drag any file or
   folder onto the droplet icon and Photoshop launches, applies the
   Action, and exports automatically, without opening the Photoshop UI
   manually first. Useful for handing a repetitive task to a non-Photoshop
   user (e.g. a client dragging their own photos onto a pre-built
   watermarking droplet).

## 2. Lightroom: Export Presets and Publish Services

1. Beyond a one-off **Export** dialog, save its full settings as an
   **Export Preset** (left panel of the Export dialog > **Add** button) so
   any future selection can be exported identically in one click from
   **File > Export with Preset**.
2. **Publish Services** (left panel in Library module, below Catalog) go a
   step further: connect a folder or a supported service, and photos
   marked for that Publish Service **re-export automatically** whenever
   they're modified, tracking what's already been published versus
   what's new/changed via a **Modified Photos to Republish** indicator.
3. Right-click any folder/collection > **Export...** and check the
   **Post-Processing** dropdown for "Open in Other Application" to chain a
   Lightroom export directly into another app or a custom script
   automatically after export finishes.

## 3. After Effects: render automation and expressions as automation

1. **The Render Queue** supports queuing many compositions across
   multiple output modules at once — set up several comps' renders,
   click **Render**, and let it work through all of them unattended,
   useful for overnight batch renders of many variants (e.g. per-language
   title cards).
2. **Adobe Media Encoder**'s **Watch Folder** (right-click in the Watch
   Folders panel > **Add Folder...**) automatically encodes any file
   dropped into a designated folder using a preset you assign — a simple,
   script-free way to automate a repeated encode step across a team.
3. Level 3's expression controllers (Slider/Color/Checkbox Control) are
   themselves a form of automation: one exposed control driving many
   linked properties means updating a whole animated system takes one
   edit instead of many.

## 4. Scripting with ExtendScript / UXP and the Scripts panel

1. Photoshop, Illustrator, InDesign, and After Effects all support
   scripting (legacy **ExtendScript**, JavaScript-based, still widely used;
   newer apps are migrating to **UXP** plugins) for tasks beyond what
   Actions/Batch can express — e.g. renaming layers based on a rule,
   generating many InDesign pages from a data source, or batch-exporting
   named artboards.
2. Install a script by placing the `.jsx`/`.jsxbin` file in the app's
   **Scripts** folder (**[App] > Presets > Scripts** on the install path,
   varies by OS), then it appears under **File > Scripts** (Photoshop/
   Illustrator) or **Window/File > Scripts** (After Effects, and
   Illustrator's own menu) ready to run without any coding at the point of
   use.
3. **InDesign's Data Merge** (**Window > Utilities > Data Merge**) is a
   built-in, no-scripting way to generate many personalized documents from
   a CSV/spreadsheet — e.g. 200 individually named certificates or
   business cards from one template plus a data file, via **Create Merged
   Document...** once fields are placed.

## 5. When to automate vs. when it's not worth it

1. Automate anything done **3+ times** identically, or anything handed to
   someone else to repeat without your direct guidance each time.
2. Don't over-invest in a custom script for a one-off task where a manual
   pass, or Photoshop's built-in Batch/Image Processor, would take less
   total time than writing and testing the automation.
3. Always test any automation (Action, droplet, script, Data Merge) on a
   small sample first, and check the actual output files before running it
   across a full production batch — an automated mistake repeats
   identically across every file, which is exactly why it's worth catching
   early.

## Worked example: automating campaign photo delivery

1. Build a Lightroom Export Preset for client-delivery JPEGs (sRGB, sized,
   watermark-free) and a separate preset for social-media JPEGs (smaller,
   1080px longest edge).
2. Set up a Publish Service pointed at the client's shared delivery
   folder, so re-editing any photo later and republishing keeps that
   folder current without manually re-exporting the whole set again.
3. For the print handout (Level 4 uses InDesign for this in later
   modules), set up **Data Merge** with a small CSV of names/roles to
   generate personalized name badges from one InDesign template as a
   stand-in for a real client-list mail merge.

## Cheat sheet — automation options

| Task | Where |
|---|---|
| Batch-convert format/size, no Action needed | Photoshop > File > Scripts > Image Processor... |
| Standalone drag-and-drop Action | File > Automate > Create Droplet... |
| One-click repeat export | Lightroom Export Preset |
| Auto re-export on edit | Lightroom Publish Services |
| Queue multiple unattended renders | After Effects Render Queue |
| Auto-encode on file drop | Adobe Media Encoder > Watch Folder |
| Run a custom script | File > Scripts (after installing to the app's Scripts folder) |
| Generate many personalized documents | InDesign > Window > Utilities > Data Merge |

## Exercise

Set up one automation from this module end to end: either a Lightroom
Export Preset plus a Publish Service pointed at a test folder, or an
InDesign Data Merge generating at least 5 personalized documents from a
small CSV and a template. Test it on a small sample, verify the output is
correct, then run it across a slightly larger batch and confirm every
output file matches expectations.
