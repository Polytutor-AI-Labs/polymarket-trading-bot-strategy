# Copy Trading

**Status:** Research
**Area:** Leader-following execution
**Research source:** [Leader-Follower Copy Trading](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/copy-trading/leader-follower-copy-trading.md)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Research into observing an identified leader's market activity and translating eligible actions into follower-side execution according to independently defined risk and sizing controls.

A leader fill is not a follower fill. Detection delay, a later book, and missing liquidity can change the economics the leader received.

PolyTutor can work with clients on systems involving this research area, subject to feasibility, scope, and strategy review.

## Market Idea

Some traders treat another participant’s observed execution as a signal. The research question is whether a follower can capture any residual value after later detection, a different executable price, and a separate risk policy.

## System Flow

```text
Leader Activity
      ↓
Event Detection
      ↓
Eligibility Checks
      ↓
Position Translation
      ↓
Risk Validation
      ↓
Follower Execution
      ↓
Position Tracking
```

## Engineering Focus

- Event detection and fill or activity interpretation
- Market and outcome identification
- Direction matching in the same outcome token
- Follower sizing as a separate policy layer
- Duplicate-event prevention
- Execution timing versus the leader event
- Partial fills and position reconciliation

## Key Risks

- Leader latency and detection delay
- Price movement between leader and follower
- Liquidity, slippage, and partial fills
- Leader behavior changes
- Follower capital and risk limits that differ from the leader
- Market-resolution risk on the copied outcome

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including leader wallet addresses, private wallet lists, sizing rules, exact percentages, execution thresholds, customer configuration, and source code.

## Further Research

[Handbook: Leader-Follower Copy Trading](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/copy-trading/leader-follower-copy-trading.md)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
