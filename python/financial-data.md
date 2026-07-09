# Financial data

## Financial data

Quadratic includes a built-in financial data API for Python — no API keys or external accounts required. Use `q.financial` to pull stock prices, company fundamentals, financial statements, news, and technical indicators straight into your sheet.

### Quick start

All methods are async — use `await`:

```python
# Daily stock prices as a DataFrame
prices = await q.financial.stock_prices('AAPL', start='2025-01-01')
prices
```

```python
# Latest real-time quote
quote = await q.financial.realtime_price('NVDA')
quote['last_price']
```

### Available methods

| Method                                                                    | Returns                                                                                                                     |
| ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `stock_prices(identifier, start, end, frequency)`                         | Historical prices (DataFrame)                                                                                               |
| `realtime_price(identifier)`                                              | Real-time quote (dict)                                                                                                      |
| `intraday_prices(identifier)`                                             | Intraday bars                                                                                                               |
| `company(identifier)`                                                     | Company profile (dict)                                                                                                      |
| `company_news(identifier, start_date)`                                    | Recent news                                                                                                                 |
| `financial_statements(identifier, statement, fiscal_year, fiscal_period)` | Income statement, balance sheet, or cash flow (DataFrame)                                                                   |
| `dividends(identifier)`                                                   | Dividend history                                                                                                            |
| `splits(identifier)`                                                      | Split history                                                                                                               |
| `data_point(identifier, tag)`                                             | Single numeric metric                                                                                                       |
| `data_point_text(identifier, tag)`                                        | Single text metric                                                                                                          |
| `historical_data(identifier, tag)`                                        | Metric time series                                                                                                          |
| `technical_indicator(identifier, indicator, ...)`                         | Technical indicators (DataFrame): `sma`, `rsi`, `macd`, `bollinger_bands`, `vwap`, `atr`, `adx`, `obv`, `stochastic`, `cci` |

{% hint style="info" %}
Prefer adjusted prices for historical analysis — they account for splits and dividends.
{% endhint %}

### Prefer formulas?

The Excel-compatible `STOCKHISTORY` function retrieves historical prices without writing Python:

```
=STOCKHISTORY("MSFT", "2025-01-01", "2025-12-31")
```

### Rate limits

Financial data requests are limited to 500 requests per team per minute. If your team hits the limit, requests briefly pause and a notification appears in the app.
