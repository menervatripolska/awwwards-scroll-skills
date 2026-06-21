---
name: volume-volatility-analysis
description: Analyze volume, liquidity, ATR, realized volatility, volatility regimes, squeeze/expansion, volume profile, VWAP, abnormal volume, spread, slippage, funding, and open interest for trading setup filters and risk controls.
---

# Volume Volatility Analysis

## Purpose

Use this skill to decide whether a setup has enough liquidity, volatility, and regime alignment to trade or scan.

## Review Areas

- Volume trend and abnormal volume.
- ATR and volatility regime.
- Spread and slippage risk.
- Squeeze/compression and expansion.
- VWAP and volume-weighted context.
- Open interest and funding for crypto futures.
- Liquidity by session and exchange.

## Output

Use:

`symbol | timeframe | volume condition | volatility regime | liquidity risk | setup implication | filter decision`

## Rules

- Do not compare raw volume across unrelated markets without normalization.
- Include spread/slippage for execution-aware plans.
- Route sizing to `$risk-position-sizing`.
