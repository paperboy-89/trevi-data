# Trevi Competitor Sheet — How It Works

## What this sheet controls
Six hosted files read this sheet when you click **Check for updates**:

- `wholesale-unified.html` — Trevi Wholesale Partnership Program
- `industrial-unified.html` — Trevi Industrial Hydration
- `bulk-unified.html` — Trevi Bulk Direct Program (teams, offices)
- `team-program.html` — Trevi Team Hydration Program (high-school sports)
- `comparison.html` — Standalone comparison chart
- `comparison-price.html` — Comparison chart with editable Trevi price

Each one updates: the Trevi vs. Competitors chart, the Price per stick / Cost to reach 820 mg rows, the powder multiplier, the Sources & Methodology page, and the "data as of" date.

## Tab 1 — Competitors (one row per brand)
- Columns: Brand, Flavor, Retailer, Pack name, Pack price $, Pack count, Listing URL, Last checked
- Sodium / Potassium / Magnesium / Calcium / Chloride / Phosphorus mg — as printed on the label. Leave blank if not declared (shows as —).
- Stick grams — net weight of one stick from the label. The file computes "N× the powder" vs. Trevi (Stick grams ÷ Trevi Everyday stick grams). Blank = no multiplier shown.
- Flavor type, Sweetener, Artificial colors, First two ingredients — plus "flagged" columns (TRUE/FALSE) that turn the cell red.
- "Show only with extended toggle" = TRUE hides the brand unless the Liquid I.V. + LMNT toggle is on.
- Price per stick is calculated (Pack price ÷ Pack count). Don't type it.
- Do not rename column headers. Row order = column order in the chart.

## Tab 2 — Settings (key in column A, value in column B)
| Key | What it does | Used by |
|---|---|---|
| Data as of | Date under the chart and on the methods page. Update whenever you change a price. | all |
| Source note 1, 2, 3… | Bullet list on the Sources page | all |
| Disclosure | One-line note printed under the chart. Write `[date]` where you want the Data-as-of date inserted. Blank = no line. | all |
| Trevi Everyday flavor | Flavor label under the Trevi Everyday header | all |
| Trevi Sport flavor | Flavor label under the Trevi Sport header | all |
| Trevi Everyday stick grams | Trevi Everyday stick weight (3.5). Base for the powder multiplier. | all |
| Trevi Sport stick grams | Trevi Sport stick weight (8.2) | all |
| Trevi wholesale price / …note | Optional override of Trevi's per-stick price + caption | wholesale-unified |
| Trevi direct price / …note | Optional override | industrial-unified |
| Trevi bulk price / …note | Optional override | bulk-unified |
| Trevi team price / …note | Optional override | team-program |
| Trevi price / …note | Optional override | comparison, comparison-price |

Keys must be spelled exactly (capitalization doesn't matter). Blank value = file uses its built-in default.

**Leave the Trevi price rows blank.** Each packet derives Trevi's comparison price from its own Pricing page (first tier ÷ 20, or the Starter package for team-program), so the chart always matches the pricing you chose in the toolbar. Only fill a price row if you want to force a different number.

## How to update
1. Edit cells here. Google auto-saves; the published copy refreshes within ~1 minute.
2. Open the hosted file at its github.io URL — **not** a downloaded copy.
3. Click **Check for updates**. The status line confirms brand count and date.
4. Set the pricing model, toggles, order method, terms and company name, then Print → Save as PDF.
5. Everything you set in the toolbar clears when you close the tab.

## Things to be mindful of
- **"Could not reach source"** = the file was opened from your computer, or the sheet isn't published. It falls back to built-in data and says so.
- Trevi mg values (170 / 190 / 75 / 60 / 260 / 65 = 820; Sport 2,185) are built into the files, not this sheet. Formula changes need a file update.
- A 7th brand works but the chart gets tight — check the PDF.
- Removing Gatorade affects nothing today; it will matter if the "2.3–6.2x" live claim is added.
- A Tweaks price override typed in the file wins over the sheet.
- Deleting a column header breaks that column everywhere. Hide instead of delete.
- Keep Last checked and Data as of consistent — the Sources page shows both.
