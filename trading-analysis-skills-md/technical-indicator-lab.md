---
name: technical-indicator-lab
description: Define, combine, and validate technical indicators for trading systems and setup scanners. Use when Codex needs RSI, MACD, moving averages, EMA/SMA, ATR, Bollinger Bands, VWAP, Stochastic, ADX, Supertrend, Ichimoku, custom indicators, TA-Lib, pandas-ta, vectorbt, or indicator feature engineering.
---

# Technical Indicator Lab

## Purpose

Use this skill to turn indicator ideas into explicit, testable conditions. Indicators are features, not predictions.

## Workflow

1. Define the question:
   - Trend, momentum, mean reversion, volatility, volume confirmation, regime filter, exit logic.
2. Define exact formula and parameters.
3. Define timeframe and candle close behavior.
4. Define signal conditions:
   - Cross, threshold, slope, divergence, compression, expansion, ranking.
5. Define anti-lookahead rules.
6. Route to backtest or scanner.

## Indicator Output

Use:

`indicator | parameters | timeframe | condition | purpose | failure mode | validation`

## Rules

- Do not stack indicators that measure the same thing without a reason.
- Avoid repainting and incomplete-candle signals unless explicitly desired.
- Always specify whether signals use candle close or intrabar updates.
- Route risk to `$risk-position-sizing` and validation to `$backtest-validation`.
