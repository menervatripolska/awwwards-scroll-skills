---
name: breakout-breakdown-setups
description: Define and evaluate breakout, breakdown, retest, range expansion, failed breakout, reclaim, squeeze release, and fakeout setups for trading research, scanners, and backtests.
---

# Breakout Breakdown Setups

## Purpose

Use this skill to formalize breakout/breakdown playbooks with clear triggers and invalidation.

## Setup Components

- Structure: range, triangle, consolidation, base, prior high/low.
- Trigger: close above/below level, volume expansion, volatility expansion, retest hold/fail.
- Confirmation: ATR, volume, order book, higher timeframe trend.
- Invalidation: close back inside range, level reclaim/loss, volatility failure.
- Targets: measured move, next liquidity, ATR multiple, trailing stop.

## Output

Use:

`setup | level | trigger | confirmation | entry style | stop/invalidation | target | failure mode`

## Rules

- Distinguish true breakout from fakeout/reclaim setups.
- Use liquidity and spread filters.
- Route sizing to `$risk-position-sizing` and validation to `$backtest-validation`.
