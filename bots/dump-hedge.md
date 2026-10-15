# Dump & Hedge

**Status:** Research
**Area:** Hedging / price dislocation
**Research source:** [Dump & Hedge](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/hedging-arbitrage/dump-hedge.md)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

An initial position is established and the system later evaluates whether market repricing permits an opposing position that creates a favorable combined-cost or risk structure. Completing a cheaper-than-complete-set pair is a research hypothesis, not automatic arbitrage.

PolyTutor did not originate the underlying Dump & Hedge concept. It is studied here as attributed public research.

Concept attribution: [@the_smart_ape](https://x.com/the_smart_ape) / [SmartApe-Go](https://github.com/no-serve-people/SmartApe-Go)

This research area may inform custom trading-system development after feasibility review.

## Market Idea

A rapid dump on one binary outcome may later allow an opposing leg at a combined cost below the value of a complete YES/NO pair. Until the second leg fills, the first leg is directional exposure.

## System Flow

```text
Market Observation
       ↓
Initial Opportunity
       ↓
Primary Position
       ↓
Price Repricing
       ↓
Hedge Evaluation
       ↓
Risk / Cost Validation
       ↓
Potential Opposing Position
       ↓
Settlement / Position Management
```

## Engineering Focus

- Paired outcome tracking
- Combined cost-basis after realized fills
- Hedge-opportunity detection
- Liquidity and order timing on the second leg
- Combined exposure while the hedge is incomplete
- Partial fills and settlement

## Key Risks

- The hedge never becomes available
- Second-leg execution, latency, and slippage
- Changing liquidity
- Partial fills that leave unequal size
- Incorrect market pairing
- Treating an informational dump as panic

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including exact dump or pair-cost thresholds, lookbacks, and production configuration.

## Further Research

[Handbook: Dump & Hedge](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/hedging-arbitrage/dump-hedge.md)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
