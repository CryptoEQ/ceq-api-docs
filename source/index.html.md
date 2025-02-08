---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  # - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the CryptoEQ Reports API
---

# Introduction

Welcome to the CryptoEQ Reports API.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://ceq-reports-api.herokuapp.com/" \
  -H "x-api-key: YOUR_API_KEY"
```

> Make sure to replace `YOUR_API_KEY` with your API key.

CryptoEQ uses API keys to allow access to the API.

CryptoEQ expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

# Price Reports

## Get All Price Reports

```shell
curl "https://ceq-reports-api.herokuapp.com/price-reports" \
  -H "x-api-key: YOUR_API_KEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "5c732b7f4b20c45aeb49d63f",
    "name": "Ethereum",
    "ticker": "ETH",
    "icon": "https://cryptoeq-db.s3.amazonaws.com/16558499261041876703",
    "price": {
      "raw": 1121.64,
      "formatted": "$ 1,121.64"
    },
    "volume24HrUSD": 4933169654.6794195,
    "marketCapRaw": 135975009750.98589,
    "marketCap": "LRG",
    "signals": {
      "investor": "Strong Buy",
      "investorAlert": "\n        The Ethereum Investor Signal changed to a Buy as of June 22, 2022 12:37 AM. \n        A Buy signal indicates that the coin is oversold.",
      "dayTrader": "Strong Buy",
      "dayTraderAlert": "\n        The Ethereum Day Trader Signal changed to a Strong Buy as of June 22, 2022 12:37 AM. \n        A Strong Buy signal indicates that the coin is very oversold."
    }
  },
  {
    "id": "5c732c664b20c45aeb49d640",
    "name": "Bitcoin",
    "ticker": "BTC",
    "icon": "https://cryptoeq-db.s3.amazonaws.com/16558327092896220515",
    "price": {
      "raw": 20681.5,
      "formatted": "$ 20,681.5"
    },
    "volume24HrUSD": 8307843632.120352,
    "marketCapRaw": 394425676137.5,
    "marketCap": "LRG",
    "signals": {
      "investor": "Hold",
      "investorAlert": "\n        The Bitcoin Investor Signal changed to a Hold as of June 22, 2022 12:37 AM. \n        A Hold signal indicates that the coin is in a no trade pattern.",
      "dayTrader": "Strong Buy",
      "dayTraderAlert": "\n        The Bitcoin Day Trader Signal changed to a Strong Buy as of June 22, 2022 12:37 AM. \n        A Strong Buy signal indicates that the coin is very oversold."
    }
  },
  ...
]
```

This endpoint retrieves all Price Reports.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/price-reports`

## Get a Specific Price Report

```shell
curl "https://ceq-reports-api.herokuapp.com/price-reports/eth" \
  -H "x-api-key: YOUR_API_KEY"
```
> The above command returns JSON structured like this:

```json
{
  "id": "5c732b7f4b20c45aeb49d63f",
  "name": "Ethereum",
  "ticker": "ETH",
  "icon": "https://cryptoeq-db.s3.amazonaws.com/16558499261041876703",
  "price": {
    "raw": 1116.44,
    "formatted": "$ 1,116.44"
  },
  "volume24HrUSD": 4971782039.053005,
  "marketCapRaw": 135344620276.01607,
  "marketCap": "LRG",
  "signals": {
    "investor": "Strong Buy",
    "investorAlert": "\n        The Ethereum Investor Signal changed to a Buy as of June 22, 2022 12:57 AM. \n        A Buy signal indicates that the coin is oversold.",
    "dayTrader": "Strong Buy",
    "dayTraderAlert": "\n        The Ethereum Day Trader Signal changed to a Strong Buy as of June 22, 2022 12:57 AM. \n        A Strong Buy signal indicates that the coin is very oversold."
  }
}
```

This endpoint retrieves a specific Price Report.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/price-reports/<TICKER>`
### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| TICKER    | The ticker of the coin to get    |




# Core Reports
## Get all CORE Reports

```shell
curl "https://ceq-reports-api.herokuapp.com/core-reports" \
  -H "x-api-key: YOUR_API_KEY"
```
> The above command returns JSON structured like this:

```json
[
  {
    "id": "e5283357-338b-425f-8cb0-0597e45f91ec",
    "title": "CORE Report: XRP (Abridged)"
  },
  {
    "id": "feb68dbd-d5ac-4383-a27b-d7cea87e3f59",
    "title": "CORE Report: Uniswap (Abridged)"
  },
  {
    "id": "581fa578-6067-4c53-8f92-77d09e548637",
    "title": "CORE Report: REP (Abridged)"
  },
  ...
]
```

This endpoint retrieves a list of CORE Reports.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/core-reports`

## Get a single CORE Report

```shell
curl "https://ceq-reports-api.herokuapp.com/core-reports/<ID>" \
  -H "x-api-key: YOUR_API_KEY"
```
> The above command returns JSON structured like this:

