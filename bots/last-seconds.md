# Last-Seconds & Settlement-Proximity Research

**Status:** Research
**Area:** Timing / settlement proximity
**Research source:** [99¢ Sniper — Near-Resolution Strike](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/99-cent-sniper.md) and related last-seconds timing research in the handbook

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Research around markets approaching resolution or extremely short remaining time: near-$1 prices, last-window feed and CLOB state, and whether apparent certainty survives execution.

This is a research family, not a product named “Last Sniper.” A high win rate near $1 can still have negative expected value.

PolyTutor can work with clients on systems involving this research area, subject to feasibility, scope, and strategy review.

## Market Idea

Near resolution, one outcome often trades close to $1. The research question is whether the remaining gap to settlement is compensation for residual flip risk, or a dislocation. Separate handbook work studies last-window external feeds and book features; those engines stay in the handbook rather than as named products here.

## System Flow

```text
Market
   ↓
Time-to-Resolution
   ↓
Price / Feed State
   ↓
Resolution Confidence Checks
   ↓
Liquidity / Spread Validation
   ↓
Potential Execution
   ↓
Settlement
```

## Engineering Focus

- Timing and clock synchronization
- External-feed freshness versus the binary book
- CLOB state near the close
- Settlement conditions versus intuitive event outcomes
- Order latency and market-close behavior
- Unresolved information at the decision time

## Key Risks

- Apparent certainty may be false
- Settlement criteria can differ from an intuitive event outcome
- External feeds can lag
- Late orders may not fill
- Market suspension or resolution disputes
- Final-window volatility
- Payoff asymmetry: a 99¢ long can lose almost the full premium

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including exact timing windows, price gates, and feed thresholds.

## Further Research

- [Handbook: 99¢ Sniper — Near-Resolution Strike](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/99-cent-sniper.md)
- Related last-seconds feed and CLOB research in the [Strategy Handbook](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md) · [Crypto Short-Duration](./crypto-short-duration.md)
