# 01 · Creative Cloud Setup, Libraries & Sync

Every lesson in this track assumes the same starting point: the **Creative
Cloud desktop app** installed and signed in, the apps you need downloaded,
and at least one **Creative Cloud Library** set up so assets can travel
between Photoshop, Illustrator, and Premiere Pro without you re-exporting
files by hand. This module gets that foundation in place once, so every
later lesson can focus purely on the app in question.

## 1. Install the Creative Cloud desktop app

1. Go to [creativecloud.adobe.com](https://creativecloud.adobe.com/) and sign
   in with your Adobe ID (or create one — no credit card needed for a trial).
2. Download the **Creative Cloud desktop app** installer for your OS and run
   it. This app is the hub for everything else: it is not a design tool
   itself, it's the launcher, updater, and sync client for all your Adobe
   apps and assets.
3. Once installed, open it — you'll land on the **Apps** tab, showing every
   app in your plan (Photoshop, Illustrator, Premiere Pro, After Effects,
   Lightroom, InDesign, etc.) with an **Install** button next to each.

!!! info "You do not need every app installed to start"
    Install Photoshop, Illustrator, and Premiere Pro now — you'll need those
    three for Modules 2-4. After Effects is used starting in Module 5;
    Lightroom and InDesign aren't needed until Level 3.

## 2. Install and update your apps

1. In the Creative Cloud desktop app, click **Install** next to Photoshop.
   Repeat for Illustrator and Premiere Pro. Installs run in the background —
   you can queue several at once.
2. Once installed, the button changes to **Open**. Apps also show an
   **Update available** badge when a new version ships; click it to update,
   or open **Creative Cloud desktop app menu (⋯ top-right) > Preferences >
   Apps** and toggle **Auto-update** so this happens automatically.
3. To remove an old version after updating (Adobe sometimes keeps the
   previous major version installed side-by-side), open the app's **⋯** menu
   in the Apps list and choose **Manage** to see and uninstall older
   versions.

!!! warning "Match your tutorial to your version, not the other way around"
    Menu names in this track are current as of recent Creative Cloud
    releases and are stable release-to-release, but panel positions can
    shift slightly between versions. If a menu item in a later lesson isn't
    where described, check **Help > About [App Name]** for your version and
    search the in-app **Help** search bar (top of most panels) for the exact
    command name — it hasn't been removed, just possibly relocated.

## 3. Creative Cloud Libraries — the basics

A **Library** is a container of reusable assets — colors, character (text)
styles, graphics, and images — that syncs to Adobe's servers and is
available inside every Creative Cloud app you sign into, on any machine.
This is the mechanism Module 9 and the Module 10 capstone rely on to move a
logo or a color palette between Photoshop, Illustrator, and Premiere Pro
without manual exporting.

1. Open Photoshop (or Illustrator — the Libraries panel is identical in
   both). Go to **Window > Libraries**.
2. At the top of the panel, click the Library name dropdown and choose
   **Create new library**. Name it something you'll reuse across this whole
   course, e.g. `Mastery Path Brand Kit`.
3. With a layer or selection active, you can now add assets directly:
   - Select a **Color Swatch** or use the eyedropper in the Libraries panel
     to pull a color from your canvas — it's saved to the Library as a
     reusable swatch.
   - Select text with the Type tool active, then click the **+ (Text
     Style)** button in the Libraries panel to save a **Character Style**
     (font, size, color, tracking) as one reusable asset.
   - Drag a layer, shape, or whole selection directly into the Libraries
     panel to save it as a **Graphic** — this preserves it as an editable
     Photoshop/Illustrator object, not a flattened image.

## 4. Cloud documents and sync

Separate from Libraries, Creative Cloud also offers **cloud documents** —
`.psdc`/`.aic`-style files stored in the cloud instead of on your local
disk, so they open identically from any signed-in machine.

1. In Photoshop or Illustrator, **File > Save** (⌘/Ctrl+S) on a new document
   opens a save dialog with two tabs: **Your Computer** and **Creative
   Cloud**. Choosing **Creative Cloud** saves it as a cloud document.
2. Cloud documents show up in the Creative Cloud desktop app's **Files**
   tab and in-app under **File > Open Cloud Document**, with sync status
   icons (syncing / synced / offline edit pending) next to the filename.
3. For this course, local files saved to a normal project folder work
   fine — cloud documents matter most for actual team collaboration, but
   it's worth knowing the option exists and where to find synced files if a
   teammate ever shares one with you.

## 5. Adobe Fonts

Every Creative Cloud plan includes **Adobe Fonts**, a library of licensed
fonts you can activate for use in any Adobe app (and, for most fonts, on the
web) at no extra cost.

1. Go to [fonts.adobe.com](https://fonts.adobe.com/) while signed in, browse
   or search for a typeface, and click **Activate Fonts** (some plans
   activate the whole family with one click, others per-style).
2. Activated fonts appear immediately in the font dropdown of Photoshop,
   Illustrator, Premiere Pro (Essential Graphics text properties), and
   InDesign — no separate install step, no restart required in most cases.
3. In any font dropdown inside an Adobe app, click the **Aa** / cloud icon
   next to the search field to browse and activate Adobe Fonts directly
   from inside the app, without switching to the browser.

## Cheat sheet

| Action | Location |
|---|---|
| Install/update an app | Creative Cloud desktop app > Apps tab |
| Toggle auto-update | CC desktop app (⋯) > Preferences > Apps |
| Open Libraries panel | Window > Libraries (Photoshop/Illustrator) |
| Create a new Library | Libraries panel > library dropdown > Create new library |
| Save a color to a Library | Libraries panel > eyedropper, or drag a swatch in |
| Save a text style to a Library | Select type > Libraries panel > + (Text Style) |
| Save a graphic to a Library | Drag layer/selection into Libraries panel |
| Save as a cloud document | File > Save (⌘/Ctrl+S) > Creative Cloud tab |
| Open a cloud document | File > Open Cloud Document |
| Browse/activate Adobe Fonts | fonts.adobe.com, or the Aa icon in any font dropdown |

## How It Actually Works

A Library isn't a folder of files that gets copied around — it's a client
for a per-asset sync protocol against Adobe's Creative Cloud servers, and
understanding that model explains almost every quirk you'll hit later.

- **Each asset is its own sync unit, not the whole Library.** When you drag
  a Graphic into the Libraries panel, Adobe stores the underlying editable
  data (for a Photoshop-origin Graphic, effectively a mini-PSD with its
  layers, not a flattened bitmap) plus a rendered preview thumbnail as
  *separate* cloud objects, each with its own asset ID and version number.
  That's why updating one swatch doesn't re-upload your whole Library, and
  why a huge Library with one giant Graphic syncs that one asset slowly
  while everything else stays instantly available.
- **What a placed instance actually stores is a reference, not a copy.**
  When you place a Library Graphic into a Photoshop document, Photoshop
  embeds a **linked Smart Object** whose contents point at that asset's ID
  and current version, not a baked-in copy of the pixels at place-time.
  That reference is what makes "Update" possible later (Module 9) — the
  Smart Object re-fetches whatever version the asset ID currently resolves
  to. If you instead flatten or rasterize a placed Graphic, you sever that
  reference permanently; there's no metadata left connecting it back to the
  Library asset.
- **Sync is asynchronous and conflict-resolved by version, not by merge.**
  Each app maintains a local cache of every Library you've synced (so
  Libraries still open offline), and reconciles with the cloud on a
  change-detection loop rather than continuously streaming every keystroke.
  If the same asset is edited from two machines before either syncs, Adobe
  keeps the most recently-written version and effectively discards the
  other — there's no three-way merge like in a version-control system, which
  is why team workflows adopt a convention (one owner per asset, or naming
  variants) rather than relying on the sync layer to reconcile concurrent
  edits.
- **Character Styles store style definitions, not literal formatting.** A
  saved Character Style records the attributes (font family, size, tracking,
  color reference — itself potentially a Library color swatch) as a named,
  reusable rule, similar in spirit to a CSS class. Applying it to new text
  applies the *current* values of that rule; if you never explicitly relink
  it, later edits to the rule don't retroactively update text you formatted
  by eye instead of by applying the named style.
- **Adobe Fonts activation is a licensing handshake, not a font install in
  the OS sense.** Activating a font from fonts.adobe.com registers a license
  entitlement against your Adobe ID and pushes a font file to a
  Creative-Cloud-managed font cache that every signed-in Adobe app (and,
  separately, the OS font list for some plans) can read — it isn't dropped
  into your system Fonts folder the way a purchased font usually is, which
  is why deactivating a font in the browser can make text using it show a
  missing-font warning in every open document simultaneously, even ones you
  aren't actively editing.

## Exercise

Install Photoshop, Illustrator, and Premiere Pro via the Creative Cloud
desktop app if you haven't already. Create a new Library named
`Mastery Path Brand Kit`. Activate one Adobe Fonts family you like the look
of. Then, in Photoshop, pick any color with the eyedropper and save it to
your new Library as a swatch — you'll reuse this exact Library in Module 9
and the Module 10 capstone, so keep its name consistent.
