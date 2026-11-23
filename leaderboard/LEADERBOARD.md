# Stockjection leaderboard

Same NSE stocks (EQ series, 20-session mean traded value of at least Rs 10 crore, no circuit lock), same dates (January 2024 to September 2025), same rules for every model; every model is scored only on dates it never trained on. IC = mean daily rank correlation between the score and the next h sessions' return relative to the market. Calls = top / bottom 2 % that beat / lagged the market. Book (1 day) = 5 longs + 5 shorts, next open to close, after 30.6 bps of costs.

## 1-day horizon

| # | Model | IC (NW t) | IC 2024 / 2025 | IC all stocks | Calls right | Book % / day (t) |
|---|---|---|---|---|---|---|
| 1 | Stockjection, next version (shadow test) | 0.1237 (+26.3) | 0.1358 / 0.1076 | 0.1341 | 60.5% | +0.380 (+7.6) |
| 2 | Stockjection, live | 0.1142 (+26.0) | 0.1279 / 0.0961 | 0.1256 | 59.2% | +0.346 (+6.7) |
| 3 | Microsoft Qlib DoubleEnsemble | 0.1015 (+17.8) | 0.1093 / 0.0910 | 0.1099 | 57.6% | +0.214 (+4.0) |
| 4 | LightGBM, standard inputs | 0.0997 (+18.8) | 0.1110 / 0.0847 | 0.1102 | 56.9% | +0.134 (+2.2) |
| 5 | Low volatility factor | 0.0619 (+9.0) | 0.0648 / 0.0580 | 0.0609 | 53.2% | -0.074 (-1.7) |
| 6 | Reversal, 1 day | 0.0354 (+7.8) | 0.0410 / 0.0279 | 0.0407 | 50.3% | -0.485 (-7.4) |
| 7 | Reversal, 1 week | 0.0244 (+5.2) | 0.0316 / 0.0148 | 0.0326 | 49.7% | -0.309 (-5.3) |
| 8 | Reversal, 1 month | 0.0160 (+3.1) | 0.0222 / 0.0076 | 0.0137 | 49.2% | -0.223 (-4.3) |
| 9 | Near 52-week high | 0.0129 (+2.5) | 0.0064 / 0.0216 | 0.0182 | 54.1% | -0.333 (-6.6) |
| 10 | Random score | 0.0004 (+0.2) | 0.0025 / -0.0024 | 0.0011 | 49.9% | -0.285 (-7.9) |
| 11 | Momentum, 12-1 months | -0.0072 (-1.5) | -0.0141 / 0.0021 | -0.0049 | 51.1% | -0.323 (-6.6) |

## 5-day horizon

| # | Model | IC (NW t) | IC 2024 / 2025 | IC all stocks | Calls right |
|---|---|---|---|---|---|
| 1 | Stockjection, next version (shadow test) | 0.1141 (+11.9) | 0.1289 / 0.0943 | 0.1306 | 60.5% |
| 2 | Stockjection, live | 0.1088 (+11.4) | 0.1255 / 0.0864 | 0.1260 | 59.7% |
| 3 | LightGBM, standard inputs | 0.0956 (+9.3) | 0.1089 / 0.0779 | 0.1100 | 58.0% |
| 4 | Microsoft Qlib DoubleEnsemble | 0.0902 (+8.9) | 0.0986 / 0.0790 | 0.1041 | 57.6% |
| 5 | Low volatility factor | 0.0581 (+5.0) | 0.0557 / 0.0613 | 0.0612 | 53.4% |
| 6 | Reversal, 1 day | 0.0256 (+5.5) | 0.0266 / 0.0243 | 0.0353 | 49.1% |
| 7 | Reversal, 1 week | 0.0255 (+3.8) | 0.0263 / 0.0245 | 0.0368 | 50.0% |
| 8 | Near 52-week high | 0.0211 (+2.2) | 0.0269 / 0.0134 | 0.0264 | 56.1% |
| 9 | Reversal, 1 month | 0.0113 (+1.3) | 0.0043 / 0.0207 | 0.0121 | 49.3% |
| 10 | Momentum, 12-1 months | 0.0023 (+0.2) | -0.0003 / 0.0058 | 0.0060 | 52.4% |
| 11 | Random score | 0.0008 (+0.5) | 0.0007 / 0.0010 | 0.0019 | 50.0% |

## 20-day horizon

| # | Model | IC (NW t) | IC 2024 / 2025 | IC all stocks | Calls right |
|---|---|---|---|---|---|
| 1 | Stockjection, live | 0.1235 (+5.4) | 0.1497 / 0.0886 | 0.1369 | 59.0% |
| 2 | LightGBM, standard inputs | 0.1058 (+4.3) | 0.1259 / 0.0790 | 0.1178 | 58.0% |
| 3 | Microsoft Qlib DoubleEnsemble | 0.1003 (+4.2) | 0.1157 / 0.0798 | 0.1105 | 57.4% |
| 4 | Low volatility factor | 0.0856 (+4.5) | 0.0657 / 0.1121 | 0.0837 | 54.6% |
| 5 | Near 52-week high | 0.0318 (+1.7) | 0.0442 / 0.0153 | 0.0432 | 58.3% |
| 6 | Reversal, 1 month | 0.0150 (+1.0) | -0.0086 / 0.0465 | 0.0084 | 48.7% |
| 7 | Reversal, 1 week | 0.0066 (+0.8) | 0.0002 / 0.0151 | 0.0096 | 48.2% |
| 8 | Reversal, 1 day | 0.0059 (+1.4) | 0.0061 / 0.0056 | 0.0097 | 49.4% |
| 9 | Random score | 0.0025 (+1.9) | 0.0014 / 0.0040 | 0.0027 | 49.9% |
| 10 | Momentum, 12-1 months | -0.0007 (-0.0) | -0.0048 / 0.0048 | 0.0132 | 51.1% |

Nine pretrained time-series forecasting models (Chronos-2, TimesFM-3, Moirai-2, TiRex, Sundial, Toto, Kronos, Time-MoE and others), tested zero-shot and fine-tuned on Indian daily price bars, showed no skill: none beat a no-change forecast, and direction accuracy was about 50 %.

The next version was chosen on these same dates, so its lead is optimistic. Private and commercial models publish no comparable record.
