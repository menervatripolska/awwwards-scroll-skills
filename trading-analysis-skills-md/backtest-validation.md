---
name: backtest-validation
description: Validate trading strategies and setup rules with backtests, walk-forward tests, out-of-sample checks, overfitting controls, fees, slippage, spread, survivorship bias, data leakage checks, vectorbt, backtesting.py, Backtrader, Freqtrade, Qlib, or QuantConnect Lean-style workflows.
---

# Backtest Validation

## Purpose

Use this skill to test whether a setup has evidence. Backtests do not prove future profits; they help reject weak or overfit ideas.

## Validation Checklist

- Data quality and timeframe.
- No lookahead or repainting.
- Fees, slippage, spread.
- Entry and exit rules fully specified.
- Position sizing and risk rules.
- Out-of-sample period.
- Walk-forward or parameter stability.
- Trade count and regime coverage.
- Drawdown, expectancy, win rate, profit factor, Sharpe/Sortino if useful.

## Output

Use:

`strategy | dataset | assumptions | metrics | weaknesses | overfit checks | next experiment | verdict`

Verdicts:

- `reject`
- `needs more data`
- `paper test`
- `candidate`

## Rules

- Do not trust high returns with tiny trade counts.
- Do not optimize parameters blindly.
- Route live readiness to `$live-trading-safety-guard`.
