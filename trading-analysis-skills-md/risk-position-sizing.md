---
name: risk-position-sizing
description: Calculate trading risk, stop distance, position size, leverage exposure, max loss, R multiple, invalidation, partial exits, portfolio heat, drawdown limits, and exchange order sizing. Use before any trade plan, backtest, bot strategy, or live/paper order placement.
---

# Risk Position Sizing

## Purpose

Use this skill before any trade can become an order. It converts analysis into bounded risk.

## Inputs

- Account equity or test balance.
- Risk per trade.
- Entry, stop, invalidation.
- Contract type: spot, margin, futures, inverse, linear, equities.
- Leverage and margin mode.
- Fees, spread, slippage.
- Max daily loss and max open risk.

## Calculations

Use:

`risk_amount = account_equity * risk_percent`

`position_size = risk_amount / stop_distance`

Adjust for contract multiplier, tick size, lot size, min notional, leverage, and fees.

## Output

Use:

`entry | stop | risk % | risk amount | size | leverage | max loss | R target | invalidation | order notes`

## Rules

- Never size a position without a stop/invalidation.
- Reduce size for wide spreads, high volatility, or correlated exposure.
- Route live execution to `$live-trading-safety-guard`.
