---
name: mean-reversion-setups
description: Define mean-reversion trading setups using deviation from moving averages, VWAP, Bollinger Bands, z-score, RSI extremes, volatility bands, range edges, liquidity sweeps, and reversion triggers for research, scanners, and backtests.
---

# Mean Reversion Setups

## Purpose

Use this skill to define setups where price is expected to revert after overextension. It must include regime filters because mean reversion fails hard in trends.

## Components

- Mean: VWAP, EMA, SMA, rolling midpoint, fair value, range mid.
- Deviation: ATR, Bollinger Bands, z-score, RSI, percentage move.
- Context: range regime, exhaustion, liquidity sweep, no strong trend.
- Trigger: reclaim, close back inside band, divergence, failed continuation.
- Invalidation: new impulse continuation, level loss, volatility expansion.

## Output

Use:

`mean | deviation | regime filter | trigger | entry zone | stop | target mean | skip condition`

## Rules

- Avoid counter-trend entries without strict invalidation.
- Include liquidity/spread filters.
- Route validation to `$backtest-validation`.
