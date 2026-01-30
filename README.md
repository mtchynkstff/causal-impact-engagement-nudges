# Evaluating the Causal Impact of Engagement Nudges in an Education Platform

## Overview

This project evaluates whether a targeted engagement nudge intervention causally improves student engagement on an education platform. Using a randomized experimental design and a difference-in-differences (DiD) framework, the analysis estimates the intervention’s effect on weekly student activity and examines how impacts vary by baseline engagement level.

The goal of this project is not only to estimate statistical effects, but to translate those effects into **decision-relevant insights** about where and how such an intervention should be deployed.

---

## Key Results (Executive Summary)

- The intervention increased engagement by **+0.37 active days per week**  
  (95% CI: [0.32, 0.42]), representing an **~11% lift** over baseline.
- Effects were substantially larger for students with low baseline engagement:
  - **Low-engagement students:** +0.54 active days/week
  - **Higher-engagement students:** +0.30 active days/week
- Over the six-week post-intervention period, this translates to:
  - **~2.2 additional active days per student overall**
  - **~3.2 additional active days** for low-engagement students
- A student-level robustness check yields a similar directional estimate.

**Decision implication:** Results support **targeted deployment** of engagement nudges to lower-engagement students rather than a blanket rollout.

---

## Problem Framing

**Primary question:**  
> Did the engagement nudge intervention causally increase student engagement?

**Secondary questions:**
- How large is the effect in practical (not just statistical) terms?
- Does the effect differ for students with different baseline engagement levels?
- Is the intervention likely to be efficient if deployed broadly?

---

## Data

### Synthetic Dataset

Due to privacy and access constraints around real student-level experimental data, this project uses a **synthetic dataset** designed to reflect realistic patterns observed in education platforms.

The synthetic data generation process:
- Preserves realistic distributions of engagement and performance
- Incorporates time trends (e.g., engagement fatigue)
- Embeds a modest, heterogeneous treatment effect
- Allows for missing observations and noise

The purpose of the synthetic data is to demonstrate **experimental design, causal inference, and decision-making**, not to make empirical claims about a real population.

### Unit of Analysis

- **Student-week panel**
- ~8,000 students observed over 12 weeks
- 6-week pre-intervention period, 6-week post-intervention period

---

## Methodology

### Experimental Design
- Stratified randomization by grade level and socioeconomic band
- Balanced treatment and control groups at baseline

### Causal Framework
- **Difference-in-Differences (DiD)** to estimate treatment effects
- Validation of identifying assumptions via:
  - Baseline balance checks
  - Pre-period trend analysis
  - Placebo intervention tests

### Statistical Models
- Panel DiD regression with grade-level and SES controls
- Heterogeneity analysis by baseline engagement
- Student-level pre/post aggregation as a robustness check

Robust (HC3) standard errors are used throughout.

---

## Repository Structure

- `data/`
  - `synthetic_student_week_data.csv`
- `notebooks/`
  - `01_data_generation.ipynb`
  - `02_experimental_validation.ipynb`
  - `03_difference_in_differences.ipynb`
- `decision_memo.md`
- `README.md`

---

### Notebook Guide

- **01_data_generation.ipynb**  
  Constructs the synthetic dataset and documents the data-generating assumptions.

- **02_experimental_validation.ipynb**  
  Validates randomization, checks baseline balance, assesses parallel trends, and runs placebo tests.

- **03_difference_in_differences.ipynb**  
  Estimates causal effects, explores heterogeneity, computes cumulative impacts, and connects results to decisions.

---

## Interpretation & Decision Context

While the estimated effects are modest in weekly terms, they accumulate meaningfully over time—particularly for students at risk of disengagement. The results suggest diminishing returns among already-engaged students, making targeted deployment the most effective strategy.

This project emphasizes **decision-relevant analytics**: not just whether an intervention works, but *for whom* it works best and *how* it should be deployed.

---

## Limitations

- Outcomes focus on short-term engagement; longer-term academic impacts are not evaluated.
- Results depend on assumptions embedded in the synthetic data-generating process.
- Cost data is not incorporated, so conclusions reflect effectiveness rather than cost-effectiveness.

---

## Skills Demonstrated

- Experimental design and validation
- Difference-in-differences causal inference
- Panel data analysis
- Heterogeneous treatment effects
- Robustness and placebo testing
- Translating statistical results into decisions
- Clear technical communication

---

## Author

Created by a former middle school, high school, and AP social studies teacher transitioning into data science and EdTech, with a focus on data-driven analysis and applied insights.