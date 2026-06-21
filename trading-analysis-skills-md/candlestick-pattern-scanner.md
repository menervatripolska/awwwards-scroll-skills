---
name: candlestick-pattern-scanner
description: Define and scan candlestick patterns for trading setup research, including engulfing, pin bar, hammer, shooting star, doji, inside bar, outside bar, morning/evening star, marubozu, three-bar patterns, TA-Lib candlestick functions, and context filters.
---

# Candlestick Pattern Scanner

## Purpose

Use this skill to make candle-pattern logic precise and context-aware. Candle names alone are not enough; patterns need trend, level, volume, and volatility filters.

## Pattern Definition

Specify:

- Pattern name and candle count.
- Body/wick ratio.
- Direction and close location.
- Required prior trend or range.
- Level context: support/resistance, VWAP, MA, liquidity.
- Volume/volatility confirmation.
- Timeframe and session.

## Output

Use:

`pattern | formula | context filter | entry trigger | invalidation | target logic | false-positive filter`

## Rules

- Avoid trading candle patterns without context.
- Prefer candle-close confirmation unless intrabar behavior is explicit.
- Backtest each pattern with filters, not isolated visual examples.
- Route validation to `$backtest-validation`.
