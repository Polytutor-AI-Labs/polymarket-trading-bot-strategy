# BTC 5-Minute Markets — Direction vs Execution

**Status:** Research
**Area:** Short-duration crypto prediction markets

> **Direction alone is not an edge. Execution is part of the strategy.**

This is an engineering case study. It is not a profit report, not a backtest, not a live-trading claim, and not a disclosure of a private strategy. PolyTutor has not “solved” BTC 5-minute markets.

---

## The problem

A trader may correctly believe BTC will finish a five-minute interval higher or lower. That does not automatically make the trade profitable.

In short-duration prediction markets the result depends on:

- when the position is entered
- what price is paid
- current spread
- available liquidity
- order latency
- whether the order fills
- partial fills
- time remaining
- changing external-market information
- Polymarket book state
- resolution conditions

A bot is not “predict UP or DOWN.” It is a system that must still have an acceptable trade after those constraints.

---

## Why five minutes changes everything

A five-minute market compresses the full path into one short window:

```text
signal generation
market-data processing
decision-making
risk checks
order creation
network transit
matching
fills
position management
settlement
```

A delay that is minor on a multi-hour market can change the executable price, the remaining depth, or whether a fill is still useful before resolution.

---

## Correct Direction ≠ Good Trade

`Illustrative example only.` Not a PolyTutor trade.

```text
Trader A
Predicts UP
Buys YES at 0.55

Trader B
Predicts UP
Buys YES at 0.82

Same direction.
Very different risk/reward.
```

If both are right, A paid 0.55 for a claim that settles at 1.00; B paid 0.82. Downside, required confidence, and room for fees or slippage are not the same. **Same direction is not the same trade.**

---

## Latency Changes the Trade

```text
External Price Move
        ↓
Data Feed
        ↓
Signal Detection
        ↓
Strategy Validation
        ↓
Risk Checks
        ↓
Order Construction
        ↓
Network / API
        ↓
Polymarket CLOB
        ↓
Fill
```

The market can move at every step.

> A strategy evaluated at time T may face a different executable price at T + Δ.

This page does not publish measured latencies.

### Signal latency vs execution latency

**Signal latency** is the time between market information changing and the system recognizing that change.

**Execution latency** is the time between deciding to trade and the order becoming executable or filled.

Both matter. Stale data, a stale book, asynchronous APIs, network delay, venue processing, and matching can each move the fill away from the price that justified the signal.

---

## Spread Can Destroy an Apparent Edge

`Illustrative only.`

Suppose a model estimates fair value near:

```text
YES = 0.56
```

and the executable book is:

```text
Bid: 0.51
Ask: 0.60
```

An “edge” computed from midpoint (0.555) or from a stale print may not exist at the **ask** you actually pay. Systems should reason about **best bid**, **best ask**, and **executable price**, not only a displayed probability.

---

## Liquidity Is Part of the Strategy

Seeing `YES ask = 0.54` does not mean a large position executes entirely at 0.54.

`Illustrative only.`

```text
0.54   small quantity
0.55   more quantity
0.57   more quantity
```

Size walks the book. Average fill, market impact, and remaining depth are part of the strategy, not an afterthought.

---

## Partial Fills Change Strategy State

Desired position and filled position can diverge:

```text
Desired:  100 units
Filled:    37 units
```

The system must decide what happens next: retry, accept the exposure, cancel, reprice, hedge, or wait. There is no universal answer. The choice belongs to the strategy and its risk model. Leaving 37 units unmanaged is still a decision.

---

## Time Remaining Is a State Variable

```text
Entry with 4:30 remaining
```

is not the same object as

```text
Entry with 0:15 remaining
```

even if the displayed prices look similar. Less time means less room for recovery, different information certainty, often different liquidity, and settlement proximity. Exact proprietary entry windows are not published here.

---

## Two Markets Can Move at Different Speeds

