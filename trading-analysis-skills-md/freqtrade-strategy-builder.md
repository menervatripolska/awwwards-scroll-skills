---
name: freqtrade-strategy-builder
description: Build, review, and validate Freqtrade crypto trading strategies, including populate_indicators, entry/exit signals, protections, hyperopt boundaries, backtesting, dry-run, exchange config, risk settings, and live-trading safeguards.
---

# Freqtrade Strategy Builder

## Purpose

Use this skill to turn setup rules into Freqtrade strategy logic and validation plans.

## Strategy Design

Specify:

- Timeframe and informative pairs.
- Indicators and parameters.
- Entry conditions.
- Exit conditions.
- Stoploss and trailing logic.
- Protections and cooldowns.
- Pairlist and volume filters.
- Stake sizing and max open trades.
- Dry-run/testnet/live mode.

## Output

Use:

`component | rule | Freqtrade location | parameter | risk note | test`

## Validation

- Backtest with fees/slippage assumptions.
- Check trade count and drawdown.
- Run dry-run before live.
- Review protections.
- Route exchange API safety to `$live-trading-safety-guard`.

## Rules

- Do not optimize blindly with hyperopt.
- Do not move from backtest directly to live.
- Never expose exchange API keys in config or output.
