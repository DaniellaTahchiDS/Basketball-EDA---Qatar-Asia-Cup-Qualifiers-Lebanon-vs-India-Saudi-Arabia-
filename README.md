# 🏀 Basketball EDA — Qatar Asia Cup Qualifiers
### Lebanon vs. India & Saudi Arabia — Scouting Report Notebook

A Python-based exploratory data analysis notebook that breaks down player and team statistics for the Lebanese national basketball team's upcoming Qatar Asia Cup Qualifier matchups, identifying strengths, weaknesses, and strategic advantages.

---

## 📋 Overview

This notebook ingests per-game stats for all three national teams (Lebanon, India, Saudi Arabia), cleans and normalizes the data, and produces a series of visualizations culminating in a full scouting report dashboard.

---

## 📁 File Structure

```
├── basketball_eda.ipynb   # Main analysis notebook
├── Leb.csv                # Lebanon player stats (raw totals)
├── India.csv              # India player stats (per-game)
├── Saudi.csv              # Saudi Arabia player stats (per-game)
└── README.md
```

> **Note:** Lebanon's CSV stores cumulative totals. The notebook automatically converts them to per-game averages using the `GP` (games played) column.

---

## 🔧 Requirements

```bash
pip install pandas numpy matplotlib seaborn
```

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, cleaning, aggregation |
| `numpy` | Normalization and numerical ops |
| `matplotlib` | All chart rendering |
| `seaborn` | Heatmap visualization |

---

## 📊 Notebook Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | **Imports & Setup** | Libraries, plot styling, team color palette |
| 2 | **Load & Clean Data** | CSV ingestion, column normalization, Lebanon totals to per-game conversion, DNP filter |
| 3 | **Team Aggregate Stats** | Per-game team totals table with conditional formatting |
| 4 | **Radar Chart** | Normalized multi-category spider chart comparing all three teams |
| 5 | **Shooting Efficiency** | Side-by-side bar charts for FG%, 3P%, and FT% |
| 6 | **Scoring vs. Minutes** | Bubble scatter plot (bubble size = FG% efficiency) |
| 7 | **Ball Security** | Assists vs. Turnovers scatter with quadrant annotations |
| 8 | **Defensive Heatmap** | Row-normalized heatmap across steals, blocks, rebounds, fouls, TOV |
| 9 | **Lebanon Player Contributions** | Horizontal bar charts for PPG, RPG, APG, SPG per player |
| 10 | **3PT Volume vs. Efficiency** | Scatter plot of 3PA vs. 3P% (bubble size = PPG) |
| 11 | **Scouting Report Dashboard** | Full 6-panel summary figure with key scouting notes |
| 12 | **Key Insights Summary** | Printed console output of actionable scouting findings |

---

## ▶️ Running the Notebook

1. Place `Leb.csv`, `India.csv`, and `Saudi.csv` in the same directory as the notebook.
2. Open in Jupyter or Google Colab.
3. Run all cells (`Runtime > Run all` in Colab, or `Kernel > Restart & Run All` in Jupyter).

---

## 📌 Key Findings

**Lebanon Strengths**
- Highest FT% of the three teams (54.2%)
- Best ball movement: 18.5 APG
- Elite anchor in Wael Arakji (20 PPG / 5 APG / 5 RPG)
- Dominant rebounding via Dedric Lawson (11.5 RPG)

**Lebanon Weaknesses**
- Lowest 3P% (17.6%) — poor perimeter shooting
- Tied for most turnovers (15.5 TOV/game)
- Lowest steals rate (5.5 SPG) among the three teams

**vs. India** — Most favorable matchup; India's 23.8% FG% is exploitable with disciplined half-court defense and controlled tempo.

**vs. Saudi Arabia** — Toughest matchup; Abdur-Rahkman (23.5 PPG) requires dedicated double-team schemes. Saudi Arabia leads in FG% (52.2%) and blocks (4 BPG).

---

## 🎨 Visual Style

All plots use a consistent white/light-gray aesthetic with team-specific colors:

| Team | Color | Hex |
|------|-------|-----|
| Lebanon | Red | `#C8102E` |
| India | Saffron | `#FF9933` |
| Saudi Arabia | Green | `#006C35` |

---

## 📝 Notes

- Players with fewer than 5 minutes per game are excluded from all analyses.
- Percentage columns (FG%, 3P%, FT%) are averaged across players; counting stats are summed to team totals.
- The radar chart normalizes each category min-max across the three teams; a floor of 0.15 is applied to prevent zero-value spokes from collapsing.
