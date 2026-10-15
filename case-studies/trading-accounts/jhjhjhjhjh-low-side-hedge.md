# @jhjhjhjhjh — Low-Side Optionality & Paired Hedge Research

**Account:** [@jhjhjhjhjh](https://polymarket.com/@jhjhjhjhjh?tab=activity)
**Ownership:** Demonstrated by PolyTutor
**Evidence:** [View ownership evidence](./ownership-evidence.md#jhjhjhjhjh)
**Public profile:** [Open Polymarket](https://polymarket.com/@jhjhjhjhjh?tab=activity)

**Observed public trading pattern** · **Status:** Public Activity Analysis

<p align="center">
  <img
    src="../../assets/trading-accounts/jhjhjhjhjh-paired-hedge.png"
    alt="Low-side optionality and paired-hedge family — illustrative diagram, not a reconstruction of every trade"
    width="100%"
  />
</p>

The diagram summarizes the research family. Exact thresholds and execution logic remain private.

The observable behavior resembles low-side price-dislocation research and paired-hedge structures. The owner situates this account in that research. This is **not** a reconstruction of private code and not a claim of guaranteed arbitrage. Not every position is claimed to follow one documented strategy.

> This page combines observable Polymarket activity with the owner’s research framing. It cannot establish the complete execution sequence, off-platform hedges, exact source code, private risk controls, or intent behind every trade.

---

## Source

Primary profile: [https://polymarket.com/@jhjhjhjhjh?tab=activity](https://polymarket.com/@jhjhjhjhjh?tab=activity)

At the time of observation, the public profile displayed approximately:

- 22,475 predictions
- $406.53 biggest win
- $120 positions value
- +$84.67 Past Day P/L

At the time of observation, the public profile displayed +$84.67 Past Day P/L. That snapshot is not daily expected earnings.

---

## Relation to PolyTutor research

The PolyTutor owner discloses this account as one used in trading research and experimentation around **low-side optionality and paired hedges**.

Observed public activity includes cheap-side entries and at least one equal-size two-sided BTC position. The owner’s explanation places the account near Price Dislocation and dual-side research. Inferred hedge intent is labeled in the table below. Exact private implementation is not published.

---

## Classification

**Low-Side Optionality + Paired Hedge**

The observable behavior resembles these research families:

- Price dislocation — [1¢ Buy — Ultra-Cheap Dislocation](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/one-cent-buy.md) and [Price Dislocation](../../bots/price-dislocation.md)
- Dual-side / hedge structures — [Low-Side Dual Reversion](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/low-side-dual-reversion.md), [Dual-Price Reversion](../../bots/dual-price-reversion.md), and conceptually [Dump & Hedge](../../bots/dump-hedge.md)

Dump & Hedge is an attributed public concept ([@the_smart_ape](https://x.com/the_smart_ape) / [SmartApe-Go](https://github.com/no-serve-people/SmartApe-Go)). This page does not imply that this account uses that algorithm or any exact handbook strategy.

---

## Strongest observed position

In one reviewed BTC 5-minute market the account publicly showed equal-sized exposure on both outcomes:

```text
DOWN
120 shares
average entry: 96¢

UP
120 shares
average entry: 3¢
```

Observed combined acquisition price:

```text
96¢ + 3¢ = 99¢
```

For equal quantities, a complete binary pair settles to $1 regardless of which side wins. Conceptually:

```text
Combined acquisition cost: ~99¢
Binary settlement value:   $1.00
```

For 120 matched shares:

```text
Approx. acquisition cost: $118.80
Settlement value:         $120.00
Gross difference:         ~$1.20
```

That difference is **before** fees, fill differences, timing, partial fills, execution costs, and unmatched quantities. It is not guaranteed net profit.

---

## Second observed pattern — very low price entries

The public profile also shows repeated purchases around 1¢, 2¢, and 3¢, primarily in short-duration BTC and other crypto Up/Down markets. Several displayed historical positions individually resolved to zero.

Representative public examples — not a complete trade list:

```text
2¢ × 250 shares
2¢ × ~300 shares
3¢ × 150 shares
3¢ × 120 shares
1¢ × 50 shares
```

A cheap-side print that later shows −100% on that row is not, by itself, the strategy’s market-level result.

---

## Individual leg P&L can be misleading

This is a central lesson of the account.

A cheap-side position might display:

```text
Entry: 2¢
Settlement: 0¢
P/L: -100%
```

That does not automatically tell us whether the overall strategy lost money. The same market may involve another outcome, a later hedge, partial exits, rebalancing, or other activity.

Account analysis should evaluate **market-level combined exposure**, not only isolated legs.

---

## Conceptual interpretation

A plausible system reading of the public pattern — not private-code reconstruction:

```text
Short-Duration Binary Market
            ↓
One Side Becomes Very Cheap
            ↓
Low-Side Entry
            ↓
Market Continues Moving
            ↓
Evaluate Opposite Side
            ↓
Can Matched Cost Become Attractive?
            ↓
      YES            NO
       ↓              ↓
Acquire Hedge    Maintain / Lose
       ↓          Small Premium
Matched Position
       ↓
Settlement
```

---

## Paired cost

For binary outcome tokens:

```text
YES settlement + NO settlement = $1
```

If equal quantities can be acquired such that:

```text
YES acquisition price + NO acquisition price < $1
```

the **matched** position has a positive gross settlement spread before costs.

Example from the publicly observed equal-size position:

```text
3¢ + 96¢ = 99¢
```

One attractive pair is not a standing opportunity. Combined cost can move above $1 before the second fill.

---

## Observed vs inferred

| Finding | Classification | Confidence |
| --- | --- | --- |
| Repeated 1–3¢ entries | Observed | High |
| Primarily short-duration crypto in reviewed examples | Observed | High |
| Equal quantities on both BTC outcomes in reviewed current position | Observed | High |
| Observed combined entry around 99¢ for that matched position | Observed | High |
| System exploits low-side optionality | Inferred | High |
| Some positions are later hedged | Inferred | High |
| System deliberately seeks combined cost below $1 | Inferred | Medium/High |
| Low-priced side is always entered first | Unknown | — |
| Exact entry price is fixed at 2¢ | Unknown | — |
| Exact hedge threshold is fixed at 96¢/97¢ | Unknown | — |
| Exact seconds-to-resolution condition | Unknown | — |
| Exact risk sizing algorithm | Unknown | — |

---

## Reference architecture

This is a PolyTutor reference architecture for the observed strategy family, not evidence of the trader's private implementation.

```text
Market Scanner
      ↓
Low-Price Detector
      ↓
Market / Resolution Validation
      ↓
Cheap-Side Position
      ↓
Position State Tracker
      ↓
Opposite-Side Price Monitor
      ↓
Combined-Cost Calculator
      ↓
Risk Validation
      ↓
Optional Hedge
      ↓
Settlement / Reconciliation
```

---

## Required state tracking

This family needs position state, not only a price scan:

```text
first leg price
first leg quantity

second leg price
second leg quantity

matched quantity
unmatched quantity

combined cost
remaining time

market resolution state
```

Without matched vs unmatched quantity, pair arithmetic is incomplete.

---

## Matched vs unmatched quantity

`Conceptual only.` Not an @jhjhjhjhjh fill.

```text
Cheap leg:  200 shares @ 2¢
Hedge leg:  120 shares @ 96¢
```

Only 120 shares are matched. Remaining 80 cheap-side shares still carry directional risk.

Checking `2¢ + 96¢ < $1` is insufficient unless quantity matching is handled.

---

## Main risks

- **Hedge never appears.** The opposite outcome may never reach an attractive price.
- **Cheap side expires worthless.** Reviewed historical rows include 1–3¢ positions that settled at zero.
- **Combined cost rises above $1.** Latency can remove the hedge.
- **Partial fills.** One leg may fill while the second does not.
- **Quantity mismatch.** Only matched size receives paired economics.
- **Fees.** A small gross spread can disappear after costs.
- **Resolution risk.** The market settles on its formal source, not another spot display.
- **Sudden reversal.** Late moves can change both legs quickly.

---

## Economic profile

The public pattern may combine two payoff ideas:

**Low-side optionality**

```text
Small premium
        ↓
Potentially large payout if rare outcome wins
```

**Pair completion**

```text
Cheap leg
   +
Opposite leg
   ↓
Potential matched cost < $1
```

That combination is more structured than “buy every 1¢ token.”

The profile displayed positive Past Day P/L at the time reviewed. The account has a publicly displayed biggest win of $406.53. Those figures are not a claim that the strategy is profitable, that 99¢ pairs always make money, or that the account earns $84/day.

---

## Engineering questions raised by this account

These are research questions, not published parameters.

- How should the system identify a legitimately interesting 1–3¢ outcome?
- How much capital can be allocated to cheap optionality?
- When should the opposite outcome be monitored for a hedge?
- What maximum combined cost is acceptable after fees?
- How should matched and unmatched quantities be separated?
- How should partial fills be handled?
- When should a hedge opportunity be abandoned?
- How should positions across consecutive 5-minute markets be managed?
- What happens when the book moves while the second order is being submitted?
- How should losses from unhedged cheap legs enter strategy-level expected value?

> **Direction alone is not an edge. Execution is part of the strategy.** A cheap print without a later matched fill is still a directional position.

---

## Related research

- [Price Dislocation](../../bots/price-dislocation.md)
- [Dual-Price Reversion](../../bots/dual-price-reversion.md)
- [Dump & Hedge](../../bots/dump-hedge.md) (attributed concept; not a claim about this account)
- [Crypto Short-Duration Markets](../../bots/crypto-short-duration.md)
- [Architecture](../../engineering/architecture.md)
- [BTC 5-Minute Markets — Direction vs Execution](../btc-5m-execution.md)
- Handbook: [1¢ Buy](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/one-cent-buy.md) · [Low-Side Dual Reversion](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/price-dislocation/low-side-dual-reversion.md) · [Dump & Hedge](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/strategies/hedging-arbitrage/dump-hedge.md)

← [Trading-accounts index](./README.md) · [Case studies](../README.md) · [Commercial README](../../README.md)
