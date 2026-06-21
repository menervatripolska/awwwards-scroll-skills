---
name: live-trading-safety-guard
description: Guard live trading and exchange execution workflows, including private API keys, order placement, leverage, margin mode, position sizing, max loss, kill switches, paper/testnet promotion, order validation, bot permissions, and incident rollback. Use before any real order, live bot, or exchange API execution.
---

# Live Trading Safety Guard

## Purpose

Use this skill as the mandatory final gate before real exchange execution. It supports live trading workflows but blocks unsafe automation.

## Required Checks

- Explicit user instruction for live mode.
- Exchange, account, market type, symbol, and order side.
- API key permissions reviewed; no withdrawal permission for bots.
- Testnet/dry-run result reviewed or explicitly waived.
- Entry, stop, invalidation, and max loss defined.
- Position size from `$risk-position-sizing`.
- Leverage and margin mode confirmed.
- Max daily loss, max open risk, and max concurrent positions.
- Kill switch and cancel-all process.
- Logging without secrets.

## Order Gate Output

Use:

`mode | order intent | account risk | size | leverage | stop | max loss | permissions | kill switch | verdict`

Verdicts:

- `block`
- `paper only`
- `testnet only`
- `manual approval required`
- `live-ready with constraints`

## Rules

- Do not place, suggest, or automate real orders without explicit user approval.
- Block all-in, hidden leverage, undefined stop, withdrawal-enabled bot keys, and revenge-trade escalation.
- Treat model-generated signals as candidates until validated and risk-sized.
