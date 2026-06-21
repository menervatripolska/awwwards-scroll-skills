---
name: setup-finder-watchlist
description: Find and rank trading setups across a watchlist using technical conditions, price action, indicators, volume, volatility, multi-timeframe filters, exchange data, and risk filters. Use when Codex needs to design a scanner or review assets for structured setup candidates.
---

# Setup Finder Watchlist

## Purpose

Use this skill to scan many instruments and rank setup candidates. A scanner should produce candidates, not automatic trades.

## Scanner Inputs

- Market and exchange.
- Symbol universe.
- Timeframes.
- Setup playbook.
- Required indicators or structure filters.
- Risk filters: spread, liquidity, ATR, volatility, leverage limits.
- Mode: research, alert, paper, testnet, live candidate.

## Output

Use:

`symbol | timeframe | setup type | conditions met | entry zone | invalidation | liquidity | risk note | status`

Statuses:

- `watch`
- `armed`
- `triggered`
- `invalidated`
- `skip`

## Rules

- Do not convert scanner hits into orders without `$risk-position-sizing` and `$live-trading-safety-guard`.
- Mark incomplete data as `needs data`.
- Route crypto exchange scanners to `$crypto-ccxt-scanner`.
