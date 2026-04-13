# Winning Factors in Professional Tennis — DSA 210 Term Project

## Motivation

Tennis matches are often decided by very small differences in performance. Some players win mainly through powerful serves, while others succeed with consistency, fewer mistakes, or stronger performance under pressure. This project explores whether these differences can be explained systematically using match-level data rather than only by observation.

## Research Question

**Which match statistics are most strongly associated with winning in professional ATP tennis?**

## Data Sources

| Source | Description | Link |
|--------|-------------|------|
| ATP Match Data | Match-level statistics (aces, double faults, serve %, break points, etc.) for 2019–2023 seasons | [JeffSackmann/tennis_atp](https://github.com/JeffSackmann/tennis_atp) |
| Player Data (enrichment) | Player biographical data — handedness, date of birth, nationality | Same repository (`atp_players.csv`) |

The match data is enriched with player biographical variables that are not present in the match-level files, allowing investigation of whether factors such as handedness or age interact with serve statistics in determining match outcomes.

## Project Structure

```
Melisa_Tasli_DSA210/
├── README.md                           # This file
├── requirements.txt                    # Python dependencies
├── DSA 210 PROJECT PROPOSAL.pdf        # Original proposal
├── DSA210_Updated_Proposal.docx        # Updated proposal with enrichment details
└── dsa210_tennis_analysis.ipynb        # Main analysis notebook (EDA + hypothesis tests)
```

## Analysis Overview

### Data Collection & Preparation
- Downloaded 5 years of ATP match data (2019–2023) from GitHub
- Merged with player biographical data for enrichment
- Computed derived statistics: 1st serve %, 1st serve points won %, 2nd serve points won %, break point save rate, ace rate, double fault rate
- Final dataset: ~10,000–15,000 player-match observations

### Exploratory Data Analysis
- Distribution of matches by surface and year
- Winner vs loser comparison across all key statistics (boxplots)
- Correlation matrix of winner match statistics
- Statistics breakdown by court surface
- Handedness distribution analysis

### Hypothesis Testing
- **Independent t-tests** and **Mann-Whitney U tests** comparing winners and losers on 6 key statistics
- **Cohen's d** effect sizes for each comparison
- **Kruskal-Wallis test** for ace rate differences across court surfaces
- **T-test** comparing right-handed vs left-handed winners on 1st serve %
- Significance level: α = 0.05

## How to Reproduce

1. Clone this repository:
   ```bash
   git clone https://github.com/melisatasli/Melisa_Tasli_DSA210.git
   cd Melisa_Tasli_DSA210
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Open and run the analysis notebook:
   ```bash
   jupyter notebook dsa210_tennis_analysis.ipynb
   ```
   Run all cells in order. The notebook automatically downloads the data from GitHub.

## Timeline

| Date | Milestone | Status |
|------|-----------|--------|
| March 17 | Create GitHub repo | Done |
| March 31 | Submit proposal | Done |
| April 14 | Data collection, EDA, hypothesis tests | Done |
| May 5 | Apply ML methods | Upcoming |
| May 18 | Final report and code | Upcoming |

## Tools & Libraries

- Python 3.10+
- pandas, NumPy — data manipulation
- matplotlib, seaborn — visualization
- scipy — statistical tests

## Acknowledgments

- Match data: [Jeff Sackmann / Tennis Abstract](https://github.com/JeffSackmann/tennis_atp)
- Course: DSA 210 Introduction to Data Science, Sabanci University, Spring 2025–2026
