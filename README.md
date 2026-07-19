# 2026 World Cup Final Predictor

This project uses machine learning to predict the eventual winner of the 2026 World Cup final between Spain and Argentina.
Check out my explanation ([on TikTok](https://www.tiktok.com/@lerabyte/video/7664003310478707999))

The model combines multinomial logistic regression with histogram gradient boosting. It uses only information that would have been available before each match, including Elo ratings, recent form, opponent strength, recovery time, scoring diversity, and penalty and late-goal patterns. A separate shootout calculation converts the draw probability into each team's final probability of becoming champion.

## Final prediction

| Team | Probability of becoming champion |
| --- | ---: |
| Spain | 51.6% |
| Argentina | 48.4% |

The model sees the final as essentially a coin flip, with a very slight advantage for Spain.

## Validation

- Chronological validation matches: 3,606
- Accuracy: 61.1%
- Log loss: 0.854
- Training cutoff: July 15, 2026

The model was trained on older matches and validated on newer ones instead of randomly mixing games from different years. The blank final row was never used for training.

## Repository contents

- `World_Cup_Final_Argentina_vs_Spain_Model.ipynb` — complete model and prediction notebook
- `requirements.txt` — required Python packages
- `data/README.md` — required dataset files and setup instructions

## Run the model

1. Open `World_Cup_Final_Argentina_vs_Spain_Model.ipynb` in Google Colab.
2. Download the five original CSV files listed in `data/README.md`.
3. Upload the CSV files into the Colab session.
4. Select **Runtime → Run all**.
5. Scroll to the final cells to see the prediction and probability chart.

The notebook automatically recognizes filenames with suffixes such as `results(2).csv` or `matches(3).csv`.

## Model structure

The historical model predicts three possible outcomes:

- Spain wins before a shootout
- The match remains tied
- Argentina wins before a shootout

If the match remains tied, recency-weighted historical shootout performance is used to estimate which team is more likely to win the trophy.

Detailed 2026 statistics such as possession, shots, shots on target, and corners were also tested. Because they did not improve performance on the knockout-round holdout, the model correctly assigned them zero weight in the final prediction.

## Disclaimer

This is an educational machine-learning project, not a guarantee or betting recommendation. A probability close to 50% means the model considers the match highly uncertain.

