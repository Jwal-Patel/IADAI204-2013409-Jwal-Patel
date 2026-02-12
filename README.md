# 🏏 IPL Match-Winning Analysis  
## Player Performance, Rivalries & Toss Impact

---

## 📌 Project Overview

This project analyses IPL match data to identify key factors that influence match outcomes, including batting dominance, bowling effectiveness, team rivalries, and toss decision impact.

The objective was to build an interactive Tableau dashboard that provides actionable insights for:

- IPL franchises (strategic planning)
- Coaches (player performance evaluation)
- Broadcasters (rivalry narratives)
- Fans (performance trends)

The dashboard enables dynamic filtering by season and team, allowing stakeholders to explore patterns across different IPL eras.

---

## 📊 Dataset Summary

### Data Source
IPL match-level and ball-by-ball datasets:
- matches.xlsx
- deliveries.xlsx

### Structure
- matches → Match-level data (season, venue, toss decision, winner, teams)
- deliveries → Ball-by-ball data (runs, wickets, batter, bowler)

### Join Used
deliveries.Match Id = matches.Id  
Relationship type: Inner Join

---

## 🧹 Data Cleaning & Preparation

- Verified join consistency between Match Id and Id.
- Checked for NULL winners.
- Standardized date and season formats.
- Ensured numeric datatype for Batsman Runs, Total Runs, and Ball.
- Created calculated metrics for advanced analysis.
- Excluded run-outs from bowler wicket calculations.

---

## 📐 Calculated Fields Created

### Strike Rate
(SUM([Batsman Runs]) / COUNT([Ball])) * 100

### Economy Rate
SUM([Total Runs]) / (COUNT([Ball]) / 6)

### Wickets (Exclude Run Out)
IF [Dismissal Kind] != "run out" THEN 1 ELSE 0 END

### Toss Win Conversion
IF [Winner] = [Toss Winner] THEN "Won After Toss"
ELSE "Lost After Toss"
END

---

## 🔍 Exploratory Data Analysis

- Top 10 Batters identified based on total runs.
- Top 10 Bowlers identified using wickets excluding run-outs.
- Rivalry heatmap created to analyse head-to-head frequency.
- Toss impact analysed across decisions and seasons.
- Season-wise toss trend evaluated using stacked bar chart.

---

## 🖥 Dashboard Features

- Interactive Season filter
- Dynamic updates across all visualisations
- Heatmap for rivalry intensity
- Bar charts for batting and bowling leaders
- Stacked bar for toss conversion
- Season trend analysis

---

## 📊 Key Insights

1. Virat Kohli leads IPL all-time scoring.
2. R. Ashwin is among the top wicket-takers.
3. Rivalries like CSK vs MI dominate match frequency.
4. Fielding first has increased in popularity post-2016.
5. Toss advantage alone does not guarantee victory.

---

## ✅ Testing & Validation

- Manually verified strike rate calculations.
- Confirmed exclusion of run-outs.
- Checked dashboard filter functionality.
- Ensured logical storytelling flow.

---

## 📌 Conclusion

IPL outcomes are influenced by batting consistency, bowling strength, rivalry history, and evolving toss strategies. However, sustained player performance remains the strongest determinant of success.

---

## 🔮 Future Scope

- Predictive modeling for match outcomes.
- Phase-based (Powerplay, Middle, Death) performance analysis.
- Venue-based toss influence modelling.

---

## 👤 Student Details

Name: Jwal Kiranbhai Patel 
Student ID: 2013409  
CRS: Artificial Intelligence  
Course: The Art of Storytelling with Data  
School: Udgam School For Children  
