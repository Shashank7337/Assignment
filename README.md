# Hyperliquid Trader Performance vs. Bitcoin Market Sentiment Analysis

A quantitative study exploring the correlation between historical trader profitability (PnL), position sizing, and execution behaviors on **Hyperliquid** against the macro psychological states of the market tracked via the **Bitcoin Fear & Greed Index**. 

The core objective is to identify hidden trading patterns and extract data-driven indicators to optimize systematic trading algorithms.

---

## 📊 Executive Summary

This project aggregates and analyzes a massive high-frequency derivative trading dataset alongside historical sentiment metrics. By synchronizing precise execution timeframes with market sentiment boundaries, we uncovered critical insights into retail and institutional behavioral patterns on decentralized perpetual exchanges.

### Key Performance Highlights:
* **Total Cleaned Trade Records Analysed:** 211,218 executions.
* **Peak Profitability State:** *Extreme Greed* generated the highest average profit per trade at **$67.89**.
* **Contrarian High-Conviction State:** *Fear* regimes attracted the largest position clips, averaging **$7,816.11 USD** per trade.
* **Low Edge Regimes:** *Neutral* and *Extreme Fear* phases yielded the lowest structural payouts (~$34.00), signaling high-fee churn and market indecision.

---

## 💡 Key Analytical Insights & Market Nuances

The data rejects the simple assumption that traders lose money across the board when markets get greedy, instead highlighting a structural shift in risk management:

### 1. The Climax Momentum (Extreme Greed)
* **Average PnL:** $67.89 | **Average Size:** $3,112.25 | **Total Trades:** 39,992
* **Observation:** When the market enters *Extreme Greed*, profit-taking hits its maximum efficiency. Interestingly, average trade sizes drop significantly ($3,112.25). This indicates that institutional players or smart capital scale down their unit exposure but ride the high-momentum parabolic trends to capture premium payouts.

### 2. The Dip-Buying Alpha (Fear vs. Greed)
* **Average PnL:** $54.29 (*Fear*) vs. $42.74 (*Greed*)
* **Observation:** Traders capture fundamentally higher structural alpha during *Fear* phases than during standard *Greed* expansions. This strongly implies that liquidity providers and mean-reversion bots on Hyperliquid capture clean extensions by buying heavy pullbacks.

### 3. High Sizing Bias in Mid-Fear
* **Average Size:** $7,816.11 (Highest overall) | **Total Trades:** 61,837
* **Observation:** The largest overall deployment of capital occurs during mid-level *Fear*. This represents systematic scaling by large accounts adding to positions during localized liquidations or corrections, which directly correlates with robust baseline profitability ($54.29).

---

## 📈 Metric Distribution Summary Table

| Market Sentiment (Classification) | Average PnL ($) | Average Trade Size ($) | Total Executed Trades |
| :--- | :---: | :---: | :---: |
| **Extreme Greed** | **$67.89** | $3,112.25 | 39,992 |
| **Fear** | $54.29 | **$7,816.11** | **61,837** |
| **Greed** | $42.74 | $5,736.88 | 50,303 |
| **Extreme Fear** | $34.54 | $5,349.73 | 21,400 |
| **Neutral** | $34.31 | $4,782.73 | 37,686 |

---

## 🛠️ Data Strategy & Architecture

The script uses a custom pipeline to automatically handle cross-dataset anomalies:
1. **Case & Space Sanitation:** Strips trailing whitespaces and force-aligns text layers (`Classification` auto-mapping).
2. **Temporal Alignment:** Resolves cross-timezone execution granularities by scaling `Timestamp IST` (DD-MM-YYYY HH:MM) into a native ISO-compliant daily format (`%Y-%m-%d`) matching the Fear & Greed dataset.
3. **Robust Processing:** Coerces numerical string fields to handling empty values or processing noise without interrupting the algorithmic run.

---

## 🚀 Algorithmic Implementation Architecture

Based on the empirical findings of this analysis, an optimized automated execution framework should structure capital distribution
