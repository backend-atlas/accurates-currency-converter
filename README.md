AccuRates is a currency conversion API for developers building user-facing products that handle multi-currency amounts programmatically.

It’s designed for apps where exchange rates directly affect pricing, balances, or user trust, not for accounting, reporting, or finance-owned rate systems.

AccuRates delivers globally sourced Forex data refreshed every 60 seconds, with support for live rates, historical datasets, time-series analytics, bulk conversions, and multi-currency matrices, all through simple REST endpoints optimized for production use.

If your product needs consistent, up-to-date exchange rates inside its core logic, without requiring a dedicated finance team, AccuRates is built for that use case.

## 🌟 Quick Start

```
import requests

response = requests.get( 
    "https://currencyconverter9.p.rapidapi.com/convert", 
    params={"from": "USD", "to": "EUR", "amount": "100"}, 
    headers={"x-rapidapi-key": "YOUR_API_KEY"} 
) 

print(response.json())
```

## 🌟 Key Features
##### ⚡ 60-Second Live Updates

All exchange rates are refreshed every 60 seconds for maximum accuracy.

##### 🌍 160+ Supported Currencies

Wide coverage across all major, minor, and exotic global currencies.

##### 📊 Multi-Source Aggregated Data

Aggregated data from 20+ trustworthy central banks and global financial institutions for unmatched accuracy:

##### 📚 55 Years of Historical Data

Historical rates available for most currency pairs back to the 1960s.

##### 📅 Time-Series Endpoints

Retrieve continuous datasets for building in-app charts, trends, and historical views.

##### 🔗 Bulk & Matrix Conversion

Convert multiple currencies, generate matrices, and fetch multi-pair sets in a single request.

##### 🔐 Bank-Level Security

Requests are secured with: HTTPS (SHA-256 SSL), API key authentication, Enterprise-grade request sanitization

##### 🔁 Smart Fallback System

If a data provider is down or rate-limits, AccuRates seamlessly switches to another source.

##### 🔎 Currency Metadata

Fetch standardized currency lists, ISO codes, symbols, and metadata.

##### 📘 Developer-Friendly API

Minimal learning curve, consistent JSON responses, easy integration.

## 📡 Data Sources

AccuRates aggregates data from trustworthy global institutions for unmatched accuracy:

