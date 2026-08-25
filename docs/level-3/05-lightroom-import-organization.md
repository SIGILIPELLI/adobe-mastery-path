# 05 · Lightroom Classic Import & Organization

This module shifts apps to **Lightroom Classic**, Adobe's dedicated photo
cataloging and editing tool. Before any color grading (Module 6), a shoot
needs to get in, get organized, and get findable — this module covers the
Catalog, Import dialog, keywording, collections, and ratings/flags that
make a large photo library manageable.

## 1. The catalog

1. Lightroom Classic organizes everything through a **catalog** file
   (`.lrcat`) — a database of every photo's location, edits, and metadata.
   The catalog does not store the photos themselves (unless you choose to
   copy them into a managed folder on import); it references files on disk.
2. **File > New Catalog...** to start fresh, or **File > Open Catalog...**
   to switch. Most working photographers use one ongoing catalog for all
   their work rather than a new catalog per project.
3. Back up the catalog regularly: **Catalog Settings > Back Up** (or the
   prompt Lightroom shows on quitting) — losing the catalog loses all edit
   history and organization even though the original photos are untouched.

## 2. Importing photos

1. **File > Import Photos and Video...** (or plug in a card/drive and
   Lightroom may prompt automatically). The Import dialog splits into a
   source panel (left), a preview grid (center), and destination/settings
   (right).
2. Choose the import method at the top: **Copy** (duplicates files from a
   card into your chosen folder — the standard choice for memory cards),
   **Move** (relocates files, deleting the originals from the source),
   or **Add** (catalogs files that are already in their final location on
   disk without moving anything).
3. On the right, set:
   - **File Handling > Build Previews**: Standard or 1:1 for faster
     zoomed review immediately after import.
   - **File Renaming**: apply a naming template (e.g.
     `ShootName_00001.dng`) so files are never left with camera-default
     names like `_DSC0001`.
   - **Apply During Import > Metadata**: attach a saved metadata preset
     (copyright, contact info) and initial **Keywords** common to the
     whole shoot.
   - **Destination**: the folder structure to copy into, e.g. organized by
     date or by shoot name.
4. Click **Import** in the bottom-right. Progress shows in the top-left
   activity indicator; thumbnails populate the **Library** module's grid
   as previews render.

## 3. The Library module: Grid, Loupe, and flags/ratings

1. Press **G** for **Grid** view (thumbnails) and **E** for **Loupe** view
   (single-image, full detail) — **Spacebar** also toggles between them
   on the selected photo.
2. Cull a shoot quickly using flags and star ratings:
   - **P** — flag as **Pick** (keeper)
   - **X** — flag as **Reject**
   - **1-5** — apply a star rating
   - **6-9** — apply a color label
3. After an initial pass, use the **Filter Bar** (top of the Grid, press
   **\\** if hidden) to show only Picks, or only 4-5 star images, then
   **Edit > Select All** and **Photo > Delete Rejected Photos** to clear
   out the rejects from both the catalog and disk (with confirmation).

## 4. Keywording and metadata

1. Select one or more photos and use the **Keywording** panel (right panel
   in Library, **Window > Panels > Keywording**) to type comma-separated
   keywords — apply to multiple selected photos at once to tag a whole
   batch (e.g. `client-name, product-shoot, studio`) in one action.
2. Build a reusable **Keyword List** (own panel below Keywording) with a
   hierarchy (e.g. `Clients > Acme Co > 2026 Campaign`) so keywords stay
   consistent shoot to shoot instead of being retyped freehand each time.
3. **Metadata** panel shows/edits EXIF (camera, lens, exposure — read-only)
   alongside editable fields like **Title**, **Caption**, and **Copyright**.

## 5. Collections and Smart Collections

1. Right-click **Collections** in the left panel > **Create Collection...**
   to build a named, manually-curated set of photos independent of folder
   location — drag any photo from Grid view onto a collection to add it.
2. **Collection Sets** (right-click > **Create Collection Set...**) group
   related collections together, e.g. a `2026 Campaign` set containing
   separate `Selects`, `Client Delivery`, and `Behind the Scenes`
   collections.
3. **Create Smart Collection...** builds a rule-based collection that
   auto-populates based on criteria (e.g. "Rating is 4 stars or more AND
   Keyword contains product-shoot") — it updates automatically as ratings
   and keywords change, unlike a manually curated Collection.

## Worked example: organizing a product shoot

1. Import 100+ shots from a card via **Copy**, applying a
   `ProductShoot_2026-08-25_00001` file naming template and a base
   `client-name, product-shoot` keyword during import.
2. Cull in Loupe view: **P** for keepers, **X** for clear misses, working
   through the whole set once before deleting anything.
3. Filter to Rejects, delete them from disk; filter to Picks, and apply
   star ratings (5 for hero shots, 3 for supporting) to the remainder.
4. Create a Collection Set `Product Shoot — Client Name` containing a
   `Selects` collection (drag the 5-star picks in) and a Smart Collection
   rule for "4 stars or more" as a wider safety net for delivery.

## Cheat sheet — Lightroom import & organization

| Task | Where / shortcut |
|---|---|
| New/open catalog | File > New Catalog... / Open Catalog... |
| Import photos | File > Import Photos and Video... |
| Grid / Loupe view | G / E (Spacebar toggles) |
| Flag Pick / Reject | P / X |
| Star rating | 1-5 |
| Show/hide Filter Bar | \\ |
| Add keywords to selection | Keywording panel |
| New Collection / Collection Set | Right-click Collections > Create... |
| Rule-based auto collection | Create Smart Collection... |

## Exercise

Import a folder of at least 20 photos with a file-renaming template and a
base keyword applied during import. Cull with Pick/Reject flags, delete
rejects, star-rate the keepers, and build a Collection Set containing a
manually curated Selects collection plus a Smart Collection filtering by
star rating.
