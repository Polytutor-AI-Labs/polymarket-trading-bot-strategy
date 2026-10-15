# Market Making

**Status:** Research
**Area:** CLOB liquidity / inventory
**Research source:** [PMM — Paired Market Maker](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/clob-book/pmm-paired-market-maker.md); [Inventory-Skewed Adaptive Market Making](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/clob-book/inventory-skewed-adaptive-market-making.md) (external public research)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Market-making research focuses on maintaining bids and asks around a target fair-value region while managing inventory, spread, adverse selection, and execution risk.

Historical PolyTutor research includes paired maker ladders on complementary binary outcomes. Inventory-skewed adaptive quoting is documented in the handbook as external public research and is not presented here as a PolyTutor invention.

This research area may inform custom trading-system development after feasibility review.

## Market Idea

A maker can post on one or both sides of a binary book and earn spread if filled on intended terms. In prediction markets, complementary YES/NO quotes also interact with complete-set economics. The research question is whether quote placement and inventory control can be studied without treating every fill as edge.

## System Flow

```text
Order Book
    ↓
Market State
    ↓
Fair-Value / Quote Logic
    ↓
Inventory State
    ↓
Risk Adjustment
    ↓
Bid / Ask Generation
    ↓
Order Management
    ↓
Fill / Inventory Update
```

## Engineering Focus

- Order-book state and quote lifecycle
- Bid/ask generation, spread, and replacement
- Inventory and risk adjustment
- Cancellation and stale-order handling
- Partial fills
- Adverse-selection awareness after being filled

## Key Risks

- Adverse selection and toxic flow
- Inventory accumulation on the wrong side of news
- Sudden information events
- Stale quotes
- Thin liquidity
- Cancellation or replace latency
- One-sided fills that leave directional exposure

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including quote formulas, inventory skew functions, and production order parameters.

## Further Research

- [Handbook: PMM — Paired Market Maker](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/clob-book/pmm-paired-market-maker.md) (Historical PolyTutor research)
- [Handbook: Inventory-Skewed Adaptive Market Making](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/clob-book/inventory-skewed-adaptive-market-making.md) (External public research)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
