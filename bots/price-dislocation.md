# Price Dislocation

**Status:** Research
**Area:** Extreme-price opportunities
**Research source:** [1¢ Buy — Ultra-Cheap Dislocation](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/one-cent-buy.md)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Research into extreme implied-probability pricing and the conditions under which a very low-priced binary outcome may warrant further analysis.

This is not “buy everything at one cent.” A cheap print is a quote, not expected value. Many low-priced outcomes are cheap because they are likely to settle at zero.

This research area may inform custom trading-system development after feasibility review.

## Market Idea

Binary contracts bought at a low price have large upside if they settle at one and limited dollar loss per share if they expire worthless — before costs. The research question is whether any such quotes are dislocations relative to settlement value, or simply correctly priced tails.

The broader handbook family also includes near-resolution expensive prices; that work is covered on [Last-Seconds Research](./last-seconds.md).

## System Flow

```text
Market Universe
      ↓
Extreme Price Detection
      ↓
Market / Resolution Validation
      ↓
Liquidity Check
      ↓
Risk Evaluation
      ↓
Potential Entry
      ↓
Position / Settlement Monitoring
```

## Engineering Focus

- Scanning and classifying extreme outcome prices
- Settlement-rule and market-identity checks
- Liquidity and spread before any order is considered
- Position sizing as a risk problem, not a signal
- Monitoring until settlement or an explicit exit

## Key Risks

- Low price does not mean undervaluation
- Many low-priced outcomes correctly approach zero
- Liquidity may be poor
- Spread and fees may dominate any theoretical edge
- Settlement rules matter
- Rare-event probabilities are difficult to estimate

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including exact entry prices, filters, and sizing rules.

## Further Research

- [Handbook: 1¢ Buy — Ultra-Cheap Dislocation](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/one-cent-buy.md)
- [Price Dislocation family](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#strategy-families)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