```json
{
 "_id": "e5283357-338b-425f-8cb0-0597e45f91ec",
  "title": "CORE Report: XRP (Abridged)",
  "abridged": true,
  "importantLinks": "<ul><li><a href=\"https://www.google.com/url?q=https://ripple.com/files/ripple_consensus_whitepaper.pdf&amp;sa=D&amp;ust=1591486264813000\">Whitepaper</a></li><li><a href=\"https://www.google.com/url?q=https://ripple.com/&amp;sa=D&amp;ust=1591486264813000\">Website</a></li><li><a href=\"https://www.google.com/url?q=https://github.com/ripple&amp;sa=D&amp;ust=1591486264814000\">Github</a></li><li><a href=\"https://www.google.com/url?q=https://xrpscan.com/&amp;sa=D&amp;ust=1591486264814000\">Block explorer</a></li><li><a href=\"https://www.google.com/url?q=https://xrpcharts.ripple.com/%23/graph&amp;sa=D&amp;ust=1591486264814000\">Charts</a></li><li><a href=\"https://www.google.com/url?q=https://www.reddit.com/r/Ripple/&amp;sa=D&amp;ust=1591486264814000\">Reddit</a></li><li><a href=\"https://www.google.com/url?q=https://xrpcommunity.blog/&amp;sa=D&amp;ust=1591486264814000\">Blog</a></li><li><a href=\"https://www.google.com/url?q=https://cointelegraph.com/ripple-101/ripple-xrp-wallets-for-beginners%23desktopweb-wallets&amp;sa=D&amp;ust=1591486264815000\">Wallet</a>-&nbsp;<a href=\"https://www.google.com/url?q=https://shop.ledger.com/products/ledger-nano-s?r%3D4d117270ceaf%26tracker%3DMY_TRACKER&amp;sa=D&amp;ust=1591486264815000\">Ledger</a>&nbsp;and&nbsp;<a href=\"https://www.google.com/url?q=https://trezor.io/?offer_id%3D12%26aff_id%3D2220&amp;sa=D&amp;ust=1591486264815000\">TREZOR</a></li><li>Where to buy?&nbsp;<a href=\"https://www.google.com/url?q=http://coinbase-consumer.sjv.io/Anym7&amp;sa=D&amp;ust=1591486264815000\">Coinbase</a></li></ul>",
  "analysts": [
    {
      "value": "CryptoEQ Fundamentals Team",
      "format": "basic_html",
      "processed": "CryptoEQ Fundamentals Team"
    }
  ],
  "authors": [
    {
      "value": "Cameron Pick",
      "format": "basic_html",
      "processed": "Cameron Pick"
    }
  ],
  "economics": "",
  "networkEffect": "",
  "overview": "",
  "pubLocation": "Houston, TX",
  "regulation": "",
  "roadmap": "",
  "strenghts": "",
  "team": "",
  "technology": "",
  "userExp": "",
  "vulnerables": "",
  "weaknesses": "",
  "currencyName": "XRP",
  "useCase": "",
  "created": "2020-06-06T22:32:53+00:00",
  "changed": "2022-04-28T17:26:02+00:00",
  "path": "/xrp-abridged",
  "rating": "Deficient",
  "ratingDesc": "XRP received a Deficient CORE Rating. "
}
```

This endpoint retrieves a single CORE Report.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/core-reports/<ID>`

# Sentiment Reports

## Get all Sentiment Reports

```shell
curl "https://ceq-reports-api.herokuapp.com/sentiment-reports" \
  -H "x-api-key: YOUR_API_KEY"
```
> The above command returns JSON structured like this:

```json
[
  {
    "name": "Ethereum",
    "ticker": "ETH",
    "sentiment": "positive",
    "sentimentDesc": "The current Sentiment for Ethereum is positive based on recent news and discussions on social media."
  },
  {
    "name": "Bitcoin",
    "ticker": "BTC",
    "sentiment": "positive",
    "sentimentDesc": "The current Sentiment for Bitcoin is positive based on recent news and discussions on social media."
  },
  ...
]
```

This endpoint retrieves a list of Sentiment Reports.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/sentiment-reports`

## Get a single Sentiment Report

```shell
curl "https://ceq-reports-api.herokuapp.com/sentiment-reports/<TICKER>" \
  -H "x-api-key: YOUR_API_KEY"
```
> The above command returns JSON structured like this:

```json
{
  "name": "Ethereum",
  "ticker": "ETH",
  "sentiment": "positive",
  "sentimentDesc": "The current Sentiment for Ethereum is positive based on recent news and discussions on social media."
}
```

This endpoint retrieves a single Sentiment Report.

### HTTP Request

`GET https://ceq-reports-api.herokuapp.com/sentiment-reports/<TICKER>`

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| TICKER    | The ticker of the coin to get    |
