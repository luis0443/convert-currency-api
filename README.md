# Convert Currency API

REST API to convert amounts between 100+ world currencies in real-time. One call. Instant results.

## Features

- Convert between 100+ currencies (USD, EUR, GBP, JPY, AUD, CAD, CHF, CNY, and more)
- Real-time exchange rates from authoritative financial data providers
- ISO 4217 standard currency codes
- 5,000 requests/month on free tier
- Example Response:
```json
{
  "source_currency": "USD",
  "target_currency": "JPY",
  "source_amount": 100.0,
  "target_amount": 15664.3
}
```

## Get API Key

Create an account at [omkar.cloud](https://www.omkar.cloud/auth/sign-up?redirect=/api-key) to get your API key, and use it in requests. 5000 requests are free every month.

## Quick Start

```bash
curl -X GET "https://convert-currency-api.omkar.cloud/convert?have=USD&want=JPY&amount=100" \
  -H "API-Key: YOUR_API_KEY"
```

```json
{
  "source_currency": "USD",
  "target_currency": "JPY",
  "source_amount": 100.0,
  "target_amount": 15664.3
}
```

## Installation

### Python

```bash
pip install requests
```

```python
import requests

response = requests.get(
    "https://convert-currency-api.omkar.cloud/convert",
    params={"have": "USD", "want": "JPY", "amount": 100},
    headers={"API-Key": "YOUR_API_KEY"}
)

data = response.json()
print(f"{data['source_amount']} {data['source_currency']} = {data['target_amount']} {data['target_currency']}")
```

### Node.js

```bash
npm install axios
```

```javascript
import axios from "axios";

const response = await axios.get("https://convert-currency-api.omkar.cloud/convert", {
    params: { have: "USD", want: "JPY", amount: 100 },
    headers: { "API-Key": "YOUR_API_KEY" }
});

console.log(`${response.data.source_amount} ${response.data.source_currency} = ${response.data.target_amount} ${response.data.target_currency}`);
```

## API Reference

### Endpoint

```
GET https://convert-currency-api.omkar.cloud/convert
```

### Headers

| Header | Required | Description |
|--------|----------|-------------|
| `API-Key` | Yes | API key from [omkar.cloud/api-key](https://www.omkar.cloud/api-key) |

### Parameters

All parameters are required.

| Parameter | Required | Description |
|-----------|----------|-------------|
| `have` | Yes | Source currency code (e.g., `USD`, `GBP`, `EUR`) |
| `want` | Yes | Target currency code (e.g., `JPY`, `AUD`, `CAD`) |
| `amount` | Yes | Amount to convert (e.g., `100`, `5000`, `49.99`) |

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| `source_currency` | string | Currency you're converting from |
| `target_currency` | string | Currency you're converting to |
| `source_amount` | float | Original amount sent |
| `target_amount` | float | Converted amount in target currency |

## Examples

### Convert USD to EUR

```python
response = requests.get(
    "https://convert-currency-api.omkar.cloud/convert",
    params={"have": "USD", "want": "EUR", "amount": 250},
    headers={"API-Key": "YOUR_API_KEY"}
)

data = response.json()
print(f"{data['source_amount']} USD = {data['target_amount']} EUR")
```

### Convert GBP to INR

```python
response = requests.get(
    "https://convert-currency-api.omkar.cloud/convert",
    params={"have": "GBP", "want": "INR", "amount": 500},
    headers={"API-Key": "YOUR_API_KEY"}
)

data = response.json()
print(f"{data['source_amount']} GBP = {data['target_amount']} INR")
```

### Convert EUR to JPY

```python
response = requests.get(
    "https://convert-currency-api.omkar.cloud/convert",
    params={"have": "EUR", "want": "JPY", "amount": 1000},
    headers={"API-Key": "YOUR_API_KEY"}
)

data = response.json()
print(f"{data['source_amount']} EUR = {data['target_amount']} JPY")
```

## Error Handling

```python
response = requests.get(
    "https://convert-currency-api.omkar.cloud/convert",
    params={"have": "USD", "want": "JPY", "amount": 100},
    headers={"API-Key": "YOUR_API_KEY"}
)

if response.status_code == 200:
    data = response.json()
elif response.status_code == 401:
    # Invalid API key
    pass
elif response.status_code == 429:
    # Rate limit exceeded
    pass
```

## Rate Limits

| Plan | Price | Requests/Month |
|------|-------|----------------|
| Free | $0 | 5,000 |
| Starter | $25 | 100,000 |
| Grow | $75 | 1,000,000 |
| Scale | $150 | 10,000,000 |

## Questions? We have answers.

Reach out anytime. We will solve your query within 1 working day.

[![Contact Us on WhatsApp about Convert Currency API](https://raw.githubusercontent.com/omkarcloud/assets/master/images/whatsapp-us.png)](https://api.whatsapp.com/send?phone=918178804274&text=I%20have%20a%20question%20about%20the%20Convert%20Currency%20API.)

[![Contact Us on Email about Convert Currency API](https://raw.githubusercontent.com/omkarcloud/assets/master/images/ask-on-email.png)](mailto:happy.to.help@omkar.cloud?subject=Convert%20Currency%20API%20Question)
