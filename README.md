# 5313-Project-1

First group project for 5313.  
Work by Group 2.

Blend learning for fraud detection. Each transaction is scored by an MLP, a Q-learning agent moves the alert threshold as the holdout stream changes, and a rule table can override that score when the amount or the recent transaction count crosses a limit.

Dataset: https://www.kaggle.com/datasets/waqasishtiaq/credit-card-fraud-dataset

Note that you will have to download the dataset and put the creditcard.csv in the root folder of this project to collaborate as the dataset is too large to upload to GitHub.

`V1`–`V28` are PCA features, so the rules use `Time`, `Amount`, and the model score.

## Functionality

- [ ] Load `creditcard.csv` and print shape, fraud count, and fraud rate
- [ ] Scale `Time` and `Amount`, and keep a time-ordered holdout
- [ ] Train `FraudMLP` and print loss, precision, recall, and F1 each epoch
- [ ] Run `ThresholdAgent` on the holdout and record the threshold
- [ ] Apply `amount_limit`, `velocity_limit`, and `score_above_threshold`
- [ ] `blend_decision` returns score, threshold, rule, and decision
- [ ] Print an audit sample of holdout rows

## Testing

- [ ] Small amount, low score prints `allow` / `none`
- [ ] Score above the threshold prints `alert` / `score_above_threshold`
- [ ] Amount at `AMOUNT_LIMIT` prints `review` / `amount_limit`
- [ ] Recent count at `VELOCITY_LIMIT` prints `review` / `velocity_limit`
- [ ] Holdout precision, recall, F1, and a 2×2 confusion matrix
- [ ] Plot the threshold over the stream
- [ ] Screenshot the printed tables for the submission zip