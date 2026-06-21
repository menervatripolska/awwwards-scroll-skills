---
name: trading-analysis-orchestrator
description: Coordinate trading research, technical analysis, setup discovery, exchange connectivity, backtesting, journaling, risk management, and live-trading safety. Use when Codex needs to plan or route trading workflows for crypto, forex, equities, futures, or CFDs using chart analysis, scanners, indicators, CCXT/exchange APIs, Freqtrade, vectorbt, backtesting.py, Qlib, or QuantConnect-style engines.
---

# Trading Analysis Orchestrator

## Purpose

Use this skill as the router for trading and technical-analysis work. It supports research, setup discovery, exchange data, private exchange APIs, paper trading, testnet, and controlled live execution. It does not provide guaranteed signals or financial advice.

## Scope

Clarify:

- Market: crypto, forex, equities, futures, options, CFDs.
- Venue: exchange/broker, symbol universe, spot/margin/futures.
- Mode: research, scanner, paper, testnet, live.
- Timeframes and session.
- Data source and exchange connectivity.
- Risk rules: max loss, leverage, position size, stop logic, kill switch.
- Output needed: setup definition, watchlist, scanner, backtest, bot strategy, trade plan, journal review.

## Route Work

- Use `$market-data-ingestion` for OHLCV, order book, trades, balances, positions, and exchange data quality.
- Use `$technical-indicator-lab` for indicators and feature logic.
- Use `$price-action-market-structure` for trend, structure, levels, liquidity, and invalidation.
- Use `$candlestick-pattern-scanner` for candle pattern definitions and filters.
- Use `$multi-timeframe-analysis` for HTF/LTF alignment.
- Use `$setup-finder-watchlist` for scanning assets and ranking setups.
- Use `$breakout-breakdown-setups`, `$mean-reversion-setups`, or `$trend-following-setups` for playbook-specific setups.
- Use `$volume-volatility-analysis` for volume, ATR, regimes, and volatility filters.
- Use `$risk-position-sizing` before any trade plan or order sizing.
- Use `$backtest-validation` before trusting a strategy.
- Use `$trade-journal-review` after trades.
- Use `$crypto-ccxt-scanner` for crypto exchange scanners and optional execution wiring.
- Use `$freqtrade-strategy-builder` for Freqtrade strategies.
- Use `$quant-ml-research` for ML/quant experiments.
- Use `$live-trading-safety-guard` before any private API order placement.

## Output

Use:

`objective | market | exchange mode | data | setup logic | risk gate | validation | output | next action`

## Rules

- Never claim certainty or guaranteed profit.
- Do not place or recommend live trades without explicit user instruction and risk constraints.
- Never expose API keys or secrets.
- Separate analysis, signal generation, order sizing, and execution.
- For live mode, require `$live-trading-safety-guard`.
