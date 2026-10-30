# CryptoDerivativesGuide

Crypto derivatives: futures, options, funding rates, and liquidation risk. A derivative is a contract whose value comes from another asset — you trade exposure to price movements without owning the underlying coin.

> This guide is educational only, not financial advice. Derivatives are the highest-risk products most retail traders can access, and most leveraged traders lose money. Do not trade derivatives with money you cannot afford to lose, and learn spot trading first.

## 1. What a derivative is, in plain language

Buying a coin on the spot market means you own it. Buying a derivative means you own a contract about it.

- If the coin's price rises, a contract betting on a rise gains value.
- If it falls, that contract loses value — often faster than the coin itself, because derivatives usually involve leverage.
- You never need to hold, store, or withdraw the underlying coin. You settle in cash (usually a stablecoin) based on the price difference.

Derivatives exist for hedging (protecting against price moves) and speculation (betting on them). In crypto, speculation dominates retail use — and speculation with leverage is where most losses happen.

## 2. Leverage: the amplifier

**Leverage** means controlling a larger position than your deposited capital (margin).

- With 10× leverage, $100 of margin controls a $1,000 position. A 10% price move in your favour doubles your margin; a 10% move against you wipes it out.
- With 100× leverage, a 1% move against you wipes you out.

**Liquidation** is the forced closure of your position when losses approach your margin. The exchange sells your position automatically to prevent losses exceeding your deposit. Liquidation is not a warning — it is an execution, often at the worst moment, with fees.

Three facts beginners underestimate:

1. **Liquidation price moves with leverage.** Higher leverage means a liquidation price very close to your entry. Normal market noise alone can liquidate a highly leveraged position.
2. **Fees compound.** Trading fees, funding payments, and liquidation fees all eat margin, pushing you closer to liquidation even if price moves sideways.
3. **Volatility is the norm in crypto.** A 10% intraday move that would be extraordinary in stocks is ordinary in crypto. Leverage that is survivable in stocks is lethal in crypto.

**Rule:** if you cannot state your liquidation price, your margin, and your maximum loss before entering, you are not ready to trade that derivative.

## 3. Perpetual futures (perps): the dominant crypto derivative

A **perpetual futures contract** is a futures contract with no expiry date. You can hold it indefinitely, as long as you maintain margin.

Key mechanics:

- **Long:** you profit if price rises. **Short:** you profit if price falls.
- **Mark price:** the exchange's fair price used for liquidations, based on spot prices across exchanges, not just the contract's own trading price. This prevents manipulation of a single market from liquidating everyone.
- **Funding rate:** a periodic payment between longs and shorts that keeps the perpetual's price close to spot (see section 5).
- **Margin modes:**
  - **Isolated margin:** each position has its own margin. Liquidation affects only that position.
  - **Cross margin:** all positions and balances share margin. A loss in one position can drag down others, but a winning position can support a losing one. Cross margin is riskier for beginners because one bad trade can take the whole account.

Perps are popular because they never expire and are simple to trade — which also makes them easy to overtrade.

## 4. Traditional futures and options

### Dated futures
A contract to buy or sell at a set price on a set future date. As expiry approaches, the futures price converges to the spot price. Dated futures are less common in retail crypto than perps, but they are the standard in traditional markets.

### Options
An option gives you the **right, but not the obligation**, to buy or sell at a set price (the **strike price**) before a set date (expiry).

- **Call option:** the right to buy. Profitable if price rises above the strike (plus the premium paid).
- **Put option:** the right to sell. Profitable if price falls below the strike (plus the premium paid).
- **Premium:** the price you pay for the option. If the option expires worthless, you lose the entire premium — but never more than that. This limited downside is options' main advantage over leveraged futures.
- **Implied volatility:** options are priced partly on expected future volatility. Buying options when volatility is high means paying a high premium, which requires a large price move just to break even.

Options are more complex than perps, with time decay (value erodes as expiry approaches), volatility effects, and strike selection. They are not "safer leverage" — they are a different, equally losable instrument that requires its own study.

## 5. Funding rates: the payment that keeps perps honest

Because perps never expire, their price could drift far from spot. The **funding rate** prevents this:

- When perps trade above spot (more longs than shorts), longs pay shorts a periodic fee.
- When perps trade below spot, shorts pay longs.
- The fee is usually paid every few hours, proportional to position size.

Consequences:

