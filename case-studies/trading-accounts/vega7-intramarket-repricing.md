# @vega7 — Intramarket Repricing in BTC 5-Minute Markets

**Account:** [@vega7](https://polymarket.com/@vega7?tab=activity)
**Ownership:** Demonstrated by PolyTutor
**Evidence:** [View ownership evidence](./ownership-evidence.md#vega7)
**Public profile:** [Open Polymarket](https://polymarket.com/@vega7?tab=activity)

**Public trading-pattern analysis** · **Status:** Public Activity Analysis
**Research classification:** Price Dislocation / Short-Duration Execution

<p align="center">
  <img
    src="../../assets/trading-accounts/vega7-probability-repricing.png"
    alt="Intramarket probability-repricing family — illustrative diagram, not a reconstruction of every trade"
    width="100%"
  />
</p>

The diagram summarizes the research family. Exact thresholds and execution logic remain private.

The observed and externally reported behavior is consistent with participation inside BTC five-minute markets and an attempt to benefit from large probability repricing during the window. The owner situates this account in intramarket-repricing research. That is **not** a reconstruction of exact private software, and not every trade is claimed to follow one documented strategy.

> This page combines publicly observable market records, the owner’s research framing, and supplementary third-party analytics. Public information may be incomplete and does not reveal exact signal generation, complete position history, private implementation, or the full execution sequence.

---

## Why this study is more cautious

Direct public-profile retrieval was not consistently available during external verification. Independent **market-level** records confirm Vega7 participates in BTC 5-minute Up/Down markets.

A third-party wallet-analysis page describes a short-duration low-price-entry / repricing-exit pattern, but that source reports incomplete activity retrieval and contains internally inconsistent statistics. PolyTutor does **not** treat those numbers as verified.

Evidence is split into:

- Verified market-level evidence
- Third-party reported behavior
- PolyTutor owner’s explanation
- PolyTutor inference
- Unknown / exact private implementation

---

## Classification

**Short-Duration Price Dislocation / Intramarket Repricing**

```text
@hanwuji
→ primarily near-resolution / high-price entries

@jhjhjhjhjh
→ low-side optionality + possible paired hedge

@vega7
→ intramarket entry + repricing + exit
```

The observed activity raises research questions related to Price Dislocation, Low-Side Dual Reversion, Binary Momentum, Polymarket CLOB research, and [Crypto Short-Duration Markets](../../bots/crypto-short-duration.md). The owner discloses the account for that research context. It does not establish that every fill follows an exact handbook strategy.

---

## Relation to PolyTutor research

The PolyTutor owner discloses this account as one used in trading research and experimentation around **intramarket price dislocation and repricing** in BTC 5-minute markets.

Verified market-level records show participation. The owner’s explanation places the account in a path-trading / intramarket-exit family rather than a pure hold-to-settlement strike. Inferred repricing intent is labeled in the table below. Exact private implementation is not published.

---

## Verified market-level evidence

Public market records establish that Vega7 has participated in BTC five-minute Up/Down markets.

### Example A

**Bitcoin Up or Down — September 7, 2:10PM–2:15PM ET**

Public market analytics listed Vega7 among significant Down holders, with approximately **481 Down shares**.

This establishes exposure to a BTC five-minute market. It does **not** establish original entry price, entry timing, exact exit logic, or why the position was opened.

### Example B

**Bitcoin Up or Down — May 8, 12:40AM–12:45AM ET**

Public market records show a Vega7 transaction involving the Down outcome around **99.9¢**. The record indicates a negative share delta, which is consistent with disposal or selling of shares.

That demonstrates participation near an extreme probability state. It does not, by itself, document the original acquisition price.

---

## Third-party reported pattern

A third-party wallet-analysis source characterizes Vega7 as heavily focused on BTC five-minute markets and describes behavior resembling:

```text
Enter at lower probability price
            ↓
Market reprices
            ↓
Exit before settlement
```

That source also reports incomplete activity retrieval, contains inconsistent counts, and makes interpretations that are not independently established.

PolyTutor treats it as **supporting / hypothesis-generating evidence**, not verified strategy documentation. Its claimed win rates, volumes, trade frequencies, average entries, buy/sell ratios, and withdrawal totals are **not copied here**.

---

## Observed vs reported vs inferred

| Finding | Evidence Type | Confidence |
| --- | --- | --- |
| Vega7 participates in BTC 5-minute markets | Verified market-level | High |
| Vega7 held substantial Down exposure in a reviewed BTC 5m market | Verified market-level | High |
| Vega7 disposed of Down shares around 99.9¢ in a reviewed BTC 5m market | Verified market-level | High |
| Account frequently trades BTC 5-minute markets | Third-party reported + supporting evidence | Medium/High |
| Account seeks intramarket repricing | Inferred | Medium |
| Account buys distressed/cheap probability and sells after recovery | Third-party reported / inferred | Medium |
| Account always exits before settlement | Unknown | — |
| Account uses fixed 5–10¢ entries | Unknown | — |
| Account uses a fixed 60–80¢ exit | Unknown | — |
| Account has a 100% true strategy win rate | Not established | — |
| Exact signal source | Unknown | — |
| Exact execution thresholds | Unknown | — |

---

## Strategy concept

```text
5-Minute BTC Market
        ↓
Probability / Price Dislocation
        ↓
Entry Opportunity
        ↓
Market State Changes
        ↓
Rapid Repricing
        ↓
Exit Opportunity
        ↓
Close Position Before Resolution
```

That is different from a settlement-oriented hold.

---

## Settlement trading vs intramarket trading

A trader does not necessarily need to predict the final binary outcome if the objective is to trade changes in probability **before** settlement.

`Illustrative only.` Not a Vega7 trade.

```text
Buy YES @ 0.15

Market reprices

Sell YES @ 0.43
```

The position may close before resolution.

```text
Trading the probability path
```

is a different economic hypothesis from

```text
Trading the final outcome
```

> **A prediction-market bot does not always need to trade the final outcome. It can trade the evolution of probability itself.**

```text
Outcome strategy
→ Am I right at settlement?

Repricing strategy
→ Can I enter and later exit at a better probability price?
```

---

## Why five-minute markets fit this research

BTC 5-minute markets can reprice quickly because spot or reference prices move continuously, little time remains, implied probability can jump, liquidity changes through the interval, book participants react, and late-stage certainty can push prices to extremes.

Those conditions do not create guaranteed profit. See [BTC 5-Minute Markets — Direction vs Execution](../btc-5m-execution.md).

---

## Possible repricing example

`Illustrative research scenario — not a Vega7 historical trade.`

```text
Market opens

YES = 0.42

BTC moves downward quickly

YES drops to 0.12

System evaluates whether
the move is overextended

YES recovers to 0.31

Position exits
```

The point is intramarket repricing, not a claimed fill history.

---

## Reversion or momentum?

Public records alone do not show whether Vega7 trades:

- **Reversion** — buy after an extreme move, expect partial recovery
- **Momentum** — enter with the move, exit as probability continues
- **Microstructure dislocation** — gaps among external BTC movement, Polymarket probability, book behavior, and timing

Current evidence is **insufficient to distinguish** these. That uncertainty stays visible.

---

## Reference architecture

This is a PolyTutor reference architecture for this research family, not a reconstruction of the account’s private software.

```text
BTC / Reference Data
        +
Polymarket CLOB
        ↓
Market-State Engine
        ↓
Dislocation Detector
        ↓
Entry Validation
        ↓
Risk Engine
        ↓
Execution
        ↓
Position Monitor
        ↓
Repricing / Exit Logic
        ↓
Close Position
```

---

## Entry edge ≠ exit edge

`Illustrative only.` Even if a system sees an attractive entry such as `YES @ 0.12`, it still must decide when to exit, whether liquidity exists, whether the move is continuing, whether spread makes the exit unattractive, whether the signal is still valid, and whether settlement is too close.

A good entry is not a complete strategy.

---

## Mark-to-market vs settlement

This family should care about realizable P&L:

```text
Entry Price
      ↓
Current Executable Bid
      ↓
Realizable P&L
```

not only eventual `$0` or `$1` settlement. That is what separates a repricing engine from a pure hold-to-settlement strategy.

---

## A repricing is only useful if it can be executed

`Illustrative only.`

```text
Displayed probability:
YES = 0.40

Best executable bid:
YES = 0.34
```

A system cannot assume it exits at midpoint. Best bid, best ask, spread, depth, available quantity, and slippage determine whether the move is tradeable.

---

## Sizing and exits (conceptual only)

Small, repeated short-duration size can reduce impact and limit tail exposure. That is a family-level observation, not Vega7’s formula.

Possible **time-based** considerations: maximum hold, time remaining, signal expiry, close proximity.

Possible **price/state** considerations: target repricing reached, expected value gone, spread widening, signal reverse, risk limit.

No exact thresholds are published, and none are attributed to Vega7.

---

## Main risks

- **No reversion.** A cheap outcome can go to zero.
- **Catching a falling knife.** Low price is not automatically mispriced.
- **Spread** can consume the paper edge.
- **Thin liquidity** may block the intended exit quantity.
- **Partial exit** leaves residual exposure.
- **Latency** can remove the exit.
- **Settlement proximity** leaves less time for a path trade.
- **External BTC shock** inside the five-minute window.
- **Resolution source** is the contract’s stated mechanism, not whichever spot chart a trader is watching.

---

## Engineering questions raised by this pattern

Research questions, not published answers:

- What defines a genuine probability dislocation?
- How can the system distinguish reversion from continued momentum?
- Which reference data should drive the signal?
- How quickly must the book be sampled?
- When is an entry price actually executable?
- How should exit liquidity be measured?
- How much repricing is required after fees?
- When should an unprofitable position be abandoned?
- How should maximum holding time be defined?
- How does time-to-resolution alter the required edge?
- How should repeated five-minute opportunities be risk-budgeted?
- How should the bot distinguish midpoint P&L from realizable P&L?

> **Direction alone is not an edge. Execution is part of the strategy.** A path trade that cannot exit is still a directional position.

---

## Related research

- [Price Dislocation](../../bots/price-dislocation.md)
- [Dual-Price Reversion](../../bots/dual-price-reversion.md)
- [Crypto Short-Duration Markets](../../bots/crypto-short-duration.md)
- [Architecture](../../engineering/architecture.md)
- [BTC 5-Minute Markets — Direction vs Execution](../btc-5m-execution.md)
- [Strategy Handbook](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook) — Price Dislocation, Low-Side Dual Reversion, Binary Momentum, Polymarket CLOB families

← [Trading-accounts index](./README.md) · [Case studies](../README.md) · [Commercial README](../../README.md)