##### Central & National Banks
- **[European Central Bank](https://www.ecb.europa.eu/home/html/index.en.html)**
- **[National Bank of Romania](http://www.bnr.ro/)**
- **[Central Bank of the Republic of Turkey](http://www.tcmb.gov.tr/)**
- **[Central Bank of the Czech Republic](https://www.cnb.cz/)**
- **[Central Bank of Russia](https://cbr.ru/)**
- **[Bulgarian National Bank](http://bnb.bg/)**

##### European & Global Providers
- **[Fixer](https://fixer.io/)** 
- **[Currency Layer](https://currencylayer.com/)**
- **[Open Exchange Rates](https://openexchangerates.org/)**
- **[Quodd](https://www.quodd.com/)**
- **[xChange](https://xchangeapi.com/)**

##### Additional Data Providers
- **[1Forge](https://1forge.com/)**
- **[Currency Data Feed](https://currencydatafeed.com/)**
- **[WebserviceX](http://www.webservicex.net/)**
- **[Currency Converter API](https://www.currencyconverterapi.com/)**

(Data is aggregated, blended, normalized, and validated before serving.
Rates are intended for application use, not official financial reporting or regulatory purposes.)

## 🌟 Why Developers Choose AccuRates?

##### Accuracy & Reliability
- Bank-grade multi-source data (20+ providers)
- 60-second refresh interval
- ~100 ms average response times (globally optimized)
- Smart fallback system ensures uptime

##### Coverage
- 160+ currencies
- 55 years of historical data
- Time-series & daily historical endpoints
- Bulk & matrix conversion (rare feature among competitors)

##### Developer Experience
- Simple, powerful REST API
- Consistent JSON responses
- Fast integration & predictable pricing for developers
- Developer-first documentation

## 📌 Try AccuRates API

You can try AccuRates API **[here](https://rapidapi.com/TockaAyman/api/currencyconverter9)**  

## 🔐 Authentication

Requests are authenticated using the standard RapidAPI API key header: `x-rapidapi-key: YOUR_API_KEY`

## 🔧 Available Endpoints

Below is the full list of available REST endpoints.

##### 📌 Live Rates
- GET `/fetch-one` → Fetch a single currency exchange rate, from and to any supported currency.
- GET `/fetch-all` → Fetch all available currency rates
- GET `/fetch-multi` → Fetch multiple currency rates at once

##### 📌 Conversions (Single & Advanced Multi-Currency)
- GET `/convert` → Convert an amount of one currency into another currency (start here)
- GET `/fetch-many-to-one` → Fetch a set of many source currency rates to a single target currency (inverse of /fetch-multi). Midpoint spot rates. 
- GET /`fetch-matrix` → Fetch a matrix of multiple from/to currency pairs. Midpoint spot rates. 

##### 📌 Metadata
- GET `/currencies` → Fetch a list of supported currencies

##### 📌 Historical & Time-Series
- GET `/historical` → Fetch exchange rates for a date in the past
- GET `/time-series` → Fetch a time-series dataset of currency rates for the specified interval (only daily supported currently)

## 🧪 Example Usage
##### 1. Convert Between Two Currencies

`GET https://currencyconverter9.p.rapidapi.com/convert?from=USD&to=EUR&amount=100`

Response

```json
{
    "base": "USD",
    "amount": 100,
    "result": {
        "EUR": 86.86,
        "rate": 0.8686
    },
    "ms": 13
}
```

##### 2. Fetch a Live Exchange Rate (USD → EUR)
`GET https://currencyconverter9.p.rapidapi.com/fetch-one?from=USD&to=EUR`

Response

```json
{
    "base": "USD",
    "result": {
        "EUR": 0.8686
    },
    "updated": "2025-11-21 23:57:22",
    "ms": 7
}
```

##### 3. Fetch Multiple Currency Pairs
`GET https://currencyconverter9.p.rapidapi.com/fetch-multi?from=EUR&to=GBP,CAD`

Response
```json
{
    "base": "EUR",
    "results": {
        "GBP": 0.87901,
        "CAD": 1.62364
    },
    "updated": "2025-11-21 23:58:42",
    "ms": 7
}
```

##### 4. Fetch Historical Rate
`GET https://currencyconverter9.p.rapidapi.com/historical?date=1991-10-23&from=EUR&to=GBP,CAD`

Response

```json
{
    "date": "1991-10-23",
    "base": "EUR",
    "results": {
        "CAD": 1.35327,
        "GBP": 0.70404
    },
    "ms": 7
}
```

##### 5. Time-Series Example
`GET https://currencyconverter9.p.rapidapi.com/time-series?start=1991-11-23&end=1991-11-23&from=EUR&to=GBP`

Reponse

```json
{
    "start": "1991-11-23",
    "end": "1991-11-23",
    "interval": "P1D",
    "base": "EUR",
    "results": {
        "GBP": {
            "1991-11-23": 0.7117
        }
    },
    "ms": 8
}
```

## 🛑 Error Codes

Below are the standard response codes returned by AccuRates API, along with explanations to help you quickly identify and resolve issues.

##### ✔️ 200 → Success

The request was processed successfully.

A valid response body with data will be returned.

##### ⚠️ 400 → Bad Request

Your request parameters are missing, invalid, or malformed.

**Common causes:** 
- Missing required query parameters
- Invalid currency codes
- Non-numeric values for numeric fields

#####  🔒 401 → Not Authorized

Your API key is missing, invalid, incorrectly formatted, or it's valid but it does not have permission to access this resource.

**Verify that:**

- You are including the correct `x-rapidapi-key` header
- Your subscription plan is active
- You are not trying to access a restricted endpoint on your plan

##### 📭 404 → Not Found

(Only applies to the `/historical` endpoint)

We do not have historical rates for the requested date and currency pair

Ensure the date is within the available 55-year historical range, and that both currencies are supported.

##### 🚧 429 → Rate Limit Exceeded

You sent too many requests within your plan’s allowed timeframe.

**Solutions:**
- Add a delay / retry logic
- Upgrade your plan for higher limits

### 💡 Designed For

- User-facing applications that display prices or balances in multiple currencies
- Products where exchange rate correctness affects user trust or UX
- SaaS, marketplaces, and consumer apps handling international users
- Developers who need programmatic FX inside product logic (not reports)

### 🚫 Not Intended For

- Accounting, ERP, or financial reporting systems
- Official tax, audit, or regulatory calculations
- Manual rate lookup or spreadsheet-based workflows
- Finance-department–owned FX pipelines

### 📘 OpenAPI / Swagger Documentation

You can view the full interactive API documentation here: **[Swagger UI Viewer](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/tayman12/accurates-currency-converter/main/openapi.yaml)**  

Or download the specification directly here **[Swagger File](https://raw.githubusercontent.com/tayman12/accurates-currency-converter/main/openapi.yaml)**

## 📮 Support / Contact

Developer support available for all paid plans through:

- RapidAPI Messaging
- Email
  
