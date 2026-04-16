##readme = Trader Performance vs Market Sentiment
## Primetrade.ai — Data Science Intern Assignment

## Overview
Analysis of how Bitcoin market sentiment (Fear/Greed Index) relates to
trader behavior and performance on Hyperliquid DEX.



## Datasets
| Dataset | Rows | Columns |

| Bitcoin Fear/Greed Index | 2,644 | 4 |
| Hyperliquid Trader Data | 79,165 | 16 |
| Merged (after alignment) | 79,159 | 19 |



## Setup & How to Run
1. Upload both CSV files to Google Colab
2. Run all cells top to bottom
3. Charts auto-save as PNG files

Requirements:
- pandas, numpy, matplotlib, seaborn (all pre-installed in Colab)



## Methodology
1. Loaded and cleaned both datasets (dropped 1 missing row in trades)
2. Converted Timestamp IST to date, merged on date with Fear/Greed data
3. Created daily metrics per trader:
   - Daily PnL, win rate, trade count
   - Long/Short ratio, avg position size
4. Segmented traders into:
   - High Size vs Low Size (median split on avg_size_usd)
   - Frequent vs Infrequent (median split on total_trades)
   - Winners vs Losers (total_pnl > 0)
5. Analyzed performance and behavior across all sentiment categories

---

## Key Insights

### Insight 1: Fear Days Generate Higher PnL
- Extreme Fear avg daily PnL = $11,568
- Greed avg daily PnL = $4,446
- Fear days create buying opportunities from panic selling

### Insight 2: Panic Buying During Extreme Fear
- Long/Short ratio = 22.99 on Extreme Fear days
- Extreme Greed ratio = 4.94 (most balanced/short)
- Traders aggressively buy dips during crashes

### Insight 3: Greed = Worst Trading Outcomes
- Lowest win rate (0.31) on Greed days
- Most trader-days (352) but worst avg PnL
- FOMO-driven trading hurts performance

### Insight 4: Frequent Traders Have Edge During Fear
- Frequent traders: $10,358 avg PnL on Fear days
- Infrequent traders: $4,336 avg PnL on Fear days
- Experience and activity matter most during volatility

---

## Strategy Recommendations

### Strategy 1: Fear is Opportunity
During Fear / Extreme Fear days:
- Frequent traders should INCREASE trade frequency
- Target dip-buying with controlled position sizes
- Watch drawdown carefully (Extreme Fear = -$361 avg loss)

### Strategy 2: Greed = Step Back
During Greed / Extreme Greed days:
- ALL traders should REDUCE position sizes
- Avoid FOMO entries — win rate drops to 0.31
- Infrequent traders: sit out or take short positions
- Smart money already reducing long bias (L/S = 4.94)

---

## Output Charts
- chart1_performance_vs_sentiment.png
- chart2_behavior_vs_sentiment.png
- chart3_segments_vs_sentiment.png
- chart4_drawdown_longshort.png
- chart5_final_insights.png

