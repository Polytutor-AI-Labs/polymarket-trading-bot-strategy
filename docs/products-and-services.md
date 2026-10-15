# Products & Custom Development

This page is the detailed engagement and service reference. The flagship catalog is [Trading Systems](../products/README.md). Bespoke work is summarized in [Custom Polymarket Bot Development](../products/custom-development.md).

**From trading idea to executable Polymarket system.**

PolyTutor helps traders, researchers and teams design and build Polymarket automation around specific trading hypotheses, execution requirements and risk constraints.

The public catalog of flagship systems is [products/README.md](../products/README.md). This page explains the broader custom-development funnel.

| Public label | Meaning |
| --- | --- |
| **AVAILABLE** | A working system exists and commercial delivery or customization can be discussed. |
| **CUSTOM BUILD** | Relevant research and implementation experience exist; the client system is built to their requirements. |
| **RESEARCH** | Public research exists and is not offered as a commercial system. |

Fit depends on the hypothesis, data, execution path, risk, and scope. Not every idea should become a bot. Trading software does not guarantee profit.

[Explore Trading Systems](../products/README.md) · [Request a Bot](https://github.com/polytutor-labs-handbook/polymarket-trading-bots/issues/new?template=bot-request.yml) · [Contact PolyTutor](./contact.md)

---

## 1. Custom Polymarket Trading Bot

For clients who already know what they want to trade.

Example market settings include [BTC 5-minute markets](../case-studies/btc-5m-execution.md), [short-duration crypto markets](../bots/crypto-short-duration.md), [sports prediction markets](../bots/sports-prediction-markets.md), event-driven markets, and client-selected categories.

A custom bot may include some of the following, depending on scope:

- market scanning
- signal engine
- order execution
- position tracking
- risk limits
- logs
- monitoring
- deployment

A delivered system is software and infrastructure. It is not a promise of profitability.

---

## 2. Strategy → Automation

For clients who have a manual strategy or trading hypothesis.

```text
Manual Idea
    ↓
Strategy Specification
    ↓
Rules & Edge Cases
    ↓
Architecture
    ↓
Implementation
    ↓
Simulation
    ↓
Validation
    ↓
Deployment
```

PolyTutor can help translate a workflow such as “when X happens, I usually buy YES” into a formal system definition. That typically covers:

- inputs
- conditions
- timing
- position sizing
- exits
- failure cases
- risk controls

Not every specification reaches implementation or deployment. Simulation and live trading are different environments.

---

## 3. Research-Based Bot Development

Clients may want systems inspired by research areas already studied by PolyTutor.

These are research areas, not guaranteed profitable products. They are not offered as named off-the-shelf bots.

| Research area | Public page |
| --- | --- |
| Near-resolution execution | [Last-Seconds Research](../bots/last-seconds.md) |
| Price dislocation | [Price Dislocation](../bots/price-dislocation.md) |
| Low-side optionality | [Price Dislocation](../bots/price-dislocation.md) · [Dual-Price Reversion](../bots/dual-price-reversion.md) |
| Paired hedging | [Dump & Hedge](../bots/dump-hedge.md) · [Dual-Price Reversion](../bots/dual-price-reversion.md) |
| Reversion | [Dual-Price Reversion](../bots/dual-price-reversion.md) |
| Market making | [Market Making](../bots/market-making.md) |
| Short-duration crypto | [Crypto Short-Duration](../bots/crypto-short-duration.md) |
| Copy trading | [Copy Trading](../bots/copy-trading.md) |
| Intramarket probability trading | [@vega7 case study](../case-studies/trading-accounts/vega7-intramarket-repricing.md) |

A project in one of these areas still needs its own specification, feasibility review, and implementation plan.

---

## 4. Existing Bot Improvement

For a client who already has code.

Depending on the codebase and project scope, work may include:

- architecture review
- execution improvements
- latency investigation
- WebSocket handling
- order lifecycle
- partial fills
- retry logic
- state reconciliation
- risk controls
- monitoring
- logging
- VPS deployment
- reliability

Documented public research mentions Rust implementations, Polymarket CLOB interaction, Polygon activity used for copy-trading research, and WebSocket streams. That is evidence of work that exists in research records, not a claim that every language or hosting setup is a standard delivery stack.

---

## 5. Backtesting / Simulation Infrastructure

A bot should ideally be evaluated before capital is exposed.

Potential tooling, depending on scope:

- historical replay
- paper/simulation mode
- execution modeling
- slippage assumptions
- fee modeling
- latency assumptions
- trade logging
- strategy metrics
- failure analysis

Simulation, backtests, and paper trading are not live results. They do not guarantee fill quality or future performance.

---

## 6. Deployment & Monitoring

When a project includes operations work, potential services include:

- Linux/VPS deployment
- process management
- environment configuration
- restart/recovery
- logging
- monitoring
- configuration separation
- secret handling
- update workflow

Individual deployments differ. This page does not name a required cloud provider or claim a single production stack.

---

## Systems We Can Research or Engineer

These are engineering problem areas, not ready-built products.

| Area | Typical Problem |
| --- | --- |
| [Near-Resolution](../bots/last-seconds.md) | Timing and late-market execution |
| [Price Dislocation](../bots/price-dislocation.md) | Detect unusual probability pricing |
| [Paired Hedge](../bots/dump-hedge.md) | Manage two-leg exposure |
| [Reversion](../bots/dual-price-reversion.md) | Trade temporary dislocations |
| [Intramarket Trading](../case-studies/trading-accounts/vega7-intramarket-repricing.md) | Enter and exit before resolution |
| [Copy Trading](../bots/copy-trading.md) | Translate leader activity into follower execution |
| [Market Making](../bots/market-making.md) | Quote and manage inventory |
| [Short-Duration Crypto](../bots/crypto-short-duration.md) | 5m / 15m / hourly market automation |
| [Sports Markets](../bots/sports-prediction-markets.md) | Event-state-driven prediction trading |

Related execution notes: [BTC 5-Minute Markets — Direction vs Execution](../case-studies/btc-5m-execution.md).

---

## What Can Be Customized?

Exact availability depends on project scope.

### Markets

Examples supported by existing PolyTutor research or PolyTutor-controlled account activity:

- BTC
- ETH
- SOL
- XRP
- sports
- event markets
- client-selected markets

### Strategy

- entry conditions
- exits
- hedge logic
- market selection
- signal source
- time window

### Risk

- position size
- market exposure
- total exposure
- maximum loss controls
- trading limits
- kill switches

### Execution

- order type
- price tolerance
- retries
- partial-fill handling
- cancellation logic

### Operations

- configuration
- logging
- notifications
- monitoring
- deployment

---

## How a Project Works

```text
01 — Strategy / Requirement Review
          ↓
02 — Feasibility Analysis
          ↓
03 — Technical Specification
          ↓
04 — Architecture
          ↓
05 — Development
          ↓
06 — Simulation / Testing
          ↓
07 — Client Review
          ↓
08 — Deployment
          ↓
09 — Monitoring / Iteration
```

**01 — Strategy / Requirement Review.** What should be traded, under what conditions, and with what constraints.

**02 — Feasibility Analysis.** Whether the hypothesis, data, execution path, and risk model can be engineered as specified.

**03 — Technical Specification.** Inputs, rules, edge cases, position behavior, and failure handling.

**04 — Architecture.** How market data, signals, risk, execution, and position state fit together. See [Trading System Architecture](../engineering/architecture.md).

**05 — Development.** Implementation of the agreed specification.

**06 — Simulation / Testing.** Replay, paper/simulation, or other agreed evaluation before any capital discussion.

**07 — Client Review.** Confirm behavior against the specification.

**08 — Deployment.** Only if the project includes operations work and the client chooses to proceed.

**09 — Monitoring / Iteration.** Logging, review, and controlled changes if that work is in scope.

Not every project reaches live deployment. Some engagements stop at research, specification, architecture, or simulation.

---

## What We Need From You

Useful starting material includes:

- target Polymarket markets
- strategy description
- entry conditions
- exit conditions
- position sizing idea
- expected trading frequency
- risk constraints
- current bot/code if applicable
- preferred deployment environment
- whether source-code delivery is required
- maintenance expectations

> You do not need to have every technical detail defined. A manual trading workflow can be used as the starting point for system design.

## Do Not Send Sensitive Credentials

Never send through GitHub issues:

- seed phrases
- private keys
- exchange passwords
- unrestricted API credentials
- VPS passwords
- wallet recovery phrases

Credentials should only be configured through an agreed secure process.

See [SECURITY.md](../SECURITY.md).

---

## Engagement Types

### New Bot

Build a new system from requirements.

### Existing Bot Upgrade

Improve an existing implementation.

### Strategy Research Prototype

Build a simulation/research implementation before production consideration.

### Execution Infrastructure

Focus primarily on order execution, market data and reliability.

### Consulting / Architecture Review

Review a strategy or existing design before development.

Scope and commercial terms are agreed per project. This page does not list prices.

---

## Source Code & Licensing

> Source-code delivery, licensing, exclusivity, redistribution rights and ongoing maintenance depend on the individual project agreement.

This repository does not state that all source code is included, and it does not state that all source code remains private. Those terms are project-specific.

---

## Trading Risk

PolyTutor builds trading software and research infrastructure.

We do not guarantee:

- profitability
- win rate
- ROI
- market availability
- fill quality
- future strategy performance

Liquidity changes. Market structure changes. A strategy edge can disappear. Execution differs from simulation. Software can fail.

[Full disclaimer](../DISCLAIMER.md)

---

## Research Informed by Real Markets

PolyTutor research is informed by PolyTutor-controlled accounts. Ownership demonstrations are available:

- [@hanwuji](../case-studies/trading-accounts/hanwuji-near-resolution.md) — near-resolution research
- [@jhjhjhjhjh](../case-studies/trading-accounts/jhjhjhjhjh-low-side-hedge.md) — low-side optionality / paired hedge research
- [@vega7](../case-studies/trading-accounts/vega7-intramarket-repricing.md) — intramarket probability repricing research

Historical activity does not guarantee future performance.

[Explore Trading Evidence →](../case-studies/trading-accounts/README.md)

---

## Build With PolyTutor

> Have a Polymarket strategy you want to automate, a bot that needs improvement, or an execution problem you want to solve?

**Start with a project request.** Trading systems involve risk and future performance cannot be guaranteed.

[Explore Trading Systems](../products/README.md) · [Request a Bot](https://github.com/polytutor-labs-handbook/polymarket-trading-bots/issues/new?template=bot-request.yml) · [Contact PolyTutor](./contact.md)
