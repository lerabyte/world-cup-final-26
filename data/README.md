# Dataset setup

The model expects the following five CSV files:

- `matches.csv` — detailed 2026 World Cup match statistics
- `results.csv` — historical international match results
- `goalscorers.csv` — individual international goals
- `shootouts.csv` — historical penalty-shootout results
- `former_names.csv` — historical country-name mappings

Download the original datasets and upload the five CSV files into the same Google Colab session as the notebook. The loader accepts renamed downloads such as `matches(3).csv`, `results(2).csv`, or `goalscorers(1).csv`.

The CSV files are not stored in this repository so that the original dataset sources and licensing remain intact.

