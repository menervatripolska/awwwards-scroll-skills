---
name: trend-following-setups
description: Define trend-following and continuation setups using market structure, moving averages, pullbacks, breakouts, momentum, ADX, Supertrend, volatility contraction, trailing stops, and regime filters for scanners and backtests.
---

# Trend Following Setups

## Purpose

Use this skill to create setups that follow established trend or momentum while controlling late-entry risk.

## Components

- Trend definition: higher highs/lows, MA slope, price above/below MA, ADX, structure.
- Entry type: pullback, breakout, retest, compression release, continuation candle.
- Confirmation: volume, momentum, HTF alignment, volatility expansion.
- Invalidation: trend structure break, MA reclaim/loss, failed retest.
- Exit: trailing stop, structure stop, ATR stop, partials, time stop.

## Output

Use:

`trend filter | setup trigger | confirmation | stop | trailing logic | target/risk | no-trade condition`

## Rules

- Avoid chasing extended moves without pullback or volatility logic.
- Define trend exhaustion filters.
- Route HTF context to `$multi-timeframe-analysis`.
