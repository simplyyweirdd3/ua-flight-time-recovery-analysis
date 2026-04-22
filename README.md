# United Airlines Flight Time Recovery Analysis
**Course:** DATA 5300 - Applied Statistical Inference & Experimental Design  
**Institution:** Seattle University, MS in Data Science  
**Term:** Fall 2025  
**Team:** Hamda H, Ruman S, Aaron D, Carter W  
**Type:** Group Project (Individual Contribution)

---

## Overview

Can United Airlines pilots actually "make up" time once a flight is in the air? This project investigates whether delayed UA flights recover time during flight, and what factors influence how much time is gained or lost. The analysis uses the `nycflights13` dataset and applies statistical inference methods including Welch t-tests, confidence intervals, and multiple linear regression.

This repository contains **my individual code contribution** to the group project.

---

## Research Questions

1. Do flights that depart late gain more time in the air than on-time flights?
2. What are the five most common UA destinations from NYC, and how does average gain differ across them?
3. Does gain per flight hour differ for longer vs. shorter flights?

---

## Dataset

- **Source:** `nycflights13` R package
- **Subset:** United Airlines (carrier code: UA) flights departing NYC
- **Engineered variables:**
  - `net_gain` = departure delay − arrival delay
  - `air_time_hr` = air time converted to hours
  - `gain_per_hour` = net gain / air time in hours
  - `late_dep` = departure delay > 0 minutes
  - `late30_dep` = departure delay > 30 minutes

---

## Methods

- Feature engineering of gain and per-hour gain metrics
- Exploratory analysis with boxplots and QQ plots across delay subgroups
- Welch two-sample t-tests comparing on-time vs. late departure groups
- 95% confidence intervals for average gain by delay category and distance group
- Multiple linear regression modeling gain with air time, distance, and destination as predictors
- Distance-based grouping (0–800, 800–2000, 2000–3000, 3000–5000 miles) to examine how flight length affects recovery

---

## Tools & Technologies

- **Language:** R
- **Libraries:** `nycflights13`, `dplyr`, `ggplot2`, `tidyr`
- **Output:** R Markdown rendered as HTML

---

## Key Findings

- On-time/early flights gained an average of **3.90 minutes per hour** vs. **3.18 minutes per hour** for late departures - a statistically significant difference (p < 0.001)
- Flights delayed more than 30 minutes consistently showed the lowest time recovery
- UA flights recovered roughly **7–9 minutes** on average across the top 5 destinations (ORD, IAH, SFO, LAX, DEN), with similar patterns across all five
- **Air time** was the strongest predictor of gain in the regression model; distance alone was not significant
- Shorter flights (0–800 miles) had the highest average gain (μ = 7.71 min); longer flights (3000–5000 miles) had the lowest (μ = 1.03 min)
- **Bottom line:** Preventing departure delays matters more than expecting pilots to recover time in the air

---

## Files

| File | Description |
|------|-------------|
| `Project_2_Code_Ruman_Sidhu.html` | Rendered R Markdown with full analysis, visualizations, and model output |
| `DATA_5300_Project2_Presentation.pdf` | Group presentation slides |

> **Note:** This was a collaborative course project. The code and analysis in this repo represent my individual contribution to the group's work.

---

## About

Part of the MS in Data Science program at Seattle University. This course covered statistical inference, experimental design, confidence intervals, and hypothesis testing using real-world flight data.
