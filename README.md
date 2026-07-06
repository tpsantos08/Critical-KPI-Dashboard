# AIK Critical KPI Dashboard

A static HTML dashboard that reads KPI data directly from your Excel files — no conversion, no build step.

## How It Works

```
aik-kpi-dashboard/
├── index.html                          ← open this (or deploy to GitHub Pages)
├── data/
│   ├── 6_KPI_Match_by_match.xlsx       ← add new match rows here
│   └── 6_KPI_League.xlsx              ← update league averages here
└── README.md
```

The dashboard uses [SheetJS](https://sheetjs.com/) to parse the `.xlsx` files directly in the browser. No Python, no Node, no build step.

## Adding a New Match

1. Open `data/6_KPI_Match_by_match.xlsx` in Excel
2. Add a new row at the bottom with the match data
3. Save the file
4. Push to GitHub → dashboard updates automatically

**Required columns** (must exist in your Excel file):

| Column | Example |
|--------|---------|
| `Matchday` | `Matchday MD 10` |
| `Team` | `AIK Solna (H) 3:1` |
| `Date` | `31.05.2026` |
| `Opposition` | `IFK Norrköping` |
| `xG Difference` | `1.15` |
| `Breaking Opponent Defence` | `52` |
| `Ball Progression` | `410` |
| `Defensive Ball Control` | `130` |
| `Critical Ball Loss Number` | `7` |
| `Offensive Ball Wins (from Defenders)` | `11` |

The `Team` column is parsed to extract the result (H/A and score).

## Updating League Averages

1. Open `data/6_KPI_League.xlsx`
2. Update the numbers on the `data` sheet
3. Save and push

## Changing KPIs

Edit the `KPIS_OFFENSIVE` and `KPIS_DEFENSIVE` arrays at the top of `index.html`. The `key` must match the column name in both Excel files.

## Deploy to GitHub Pages

1. Create a new GitHub repository
2. Push all files
3. Go to **Settings → Pages → Source: Deploy from branch → main / root**
4. Live at `https://yourusername.github.io/aik-kpi-dashboard/`

## Rank Colours

| Rank | Colour |
|------|--------|
| 1–4  | 🔵 Blue `#0000FF` |
| 5–8  | 🟢 Green `#00BF00` |
| 9–12 | 🟡 Yellow `#F2DD41` |
| 13–16 | 🔴 Red `#FF0000` |
