---
name: market-data-ingestion
description: Design market data and exchange connectivity pipelines for trading analysis and bots. Use when Codex needs to fetch or normalize OHLCV, tickers, order books, trades, funding, open interest, balances, positions, orders, fills, and exchange metadata using CSV, broker APIs, CCXT, exchange REST/WebSocket APIs, or backtesting data stores.
---

# Market Data Ingestion

## Purpose

Use this skill to design reliable data inputs for scanners, backtests, dashboards, and execution-aware bots. It supports public data and private authenticated endpoints when the user explicitly authorizes exchange connection.

## Data Types

- Public: OHLCV, ticker, order book, recent trades, funding rates, open interest, exchange symbols, fees.
- Private: balances, positions, open orders, order history, fills, margin mode, leverage, account risk.
- Local: CSV, Parquet, database, TradingView export, broker export, trade journal.

## Exchange Connection

For private API:

- Use environment variables or a secret manager for keys.
- Ask whether permissions include read, trade, withdraw, transfer, or margin/futures.
- Strongly prefer no withdrawal permission for trading bots.
- Use testnet/paper mode first when available.
- Log key fingerprints/permissions, never key values.

## Quality Checks

- Timezone and exchange timestamp alignment.
- Missing candles and duplicate bars.
- Symbol naming and contract type.
- Spot versus futures data.
- Funding/open interest availability.
- Survivorship bias for equities.
- Fees, slippage, and spread assumptions.

## Output

Use:

`source | mode | symbols | timeframe | fields | auth/permissions | storage | quality checks | risks`

Route scanners to `$setup-finder-watchlist` or `$crypto-ccxt-scanner`; route execution safety to `$live-trading-safety-guard`.
