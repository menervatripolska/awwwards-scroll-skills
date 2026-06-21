---
name: price-action-market-structure
description: Analyze price action, market structure, trend, ranges, support/resistance, liquidity, break of structure, change of character, swing highs/lows, supply/demand zones, order blocks, invalidation, and discretionary chart context for trading setup research.
---

# Price Action Market Structure

## Purpose

Use this skill to describe chart context in structured language before defining entries. It helps avoid indicator-only signals without market context.

## Analysis Steps

- Identify regime: uptrend, downtrend, range, compression, expansion, transition.
- Mark swing highs/lows and key levels.
- Identify support, resistance, supply/demand, liquidity pools, equal highs/lows.
- Define structure events: BOS, CHOCH, failed break, reclaim, retest.
- Define invalidation.
- Separate observed structure from trade idea.

## Output

Use:

`timeframe | regime | key levels | structure event | liquidity | bias | invalidation | setup candidate`

## Rules

- Do not force a bias when structure is unclear.
- Use higher timeframe context before lower timeframe entries.
- Require risk and invalidation before any trade plan.
- Route HTF/LTF alignment to `$multi-timeframe-analysis`.
