# Trevi Industrial Packet — Live Data Setup

The Live packet reads `competitor-data.json`. Edit the JSON, click **Check for updates** in the packet, confirm the chart and Sources page, then save the PDF.

## 1. Host the JSON on GitHub (one-time, ~10 min)

GitHub Pages only serves from **private** repos on paid plans (Pro / Team). The JSON contains only public label and listing data, so a small **public** repo holding just this one file is the practical route.

1. github.com → **New repository** → name it `trevi-data` → Public → Create.
2. **Add file → Upload files** → drop `competitor-data.json` → Commit.
3. Repo **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / root → Save.
4. After ~1 minute your file is live at:
   `https://<your-username>.github.io/trevi-data/competitor-data.json`
5. Send me that URL and I'll bake it into the packet and re-export. (Or paste it into Tweaks → Export → `dataUrl` yourself.)

## 2. Editing in GitHub's web UI

Open `competitor-data.json` in the repo → pencil icon → edit → **Commit changes**. Pages republishes in about a minute. Then open the packet and click **Check for updates**.

Validate before committing: paste the file into jsonlint.com if you're unsure — a missing comma breaks the whole file and the packet will fall back to its last good data.

## 3. What each field does

Top level:
- `asOf` — printed in the footnotes and on the Sources page. Update it whenever you change a price.
- `brands` — one entry per competitor column, in display order. Trevi columns are fixed in the packet.
- `sources` — free-text lines on the Sources page. Listing lines are added automatically from each brand's `listing`.

Per brand:
- `name`, `flavor` — column header.
- `ext: true` — hides the brand unless the "Liquid I.V. + LMNT" toggle is on (use for secondary comparisons).
- `listing` — `retailer`, `pack`, `packPrice`, `packCount`, `url`. Price per stick = packPrice ÷ packCount. Set `price` directly to override.
- `na`, `k`, `mg`, `ca`, `cl`, `p` — mg per stick. Use `null` when not on the label; it prints as "—". Total and "x of 6 minerals" are calculated.
- `powder` — multiplier for the "× the powder" note under Sticks needed. Omit to hide the note.
- `stickNote` — small note under Sticks needed when a brand reaches 820 mg in one stick (e.g. "+ 11 g sugar").
- `vitamins`, `sugar`, `salt`, `flavor_type`, `sweetener`, `colors`, `first2` — each is `{ "t": "cell text", "note": "small text", "bad": true }`. `bad` turns the cell red. Use `\n` in `t` for a manual line break.

## 4. Adding or removing a brand

Add or delete a whole `{ … }` block inside `brands`. The chart adds or removes the column and widths adjust. Six competitor columns fit comfortably; beyond that, mark extras `ext: true`.

## 5. Workflow

1. Edit JSON on GitHub → Commit.
2. Open the packet HTML → **Check for updates** → status line confirms "Updated · data as of …".
3. Toggle flavors / brands as needed, type the customer name.
4. Print → Save as PDF.
