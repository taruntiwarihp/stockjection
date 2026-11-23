# Forecast proof

Each evening after the NSE close, Stockjection freezes the day's ranking: for every stock and horizon (1, 5 and 20 sessions
ahead), its rank among about 4,000 NSE stocks. Before the next market open, the file's **SHA-256 fingerprint** is added to
[commitments.csv](commitments.csv) and committed to this repository, so the time of the commitment is public in the git history.

After all horizons have played out (about a month later), the exact file is published in [revealed/](revealed/) as
`<date>.parquet`. Anyone can check it:

```bash
sha256sum revealed/2026-11-25.parquet                    # Linux / macOS / Git Bash
certutil -hashfile revealed6-11-25.parquet SHA256    # Windows
```

The result must equal the `sha256` in commitments.csv for that date. If even one rank in the file had been changed after the
fact, the fingerprint would not match.

Columns: `date` (the evening the ranking was made), `symbol`, `h` (horizon in sessions), `rank_pct` (0 to 1; 1 = expected to do
best relative to the market). Ranks order stocks against each other; they are not buy / sell advice.
