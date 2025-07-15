# Bollinger Band EMA Trading Strategy

A Pine Script v5 trading strategy that combines Bollinger Bands with Exponential Moving Average (EMA) to identify mean reversion opportunities in trending markets.

## Strategy Overview

This strategy identifies oversold conditions in uptrends and overbought conditions in downtrends by using Bollinger Bands for entry signals and EMA for trend direction confirmation.

## Trading Logic

### 📈 Buy Setup (Long Entry)

**Pre-conditions:**
1. Price must be below the 50 EMA (downtrend confirmation)
2. Price must be below the lower Bollinger Band (oversold condition)
3. Current candle closes above the lower Bollinger Band but remains below the middle Bollinger Band (mean reversion signal)

**Entry:** Buy at the open of the next candle after conditions are met

**Stop Loss:** 1.5 ATR below the entry price

**Take Profit:** Exit when price closes above the middle Bollinger Band

### 📉 Sell Setup (Short Entry)

**Pre-conditions:**
1. Price must be above the 50 EMA (uptrend confirmation)
2. Price must be above the upper Bollinger Band (overbought condition)
3. Current candle closes below the upper Bollinger Band but remains above the middle Bollinger Band (mean reversion signal)

**Entry:** Sell at the open of the next candle after conditions are met

**Stop Loss:** 1.5 ATR above the entry price

**Take Profit:** Exit when price closes below the middle Bollinger Band

## Key Features

- **No Pyramiding:** Only one position open at a time
- **Dynamic Stop Loss:** Uses ATR-based stops that adapt to market volatility
- **Visual Signals:** Clear buy/sell triangles on chart
- **Real-time Status:** Information table showing current market conditions
- **Built-in Alerts:** Notification system for setup conditions
- **Risk Management:** Automatic stop loss and take profit execution

## Input Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| Bollinger Band Length | 20 | Period for BB calculation |
| Bollinger Band Multiplier | 2.0 | Standard deviation multiplier |
| EMA Length | 50 | Period for trend-following EMA |
| ATR Length | 14 | Period for ATR calculation |
| ATR Multiplier | 1.5 | Multiplier for stop loss distance |

## Visual Elements

- **Blue Line:** 50 EMA (trend direction)
- **Red Line:** Upper Bollinger Band
- **Orange Line:** Middle Bollinger Band (20 SMA)
- **Green Line:** Lower Bollinger Band
- **Gray Shading:** Bollinger Band channel
- **Green Triangle Up:** Buy signal
- **Red Triangle Down:** Sell signal
- **Red Dashed Lines:** Active stop loss levels

## How to Use

1. **Installation:**
   - Copy the Pine Script code
   - Open TradingView Pine Script editor
   - Paste the code and add to chart

2. **Configuration:**
   - Adjust input parameters based on your trading style
   - Set up alerts for buy/sell signals
   - Configure position sizing in strategy settings

3. **Monitoring:**
   - Watch for signal triangles on chart
   - Monitor the information table for current conditions
   - Use alerts for real-time notifications

## Risk Management

- **Position Sizing:** Uses percentage of equity (default 100%)
- **Stop Loss:** Dynamic ATR-based stops (1.5 × ATR)
- **Take Profit:** Mean reversion to middle Bollinger Band
- **No Pyramiding:** Prevents overleveraging

## Best Practices

- **Timeframes:** Works best on 1H, 4H, and daily charts
- **Markets:** Suitable for forex, stocks, and crypto
- **Volatility:** ATR-based stops adapt to market conditions
- **Trend Context:** Only trades against short-term moves within larger trends

## Alerts Setup

The strategy includes built-in alert conditions:
- **Buy Setup Alert:** Triggers when all buy conditions are met
- **Sell Setup Alert:** Triggers when all sell conditions are met

To activate alerts:
1. Right-click on the chart
2. Select "Add Alert"
3. Choose the strategy and desired condition
4. Configure notification settings

## Performance Considerations

- **Backtesting:** Test on historical data before live trading
- **Market Conditions:** Performs best in trending markets with periodic pullbacks
- **Commissions:** Factor in spreads and commissions for realistic results
- **Slippage:** Consider market impact, especially for larger position sizes

## Limitations

- May produce false signals in ranging markets
- Requires clear trend direction for optimal performance
- Stop losses may be hit during high volatility periods
- Past performance doesn't guarantee future results

## Customization

The strategy can be modified by:
- Adjusting Bollinger Band parameters for different volatility
- Changing EMA period for trend sensitivity
- Modifying ATR multiplier for stop loss distance
- Adding additional filters or conditions

## Disclaimer

This strategy is for educational purposes only. Always:
- Test thoroughly before live trading
- Use proper risk management
- Consider your risk tolerance
- Consult with financial advisors if needed
- Never risk more than you can afford to lose

## Version History

- **v1.0:** Initial release with basic BB/EMA logic
- **v1.1:** Added ATR-based stop loss
- **v1.2:** Implemented no pyramiding rule
- **v1.3:** Added visual enhancements and alerts

---

*Built with Pine Script v5 for TradingView*
