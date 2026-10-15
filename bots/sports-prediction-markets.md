# Sports Prediction Markets

**Status:** Research
**Area:** Event-state modeling
**Research source:** [Live Sports State Fair Value](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/sports-event-modeling/live-sports-state-fair-value.md) (external public research)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Research around converting changing live-game information into prediction-market fair-value estimates and comparing those estimates with executable prices.

The public handbook page is based on external public research. This is not a claim that PolyTutor operates a production sports bot.

Conceptual inputs studied in this area can include score, game time, match state, event context, market probability, and liquidity. This page does not invent a proprietary sports model.

This research area may inform custom trading-system development after feasibility review.

## Market Idea

Live sports state changes faster than a static pre-game price. The research question is whether a state-based probability estimate can disagree with the market by enough, after feed lag, spreads, and clustering, to be worth studying as a paper idea.

## System Flow

```text
Live Event State
       ↓
State Normalization
       ↓
Probability / Fair-Value Research
       ↓
Market Comparison
       ↓
Risk Validation
       ↓
Potential Execution
       ↓
Event / Position Monitoring
```

## Engineering Focus

- Ingesting and normalizing live event state
- Mapping state to a research probability, not a guaranteed forecast
- Comparing model output with executable CLOB prices
- Handling suspensions, corrections, and feed gaps
- Position monitoring through the remainder of the event

## Key Risks

- Delayed or inconsistent sports data
- Suspended markets
- Score corrections
- Event-feed differences
- Modeling error
- Thin liquidity
- Sudden game-state shocks (injury, card, weather, and similar)
- Settlement-rule differences from broadcast intuition

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including model coefficients, proprietary feature sets, and production configuration.

## Further Research

[Handbook: Live Sports State Fair Value](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/sports-event-modeling/live-sports-state-fair-value.md)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md) · [Architecture](../engineering/architecture.md)
