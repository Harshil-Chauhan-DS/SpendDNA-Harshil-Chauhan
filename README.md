# SpendDNA Harshil Chauhan

A Python tool that reads a messy bank/UPI transaction export and turns it into a full spending analytics report — top vendors, category breakdowns, monthly trends, time-of-day habits, anomalies, and a spending personality archetype.

## Screenshot

I do not wish to reveal my spending habbits so i'll refrain from this part...

# What it does

Reads a raw transaction CSV and produces:

- Clean parsed data — 4 date formats, 3 amount formats, standardised debit/credit, duplicates dropped
- Canonical vendor extraction from messy UPI/POS descriptions (~40 vendors)
- Category tagging across 12 spending categories
- Executive summary — total credits, debits, net change, savings rate
- Top 5 categories and top 5 vendors by spend
- Monthly spending trend per category
- Time-of-day spending patterns (with an hourly activity grid)
- Anomaly detection using z-scores (transactions 2+ standard deviations above the category average)
- Spending personality archetype detection (Foodie, Shopaholic, Investor, YOLO Spender, and more)
- A vendor cleanup audit to catch anything that slipped through uncategorised

# Works on any statement

The notebook asks for the file name and account holder's name when it runs, and works out the transaction period directly from the dates in the file. Point it at any bank/UPI CSV export with `Date, Time, Description, Type, Amount, Balance, Mode, Ref` columns and it will parse and analyse it the same way — no hardcoded names or dates.

# Constraints

**Built using only Python fundamentals, pandas, and NumPy. No shortcuts.**

- No pandas-profiling, matplotlib, seaborn, or plotly
- No scikit-learn, scipy.stats, or statsmodels — z-score written by hand
- No collections.Counter — used plain dictionaries and pandas groupby instead
- No regex — all matching done with in and .str.contains

**Only pandas, NumPy, and datetime**

# How to run it

1. Clone this repo or download the `.ipynb` file
2. Upload your file to the same folder (or to `/content/` if using Google Colab)
3. Open the notebook in Jupyter or Google Colab
4. Run all cells from top to bottom
5. Enter the file name and account holder name when prompted (or just press Enter to use the defaults)
6. Screenshot the output

To run on your own statement:
- Export 3-6 months of your own UPI/bank statement as a CSV
- Save it next to the notebook
- When prompted, type in the file name and your name instead of the default

# Dataset

`DADSJUNE.csv` is a synthetic transaction export provided by The Unlox Academy for this project.

# Built by

Harshil Chauhan — Computer Science & Engineering Student, Graphic Era Deemed to be University | Unlox Academy
