---
name: multi-timeframe-analysis
description: Build higher-timeframe and lower-timeframe trading analysis, including bias, regime, levels, entries, confluence, HTF/LTF alignment, intraday context, swing context, and timeframe-specific invalidation for setup discovery.
---

# Multi Timeframe Analysis

## Purpose

Use this skill to connect strategic context with tactical entries. HTF defines the field; LTF defines execution.

## Workflow

1. Choose timeframe stack:
   - Swing: 1W/1D/4H.
   - Intraday: 1D/4H/1H/15m/5m.
   - Scalping: 1H/15m/5m/1m.
2. Define HTF regime and levels.
3. Define mid-timeframe setup zone.
4. Define LTF trigger.
5. Define invalidation and risk.

## Output

Use:

`HTF bias | HTF levels | MTF setup zone | LTF trigger | invalidation | risk note | no-trade condition`

## Rules

- If HTF and LTF conflict, state the conflict.
- Do not overfit by adding too many timeframe filters.
- Route position sizing to `$risk-position-sizing`.
