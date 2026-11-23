# How Stockjection is tested

## What is predicted

For each NSE stock and each evening *t*, a score for how the stock will do over the next *h* sessions (h = 1, 5, 20)
**relative to the market** (return from the next open, minus beta times the market's return). Scores rank stocks against each
other; they are not price targets and not advice.

## The rules every experiment follows

1. **The pass / fail rule is written before the run** (in the experiment's script and the research log), including the
   measure, the comparison, the statistic and the years it must hold in. Results never change the rule afterwards.
2. **Point in time.** Every input is used only from the moment it was public (filing times, result dates, data publication
   times). Known open issue: some historical corporate-action confirmations depend on later prices; this is being audited.
3. **Walk-forward training.** Each year is scored by models trained only on earlier data. The leaderboard covers January 2024 to
   September 2025.
4. **A sealed year.** October 2025 to October 2026 is kept out of the leaderboard and of model selection from now on.
5. **Same rows for every competitor.** A comparison only counts on identical stocks and dates.
6. **Dependence-aware statistics.** Daily results are not independent, so t-values use Newey-West errors, and a rule also
   requires the result to hold in each year separately (2024 and 2025).
7. **Costs in every money result.** Brokerage, STT, stamp duty, exchange charges, GST, the SEBI fee and slippage. Intraday
   round trip about 30.6 bps; delivery about 44 bps.
8. **Failures are kept.** [research/RESULTS.md](../research/RESULTS.md) lists every experiment and its verdict.

## Measures

| Measure | Meaning |
|---|---|
| IC (rank information coefficient) | Spearman correlation between the score and the next market-relative return across stocks on a day, averaged over days. 0 = no skill. Around 0.05 is useful in daily stock data; above 0.10 is strong. |
| Calls right | Of the top 2 % (expected to beat the market) and bottom 2 % (expected to lag) each day, the share that did. |
| Book | 5 longs + 5 shorts per day, next open to close, after costs; mean % per day and its t-value. |
| Capacity | How much money a book can take before its own orders move prices enough to eat the edge (square-root market impact). |

## Going live

A model change goes live only after (1) its research rule passes, (2) it runs as a **shadow** next to the live model for at
least 10 scored days without changing anything published, and (3) the owner decides. Forecasts are frozen before the open
and fingerprinted (see [forecasts/README.md](../forecasts/README.md)).
