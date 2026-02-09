# Penalty Kick Project

This project analyzes how **run-up step routines** relate to **shot placement** and **outcomes** in soccer penalty kicks. Using a hand-coded dataset of 300 penalty attempts, we study whether deviations from a kicker’s normal run-up length are associated with differences in accuracy or placement within the goal.

The analysis was completed as part of **STOR 538** and includes a full statistical write-up, visualizations, and reproducible code.

---
```
penalty-kick-project/
├── README.md
├── code/
│ └── Penalty_Kick_Project.Rmd
├── data/
│ └── Champ_Data.csv
├── paper/
│ └── STOR538_Championship.pdf
├── figures/
│ ├── fig1_steps.pdf
│ └── fig2_ball_steps.pdf
```
---

## Data Description

Each row in the dataset represents a single penalty kick. Key variables include:

- `steps` – number of run-up steps taken before the shot  
- `ball_position` – shot quadrant (1–6 in goal, 7 = off-target)  
- `g_position` – goalkeeper dive quadrant (1–6)  
- `result` – goal, save, or miss  
- `foot` – kicker’s shooting foot (left/right)  
- `k_ability`, `g_ability` – historical penalty performance metrics  

The dataset was constructed using Transfermarkt and manual video coding from YouTube.

---

## Methods Summary

- Step routines are classified using the empirical distribution of step counts:
  - **Shortened:** fewer than 4 steps  
  - **Normal:** 4–8 steps (25th–75th percentile range)  
  - **Lengthened:** more than 8 steps
- Visual analysis includes:
  - boxplots of steps vs outcome
  - heatmaps of ball placement by step routine
- Statistical tests include:
  - Shapiro–Wilk tests for normality
  - Wilcoxon rank-sum test (steps vs outcome)
  - Chi-square tests of independence (step routine vs placement)

---

## How to Run the Code

### Option 1: RStudio 

1. Clone or download this repository.
2. Open `code/Penalty_Kick_Project.Rmd` in RStudio.
3. Install required packages (first time only):

```r
install.packages(c("tidyverse", "ggplot2", "scales", "viridis", "here"))
```
### Option 2: R Console
```
install.packages(c("rmarkdown", "tidyverse", "ggplot2", "scales", "viridis", "here"))
rmarkdown::render("code/Penalty_Kick_Project.Rmd")
```

