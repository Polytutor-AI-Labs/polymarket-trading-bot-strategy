# Strategy Research

This directory is a bridge to the public [PolyTutor Strategy Handbook](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook).

The handbook documents **39 strategy pages across 14 families**. This commercial repository does not copy those pages. It explains which families exist and why they matter for systems work.

Read a family here, then open the handbook for provenance, assumptions, failure modes, and revalidation requirements.

> Status on every published handbook page is a research state: Historical / Revalidation Required, or External Research / Revalidation Required. Nothing here is labeled Production.

## Families

| Family | Focus | Commercial relevance |
| --- | --- | --- |
| Price Dislocation | Extreme binary prices versus settlement or complementary-pair value | High — 1¢, 99¢, dual-price / reversion |
| Hedging & Arbitrage | Multi-leg and multi-market structures | High — Dump & Hedge (attributed), cross-market research |
| Timing & Latency | Queue position and early order placement | Medium — execution and opening-window research |
| Position Sizing | How stake changes after wins, losses, or price events | Low as a product — overlay, not a standalone bot |
| Experimental | Technical-indicator experiments on binary token paths | Low — experimental only |
| Momentum | Token-native direction from the outcome’s own price and volume | High — short-duration crypto research |
| Oracle & Cross-Feed | Coinbase, Chainlink, PTB, and combinations | High as a family — do not treat each engine as a product |
| Binance Feed | Binance level, delta, squeeze, and hourly PTB research | High as a family — grouped under crypto short-duration |
| Polymarket CLOB | Ask relationships, depth, and paired maker structure | High — market-making and book research |
| Pattern & Predictor | Clock rules, forecasts, microstructure probability models | Low on this site — high research detail, weak product fit |
| Settlement Modeling | Settlement TWAP versus PTB | Medium — external public research; attribute |
| Sports Event Modeling | Live game state versus executable market price | High as a category — external public research; attribute |
| Model Fair Value | Statistical or stochastic model versus CLOB | Low on this site — includes source-negative public experiments |
| Copy Trading | Observed leader execution as a signal | High — architecture only; no wallets or private sizing |

Reserved handbook directories `strategies/failures/` and `strategies/orderbook/` currently have no published pages.

## Provenance

Do not mix these classes:

| Class | Meaning |
| --- | --- |
| Historical PolyTutor | Documented historical PolyTutor architecture. Still Research. |
| Private Historical Implementation | Later private project, educational architecture only. |
| External Public Research | Third-party public work, attributed. Not independently validated as profitable by PolyTutor. |

Dump & Hedge is an attributed concept ([@the_smart_ape](https://x.com/the_smart_ape) / [SmartApe-Go](https://github.com/no-serve-people/SmartApe-Go)). PolyTutor documented it; PolyTutor did not invent it.

## Handbook

- [Handbook README](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook)
- [Strategy catalog](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#strategy-catalog)
- [Strategy families](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#strategy-families)
- [Research origins](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook#research-origins)
- [Disclaimer](https://github.com/PolyTutor-Labs/polymarket-strategy-handbook/blob/main/DISCLAIMER.md)

Return to the [commercial README](../README.md) for systems, engineering, and contact.
