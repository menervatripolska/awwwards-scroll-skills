---
name: quant-ml-research
description: Plan quantitative and machine-learning trading research using feature engineering, labels, train/test splits, walk-forward validation, leakage prevention, Qlib-style pipelines, FinRL-style experiments, regime modeling, and portfolio-level evaluation.
---

# Quant ML Research

## Purpose

Use this skill for ML/quant trading ideas. The goal is reproducible research, not mystical prediction.

## Research Workflow

1. Define prediction target:
   - Return, direction, volatility, regime, rank, risk, allocation.
2. Define features:
   - Technical, volume, volatility, market structure, fundamentals, sentiment if sourced.
3. Prevent leakage:
   - No future features, no post-event labels in inputs, correct timestamp alignment.
4. Split:
   - Train, validation, test, walk-forward.
5. Evaluate:
   - Out-of-sample performance, turnover, costs, drawdown, stability.

## Output

Use:

`hypothesis | target | features | split | model | costs | metrics | leakage checks | verdict`

## Rules

- Do not treat high in-sample accuracy as edge.
- Include transaction costs and turnover.
- Route execution readiness to `$live-trading-safety-guard`.