- **Holding a popular-side position costs money continuously.** A long position during a bullish frenzy can pay high funding for days, eroding profits even if price rises.
- **Funding rates signal positioning.** Extremely high positive funding means the market is heavily long and crowded — a condition that often precedes sharp reversals as longs are liquidated.
- **"Funding farming"** (collecting funding by holding the unpopular side) sounds like free money, but it requires holding price exposure on the other side, margin for both sides, and funding rates that can flip suddenly.

Always check the current funding rate and its history before opening a perp position, and factor expected funding into your profit calculation.

## 6. Liquidation cascades: how crashes accelerate

Liquidation is not just personal — it is systemic:

1. Price falls.
2. Leveraged long positions hit their liquidation prices.
3. Exchanges sell those positions automatically, pushing price lower.
4. Lower prices liquidate the next layer of longs.
5. The cascade continues until enough leverage is flushed out, or buyers step in.

This is why crypto crashes are so fast and so deep: leverage unwinds mechanically, without human decisions slowing it down. Short cascades work the same way in reverse during violent rallies.

**Implication:** your stop-loss may not save you in a cascade. In fast moves, prices can gap past your stop, exchanges can be congested, and liquidations can execute before your stop order is processed. Position size, not stop-losses alone, is your real protection.

## 7. Hedging: the legitimate use

Derivatives were invented for hedging, and hedging remains their most defensible use:

- A miner who will receive BTC next month can short BTC futures today, locking in today's price and removing price risk from their business.
- A holder who does not want to sell (for tax or conviction reasons) can short a smaller amount to offset a potential fall, reducing net exposure without selling.

Hedging still involves leverage, margin, funding, and liquidation risk on the hedge itself. A badly sized hedge can lose more than the position it was meant to protect. Hedging is risk management, not risk elimination.

## 8. Common mistakes

| Mistake | Better approach |
|---|---|
| Using maximum leverage | Start with 1–3×, if at all, and only after mastering spot |
| No liquidation price known before entering | Calculate liquidation price first; if it is within normal daily volatility, the position is too large or too leveraged |
| Ignoring funding rates | Check funding history; avoid holding crowded-side positions for long |
| Revenge trading after liquidation | Stop for the day; liquidations are often followed by emotional, larger losses |
| Cross margin with many positions | Isolated margin, so one bad trade cannot take the account |
| Trading derivatives to "recover" spot losses | Losses do not create an obligation to win them back; they create a reason to reduce risk |
| Assuming a stop-loss guarantees an exit price | In cascades and gaps, stops slip or fail; size positions so a failed stop is survivable |

## 9. A beginner derivatives learning path (if you insist)

1. Master spot trading for months, including risk management and journaling (see SpotTradingBasics).
2. Paper-trade derivatives (most exchanges offer testnets or demo accounts) for at least a month, tracking funding, fees, and liquidations.
3. Trade the smallest possible size with low leverage (1–3×), isolated margin, on a liquid pair.
4. Review every trade: was the liquidation price respected? Did funding eat the profit? Did emotion drive the entry or exit?
5. Only increase size after consistent, disciplined execution — not after a lucky win.

If any step feels boring or slow, that is the point. Derivatives reward discipline and punish impatience more than any other crypto product.

## 10. Frequently asked questions

**Can I lose more than I deposit in derivatives?**
On most retail exchanges, no — positions are liquidated before losses exceed margin, and exchanges have insurance funds for shortfalls. But in extreme events, insurance funds can be exhausted, and some platforms socialise losses across profitable traders (clawbacks). Read your exchange's terms; "cannot lose more than deposited" is a policy, not a law of physics.

**Are derivatives gambling?**
For most retail traders, functionally, yes: leveraged, short-term speculation with negative expected value after fees, funding, and MEV. Hedging and disciplined, low-leverage strategies are the exceptions, and they require expertise most beginners do not yet have.

**What is open interest?**
The total value of outstanding derivative positions. Rising open interest with rising prices suggests new money entering; rising open interest with falling prices suggests new shorts. Extremely high open interest relative to spot liquidity means a liquidation cascade has more fuel.

**Should I trade options instead of perps because losses are capped?**
Options cap losses at the premium, which is a real advantage. But premiums, time decay, and volatility pricing make options hard to profit from consistently. Capped loss is not the same as likely profit.

> Educational content only. This is not financial, investment, or tax advice.
