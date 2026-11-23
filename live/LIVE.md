# Live track record

Updated as results come in, good or bad.

## Paper trading (simulated money, real prices, real costs)

Book C2: each session, buy the 5 highest-ranked and short the 5 lowest-ranked stocks (Rs 10,000 each) at the open, close all at
the close. Charges: brokerage, STT, stamp duty, exchange fees, GST, SEBI fee and 10 bps slippage per side.

| Week | Sessions | Net | Note |
|---|---|---|---|
| 17 - 23 Nov 2026 | 5 | −Rs 3,327 (−3.3 % of Rs 1 lakh) | Poor start: only 2.3 % of 5-session stretches in the backtest were this bad. Losses came mostly from two short squeezes (+8.9 %, +6.2 %). Tests of a liquidity floor and a stop-loss on 2024-25 data did not improve the book, so the rules stay unchanged. |

Backtest expectation for this book (Jan 2024 - Sep 2025): +0.346 % a day after costs, with a daily swing of about ±1.1 %.
A fair live verdict needs about 20 to 30 sessions (around 23 December 2026).

## Shadow test (next version vs live model)

The next version runs every night next to the live model without changing anything that is published. It is scored once
each forecast's outcome is known. A switch needs at least 10 scored days.

| Day | Live model IC | Note |
|---|---|---|
| 20 Nov 2026 | 0.065 | The live model did better than the shadow variants on this day. One day is noise. |
