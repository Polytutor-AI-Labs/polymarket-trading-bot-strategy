# Dual-Price Reversion

**Status:** Research
**Area:** Reversion / paired pricing
**Research source:** [Low-Side Dual Reversion](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/low-side-dual-reversion.md)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Research into unusual relative pricing between complementary binary outcomes, and whether temporary dislocations may revert or create structured two-sided opportunities.

The canonical handbook name is **Low-Side Dual Reversion**. This page does not invent separate products such as Dual 45¢ or Dual 49¢.

PolyTutor can work with clients on systems involving this research area, subject to feasibility, scope, and strategy review.

## Market Idea

When both complementary sides look unusually cheap, a research question is whether both can be acquired below complete-set value. When only one side is cheap, a related question is whether that side later reverts. One filled leg without the other is a directional position.

## System Flow

```text
YES / NO Market
      ↓
Relative Price Observation
      ↓
Dislocation Detection
      ↓
Validation
      ↓
Primary Entry
      ↓
Repricing / Reversion
      ↓
Optional Secondary Action
      ↓
Exit / Settlement
```

## Engineering Focus

- Paired price state across complementary outcomes
- Market and book synchronization
- Spread, liquidity, and timing
- Combined cost after fills
- Position state when one leg is missing
- Execution of a later complementary or exit action

## Key Risks

- Combined cost is not attractive after fees and slippage
- Only one side fills
- Reversion never arrives
- Thin books move through the intended size
- Treating a cheap pair as completed arbitrage before both legs exist

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including exact trigger prices, pair-cost targets, and lookbacks.

## Further Research

[Handbook: Low-Side Dual Reversion](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/low-side-dual-reversion.md)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
