# Fantasy Football Optimization-Project  
This project builds a complete NFL fantasy football lineup optimizer using **Pyomo**, **pandas**, and **Colab**. The model simulates optimal DraftKings lineups using both real Week 17 performance data and historical season trends.

---

##  Data Sources

- **DKSalaries.csv**: Player salaries and average points.
- **NFL2024SeasonStats.xlsx**: Full season player stats (Passing, Rushing, Receiving, Defense).
- **NFLWeek17Stats.csv**: Actual performance data for Week 17.

---

##  Process Overview

1. **Data Cleaning & Merging**  
   Merged salaries, season stats, and Week 17 performance while handling mismatches and missing data.

2. **Fantasy Scoring Logic**  
   Custom functions calculated fantasy points based on DraftKings rules for both offense and defense.

3. **Optimization Model (Pyomo)**  
   Built two models:
   - **Cheat Code Model**: Uses actual Week 17 points to find the perfect lineup.
   - **Predictive Model**: Uses season averages + constraints to predict the best lineup.

4. **Constraints Included**
   - Salary cap ($50,000)
   - Roster structure: 1 QB, 2 RB, 3 WR, 1 TE, 1 FLEX, 1 DST
   - Max 9 players
   - Must include players from ≥ 2 games
   - Exclude QBs in top 10% for interception rate
   - Require stacking: QB paired with WR/TE from same team
   - Require ≥ 4 players with consistent scoring (AvgPointsPerGame ≥ 10)

---

##  Results

- **Week 17 Optimized Lineup**:
  - QB: Drew Lock
  - RBs: Jonathan Taylor, Bucky Irving
  - WRs: Tee Higgins, Malik Nabers, Ricky Pearsall
  - TE: Trey McBride
  - FLEX: Zach Ertz
  - DST: Broncos
- **Max Fantasy Points**: 277.89  
- **Total Salary Used**: $50,000

---

##  Notes

- This project was built entirely in **Google Colab** with Pyomo and HiGHS as the solver.
- Thorough data exploration was done to test assumptions (e.g. home vs. away performance, stacking benefits, age effects).
- All source files are included in the repository.

---
