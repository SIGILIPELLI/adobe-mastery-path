# 04 · Team Libraries & Collaboration at Scale

Level 1 introduced a personal Creative Cloud Library for reusing assets
across your own projects. **Team Libraries** extend the same mechanism to
a group — a shared, permissioned Library that keeps every collaborator's
copy of a logo, color palette, or character style in sync in real time.
This module covers setting one up and using it in a multi-person workflow.

## 1. Creating and sharing a Team Library

1. In any Creative Cloud app's **Libraries** panel (**Window > Libraries**
   in Photoshop/Illustrator/InDesign, or the Libraries panel in
   Premiere/After Effects), click the Libraries dropdown at the top and
   choose **Create New Library**, name it (e.g. `Campaign Name — Shared`).
2. To make it a Team Library, manage sharing from
   [creativecloud.adobe.com/libraries](https://creativecloud.adobe.com) in
   a browser: open the Library, click **Collaborate** (or the share icon),
   and add collaborators by email, assigning each **Can edit** or **Can
   view** permission.
3. Alternatively, for an organization on an Adobe Teams/Enterprise plan,
   an admin can convert a Library into an org-wide Team Library from the
   **Admin Console**, making it automatically visible to every licensed
   member rather than requiring individual email invites.

## 2. What syncs, and how conflicts are handled

1. Colors, character/paragraph styles, graphics (as linked Smart Objects),
   layer styles, and brushes all sync automatically to every collaborator
   with access, generally within seconds of being added or edited by
   anyone with edit permission.
2. If two people edit the same Library asset around the same time, Adobe's
   sync resolves it by keeping the most recent save and does **not**
   silently merge conflicting versions — for anything actively being
   edited by multiple people, agree verbally/in chat on who's editing a
   given asset at a given time rather than relying on the sync to resolve
   simultaneous conflicting edits.
3. Deleting an asset from a Team Library removes it for every
   collaborator — anyone with edit access can do this, so it's worth
   agreeing on a "who can delete" norm even though the tool doesn't
   enforce one itself.

## 3. Using shared assets across apps

1. Drag any Library graphic into Photoshop/Illustrator/InDesign/AE
   exactly as in Level 1 — it lands as a linked Smart Object (or the
   app-appropriate linked equivalent), so an edit to the source Library
   asset by any collaborator propagates to every placed instance the next
   time each file is opened or the link is manually updated.
2. Library **Colors** and **Character/Paragraph Styles** appear directly
   in each app's own Swatches/Styles panels once added to a shared
   Library, so a designer building a poster and a video editor building a
   lower third can both pull the exact same brand blue without either of
   them retyping a hex value.
3. For video/motion assets specifically, save a finished **Motion Graphics
   Template** (Module 6) into the Team Library so editors across a team
   can drop a consistent, on-brand title/lower-third into any Premiere
   project without owning the source After Effects file.

## 4. Cloud Documents vs. local files in a team workflow

1. **Cloud Documents** (Photoshop `.psdc`, Illustrator `.aic`) store the
   working file itself in Creative Cloud rather than on local disk,
   syncing automatically and supporting version history from
   [creativecloud.adobe.com](https://creativecloud.adobe.com) — useful for
   fast iteration and always-available access across machines, though
   large video/print production projects with heavy linked assets often
   still favor local files plus a Team Library for shared components.
2. Cloud Documents' built-in **version history** (accessible via **File >
   Version History** in-app, or from the web) lets you review or restore
   an earlier autosaved state — a lighter-weight safety net than manual
   `_v01`/`_v02` file naming, though the two approaches are commonly used
   together on a real team.

## 5. Managing access as a project winds down

1. Review Library collaborators periodically — remove access for anyone
   who's rolled off the project via the same Collaborate/share panel used
   to add them, rather than leaving a shared Library open to former
   collaborators indefinitely.
2. Before final archival, consider converting the Team Library's key
   assets into local, embedded copies (or Packaging/Collecting the files
   that reference them, per Module 1) so the final delivered project
   doesn't depend on a Library that might later be deleted or have its
   sharing changed.

## Worked example: a two-person campaign handoff

1. Designer creates a Team Library `Product Launch — Shared`, adds the
   logo, two brand colors, and a paragraph style, and invites the video
   editor with **Can edit** access.
2. The video editor drags the logo Library graphic into an After Effects
   title composition and pulls the brand colors directly from the synced
   Swatches — no manual hex-code re-entry or file emailing.
3. The designer later refines the logo file; the editor reopens the AE
   project a day later and sees the updated logo automatically (or
   force-updates it via the Libraries panel's refresh if needed) without
   re-importing anything by hand.

## Cheat sheet — Team Libraries

| Task | Where |
|---|---|
| Open Libraries panel | Window > Libraries (most CC apps) |
| Create a new Library | Libraries panel dropdown > Create New Library |
| Share/manage collaborators | creativecloud.adobe.com > Library > Collaborate |
| Org-wide Team Library | Adobe Admin Console (Teams/Enterprise plan) |
| Cloud Document version history | File > Version History |
| Remove a collaborator | creativecloud.adobe.com > Library sharing settings |

## How It Actually Works

- **A Team Library is the identical per-asset sync mechanism from Level
  1's personal Library, with a permission layer added at the account level
  rather than any different underlying sync protocol.** Sharing a Library
  grants other Adobe IDs read/write access to the same set of cloud-stored
  asset records (each with its own asset ID and version, as covered in
  Level 1); nothing about how an asset syncs, versions, or resolves as a
  reference changes when multiple accounts can write to it — the only new
  variable is that "the most recent save wins" now has more than one
  possible writer.
- **Last-write-wins conflict resolution is a direct consequence of assets
  being versioned but not merged.** Each edit to an asset creates a new
  version record; when two edits race, the sync backend simply advances the
  asset's "current version" pointer to whichever write's timestamp is
  later, and the earlier write's content becomes an orphaned prior version
  with no automatic reconciliation of the two edits' differing changes —
  structurally identical to a last-write-wins database, not a three-way
  merge like source control. That's precisely why the module recommends a
  social/procedural fix (agree who's editing what) rather than a technical
  one — the sync layer has no merge capability to lean on.
- **A placed Library asset in another collaborator's file doesn't refresh
  itself the instant the source changes — it refreshes when that file's own
  linked-asset resolution runs (on open, or on manual update), exactly the
  "reference resolved on demand" pattern from this level's earlier
  modules.** The Library's asset list (Colors, Styles panels) updates
  quickly because that's lightweight metadata; a Graphic already placed as
  a linked Smart Object keeps referencing whatever version it was placed
  with until that specific placement's resolution step runs again — which
  is exactly why the worked example describes the editor "reopening the
  project" or manually refreshing, rather than seeing the logo change
  live while the AE project sits open.
- **Cloud Documents' version history works by the app saving discrete,
  timestamped snapshots of the whole document to cloud storage on an
  autosave cadence, each a complete restorable state — not a diff-based
  history.** Restoring an earlier version replaces the current cloud
  document's content with that snapshot's saved data wholesale; this is
  a different mechanism from a Library asset's per-asset versioning (which
  tracks one small object's history) — version history here operates at
  the scope of the entire document file.
- **Removing a collaborator's access revokes their account's permission to
  read/write that Library's asset records going forward, but does nothing
  to any copy of those assets already resolved into files on their local
  machine.** Because a linked Smart Object or a synced Style is, once
  placed, either a live reference or (if previously flattened/embedded) an
  actual local copy, revoking Library access only prevents *future*
  resolution of that reference for that account — it cannot retroactively
  remove content someone already pulled and flattened before access was
  revoked, which is exactly the reasoning behind converting key assets to
  local embedded copies before final archival.

## Exercise

Create a Team Library, add at least one color, one character/paragraph
style, and one graphic asset to it, and (if you have a second Adobe ID or
collaborator available) share it with **Can edit** access. Use the shared
color and graphic in two different apps (e.g. Illustrator and After
Effects) and confirm both pull identical values from the same synced
Library source.
