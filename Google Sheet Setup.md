# Trevi Industrial Packet — Google Sheet Setup

The Live packet can read its competitor data straight from a Google Sheet. Edit cells, click **Check for updates** in the packet, save the PDF.

## 1. Create the sheet (one-time, ~5 min)

1. sheets.google.com → Blank spreadsheet → name it **Trevi Competitors**.
2. File → Import → Upload → `trevi-competitors-sheet.csv` → Import location: **Replace current sheet**. Rename the tab **Brands**.
3. Add a second tab (+ at bottom) named **Settings** → File → Import → `trevi-competitors-settings.csv` → **Replace current sheet** (make sure you're on the Settings tab).
4. Tidy: select the flag columns (Sugar flagged, Flavor flagged, Sweetener flagged, Colors flagged, First two flagged, Show only with extended toggle) → Insert → Checkbox. Freeze row 1 (View → Freeze → 1 row).

## 2. Publish it

1. File → Share → **Publish to web**.
2. Under *Link*: choose the **Brands** tab (not Entire Document) and **Comma-separated values (.csv)** → Publish → copy the link.
3. Repeat for the **Settings** tab → copy that link too.
4. Done — both links are baked into the packet. If you ever re-publish or move the sheet, paste the new links into Tweaks → Live data → `sheetUrl` and `settingsUrl`.

Published links update ~1 minute after you edit. Nobody needs a Google login to read them, and the sheet itself stays private — only the published CSV is public.

## 3. Columns

Brands tab — one row per competitor, in display order. Leave a cell blank when it doesn't apply.

- **Brand**, **Flavor** — column header in the chart.
- **Show only with extended toggle** — check for secondary brands (Liquid I.V., LMNT).
- **Retailer**, **Pack name**, **Pack price $**, **Pack count**, **Listing URL** — price per stick is Pack price ÷ Pack count. Listing details print on the Sources page.
- **Sodium / Potassium / Magnesium / Calcium / Chloride / Phosphorus mg** — from the label. Blank = not listed, prints "—". Total and "x of 6 minerals" are calculated.
- **Powder multiplier** — the "× the powder" note under Sticks needed. Blank hides it.
- **Stick note** — small note when a brand hits 820 mg in one stick (e.g. "+ 11 g sugar").
- **Vitamins** / **Vitamins note**, **Added sugar** / **Sugar note**, **Pink Himalayan salt**, **Flavor type**, **Sweetener**, **Artificial colors**, **First two ingredients** / **First two note** — cell text and small text under it.
- **… flagged** checkboxes — tick to color that cell red.
- Type ` / ` (space-slash-space) in a text cell to force a line break, e.g. `Natural + / artificial`.

Settings tab:
- **Data as of** — printed in footnotes and Sources page. Update whenever a price changes.
- **Source note 1, 2, …** — free-text lines at the top of the Sources page. Add more rows as needed.

## 4. Adding or removing a brand

Add a row (or delete one) on the Brands tab. The chart adds or removes the column. Six competitor columns fit comfortably; past that, tick "Show only with extended toggle" on the extras.

## 5. Workflow

1. Edit the sheet.
2. Open the packet → **Check for updates** → status reads "Updated · N brands · data as of …".
3. Toggle sections, type the customer name.
4. Print → Save as PDF.

Note: the GitHub JSON still works as a fallback — if `sheetUrl` is blank the packet reads `competitor-data.json` as before.