Short-duration crypto systems may observe spot venues, futures, oracle or reference feeds, and the Polymarket CLOB. Those sources do not update as one clock.

```text
External BTC Market
        ↓
Price Change
        ↓

        timing gap

        ↓
Polymarket Price Adjustment
```

Research may study those gaps. A gap is not guaranteed arbitrage. By the time an order is live, the book may already have moved.

---

## The Order Book Is More Than One Price

Two markets with the same last trade can still differ in:

- best bid and best ask
- depth and spread
- imbalance
- cancellations and incoming orders
- stale resting quotes

Execution quality lives in that state, not in the last print.

---

## A Strategy Can Be Right and Still Fail

`Illustrative scenario — not a historical PolyTutor trade.`

```text
1. System detects BTC upward momentum.

2. YES is observed near 0.57.

3. Signal passes validation.

4. Before the order reaches the book,
   the ask moves to 0.66.

5. Only part of the order fills.

6. The remaining market window is short.

7. The original expected-value calculation
   is no longer valid.
```

The directional hypothesis may still have been correct. The **executable** trade changed. That is a research and engineering problem, not a slogan about being “right.”

---

## What an Execution Engine Must Think About

Conceptually, after a candidate is accepted:

- current executable price
- order type and requested quantity
- available depth
- fill state, cancel, replace
- remaining time
- position exposure
- maximum acceptable slippage
- whether the strategy is still valid after delay

See [Trading System Architecture](../engineering/architecture.md). Exact rules stay private.

---

## Execution and Risk Are Connected

An execution decision should not ignore risk.

```text
Signal
   ↓
Is market still valid?
   ↓
Is price still acceptable?
   ↓
Is liquidity acceptable?
   ↓
Is exposure acceptable?
   ↓
Is enough time remaining?
   ↓
Execution
```

Exact gates differ by system. Skipping them turns a hypothesis into an unconstrained order.

---

## The PolyTutor Research Loop

```text
Hypothesis
    ↓
Data
    ↓
Model / Strategy
    ↓
Simulation
    ↓
Execution Testing
    ↓
Failure Analysis
    ↓
Refinement
    ↓
Revalidation
```

A strategy is not complete because one signal looked promising. Research should test **decision quality** and **execution quality**.

---

## What Should Be Measured

Candidate metrics — not published values, and not a claim that this repository reports them:

| Layer | Questions |
| --- | --- |
| Signal | Accuracy, confidence, freshness |
| Execution | Decision-to-order time, fill latency, fill ratio, average entry, slippage |
| Market | Spread, depth, liquidity, time remaining |
| Risk | Exposure, failed orders, partial fills, path of capital |

Do not treat a paper midpoint series as a fill series.

---

## Why This Matters When Building a Bot

A client may start with:

> “When BTC moves strongly upward, buy YES.”

Turning that into a trading system requires harder questions:

- Which BTC price source?
- What defines “moves strongly”?
- How fresh can the data be?
- What market price is acceptable?
- What if liquidity disappears?
- What if only part of the size fills?
- When does the signal expire?
- What if the external market reverses?
- What happens near market close?
- How is exposure limited?

That is where strategy research becomes **trading-system engineering**.

---

## What Is Intentionally Not Published

Public documentation excludes exact thresholds, signal parameters, private feed configuration, proprietary timing windows, production latency measurements, sizing algorithms, wallet configuration, live credentials, proprietary execution logic, and client-specific settings.

---

## Related research

Related system research: [Crypto Short-Duration Markets](../bots/crypto-short-duration.md)

[Architecture](../engineering/architecture.md) · [Strategy Handbook](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook) · [Commercial README](../README.md) · [Case study index](./README.md)

---

Predicting the market is only one part of automated trading. Data freshness, latency, liquidity, price, fills, timing, position state, and risk determine whether a signal can become a viable trade.

> **Direction alone is not an edge. Execution is part of the strategy.**
