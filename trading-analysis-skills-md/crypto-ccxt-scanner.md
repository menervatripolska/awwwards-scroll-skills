---
name: crypto-ccxt-scanner
description: Design crypto market scanners and exchange connectors using CCXT or native exchange APIs. Use when Codex needs to fetch OHLCV, tickers, order books, funding, balances, positions, open orders, or create paper/testnet/live execution wiring for crypto setup scanners and bots.
---

# Crypto CCXT Scanner

## Purpose

Use this skill for crypto-specific scanning and exchange connectivity. It supports public data, private account data, and order-routing designs when explicitly requested.

## Connection Modes

- Public scanner: no keys, market data only.
- Private monitor: balances, positions, orders, fills.
- Paper/testnet: simulated or exchange test environment.
- Live execution: real orders, allowed only after `$live-trading-safety-guard`.

## Scanner Design

Use:

`exchange | market type | symbols | timeframe | data endpoints | filters | ranking | alert/execution mode`

Include:

- Rate limits.
- Symbol normalization.
- Spot/futures distinction.
- Funding/open interest if futures.
- Fees and precision.
- Min notional and lot size.

## Execution Design

Before orders:

- Confirm API permissions.
- Disable withdrawals.
- Validate order type, size, leverage, margin mode.
- Add idempotency/client order ids when supported.
- Add kill switch and max loss limits.

## Rules

- Never print API keys.
- Never place live orders without explicit user instruction and safety guard.
- Route setup definitions to the relevant setup skill.
