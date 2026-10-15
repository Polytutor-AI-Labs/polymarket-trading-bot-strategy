# Crypto Short-Duration Markets

**Status:** Research
**Area:** 5-minute / 15-minute / hourly crypto prediction markets
**Research source:** Grouped handbook research across short-duration crypto Up/Down markets, including momentum, oracle/cross-feed, Binance-feed, and CLOB timing pages in the [Strategy Handbook catalog](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#strategy-catalog)

> This page describes a research and engineering area, not a claim of current profitability or production readiness.

## Overview

Short-duration crypto prediction markets compress price discovery, execution, information latency, and risk into very small time windows.

PolyTutor research in this area includes BTC and related crypto Up/Down markets, short market duration, external price feeds, prediction-market prices, and timing. Individual internal engine names stay in the handbook so this page remains a category, not a product list.

> **Direction alone is not an edge. Execution is part of the strategy.**

Two systems can predict the same direction and still produce different outcomes because of entry price, latency, spread, liquidity, slippage, time remaining, and fills.

PolyTutor can work with clients on systems involving this research area, subject to feasibility, scope, and strategy review.

## Market Idea

A short crypto window asks whether an external reference, the binary book, or token-native momentum contains information the market has not yet priced — and whether that information can still be executed before settlement.

Historically researched windows include 5-minute markets, with related 15-minute and hourly discussion in the handbook.

## System Flow

```text
External Market Data
        +
Polymarket CLOB
        ↓
Time Synchronization
        ↓
Signal / Market-State Analysis
        ↓
Risk Validation
        ↓
Execution Decision
        ↓
Position Management
        ↓
Resolution
```

## Engineering Focus

- Combining venue books with external references
- Clock alignment across feeds
- Signal versus tradeability
- Late-window order lifecycle
- Position state through settlement
- Distinguishing backtest, simulation, and any later live path

## Key Risks

- Feed lag and mismatched clocks
- Book synchronization errors
- Spread and slippage consuming a paper gap
- Time remaining too short to complete an intended order
- Partial fills
- Treating a correct direction as a profitable trade

## What Is Intentionally Not Published

Public documentation focuses on architecture and research concepts. Implementation-specific parameters and proprietary execution logic are intentionally excluded, including engine identifiers as a product catalog, lookbacks, feed thresholds, and latch rules.

## Further Research

- [Handbook catalog](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#strategy-catalog)
- [Last-Seconds Research](./last-seconds.md) for settlement-proximity work
- [Architecture](../engineering/architecture.md)

← [Back to Bot & System Research](./README.md)

[Commercial README](../README.md)
