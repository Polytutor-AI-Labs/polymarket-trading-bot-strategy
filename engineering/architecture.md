# Trading System Architecture

This is a conceptual reference architecture for Polymarket and prediction-market systems. Individual implementations differ. Not every deployment uses every layer, and this document does not describe a single production stack.

```text
             Market / CLOB
                   │
                   ▼
            Market Data Layer
                   │
                   ▼
             Signal Engine
                   │
                   ▼
            Strategy Engine
                   │
                   ▼
              Risk Engine
                   │
                   ▼
           Execution Engine
                   │
          ┌────────┴────────┐
          ▼                 ▼
     Order State       Position State
          │                 │
          └────────┬────────┘
                   ▼
                Analytics
```

Compact form used on the [README](../README.md):

```text
Market
   ↓
Market Data
   ↓
Signal Engine
   ↓
Strategy Engine
   ↓
Risk Engine
   ↓
Execution Engine
   ↓
Position Manager
   ↓
Analytics
```

> **Direction alone is not an edge. Execution is part of the strategy.**

A strategy is a hypothesis. A bot is the system that observes, validates, risks, executes, and records.

## Market Data

The market-data layer collects what the rest of the system is allowed to see:

- Polymarket CLOB state and trades
- Outcome metadata
- External reference feeds when a strategy uses them
- On-chain or venue events when a strategy uses them (for example, fill detection in copy-trading research)

Concerns at this layer: freshness, clock alignment, reconnects, and not treating a delayed print as current truth.

Documented public research mentions Rust implementations, Polymarket CLOB access, Polygon activity for copy-trading research, and WebSocket streams. Those are examples of work that exists in research records, not a required bill of materials.

## Signal Layer

The signal layer turns data into a candidate:

- Crosses, dislocations, book features, leader fills, or model estimates
- Validity checks: is the print coherent, timely, and in-scope?

A signal is not a trade. The handbook principle applies here: **a signal is not automatically a trade.**

## Strategy Layer

The strategy layer decides what the signal would mean if it were actionable:

- Direction, pair, quote, or hold-to-settlement intent
- State: latches, one-shot windows, complementary-leg waits
- What “done” means for the idea (exit, hedge, settlement, cancel)

Exact thresholds, lookbacks, and latch rules are not published in this repository. They belong in private research or the handbook’s educational pages, not in a commercial landing site.

## Risk Layer

The risk layer can reject or resize a candidate before an order is sent. Depending on the strategy and deployment, checks may include size, exposure, liquidity, spread, slippage, balances, allowances, and duplicate-order protection.

See the [Risk Management](../README.md#risk-management) section on the README. Not every system implements every control.

## Execution Layer

The execution layer turns an accepted candidate into venue orders and follows their lifecycle:

- Order construction
- Submit, acknowledge, cancel, replace
- Timeouts
- Partial fills
- Misses

Paper fills and live fills are different objects. Queue position, latency, and book movement sit in this layer, not in the hypothesis.

## Position Management

Position state is what remains after fills:

- Open size and average price
- One-sided leftover after a failed hedge
- Settlement versus early exit
- Reconciliation when the venue state and local state disagree

For copy-trading research, follower position is a separate object from the leader fill that triggered the idea.

## Analytics / Observability

Analytics records what happened so the system can be studied:

- Signal versus order versus fill
- Reject reasons
- Latency and reconnect events
- Environment labels: backtest, simulation, paper, live

PolyTutor does not mix those environments when discussing results. This repository does not publish performance statistics.

## Related documents

- [README](../README.md)
- [Strategy family map](../strategies/README.md)
- [PolyTutor Strategy Handbook](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook)
