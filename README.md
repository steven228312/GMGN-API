# GMGN-API
This is the API for the GMGN.AI platform that allows users to view the trending tokens by various criteria.

`https://gmgn.ai/defi/quotation/v1/rank/{chain}/swaps/{time_period}?&orderby={criteria}&direction={direction}&filters[]=not_honeypot&filters[]=verified&filters[]=renounced`

## Table of Contents
- [Parameters](#parameters)
- [Usage Examples](#usage-examples)
- [API Response Structure](#api-response-structure)
- [Response Field Explanations](#response-field-explanations)
- [Code Examples](#code-examples)
- [Rate Limits](#rate-limits)
- [Error Handling](#error-handling)

## Parameters

### `{chain}`
- `eth`: Ethereum
- `bsc`: Binance Smart Chain
- `base`: Base
- `sol`: Solana
- `tron`: Tron

### `{time_period}`
- `1m`: 1 minute
- `5m`: 5 minutes
- `1h`: 1 hour
- `6h`: 6 hours
- `24h`: 24 hours

### `{criteria}`
- `open_timestamp`: Trading tokens by the time they were added to the platform (`Age`)
- `liquidity`: Trading tokens by the liquidity they have (`Liq`)
- `marketcap`: Trading tokens by the market cap they have (`MC`)
- `bluechip_owner_percentage`: Trading tokens by the bluechip score they have (`BlueChip`)
- `holder_count`: Trading tokens by the number of holders they have (`Holders`)
- `smartmoney`: Trading tokens by the number of smart transactions they have (`SmartTxn`)
- `swaps`: Trading tokens by the number of transactions they have in the last 24 hours (`24h TXs`)
- `volume`: Trading tokens by the volume they have in the last 24 hours (`24h Volume`)
- `price`: Trading tokens by the price they have (`Price`)
- `change1m`: Trading tokens by the price change in the last 1 minute (`1m%`)
- `change5m`: Trading tokens by the price change in the last 5 minutes (`5m%`)
- `change1h`: Trading tokens by the price change in the last 1 hour (`1h%`)

### `{direction}`
- `asc`: Sort the trending tokens by ascending order
- `desc`: Sort the trending tokens by descending order

### Filters
- `not_honeypot`: Excludes honeypot tokens
- `verified`: Only verified tokens
- `renounced`: Only tokens with renounced ownership

## Usage Examples

### Get trending tokens on Ethereum by transaction count (6h)
```
https://gmgn.ai/defi/quotation/v1/rank/eth/swaps/6h?&orderby=swaps&direction=desc&filters[]=not_honeypot&filters[]=verified&filters[]=renounced
```

### Get tokens with highest market cap on Solana (24h)
```
https://gmgn.ai/defi/quotation/v1/rank/sol/swaps/24h?&orderby=marketcap&direction=desc&filters[]=not_honeypot&filters[]=verified&filters[]=renounced
```

### Get newest tokens on Base (1h)
```
https://gmgn.ai/defi/quotation/v1/rank/base/swaps/1h?&orderby=open_timestamp&direction=desc&filters[]=not_honeypot&filters[]=verified&filters[]=renounced
```

## API Response Structure

The API returns a JSON response with the following structure:

    ```json
    {
        "code": 0,
        "msg": "success",
        "data": {
            "rank": [
                {
                    "id": 768610,
                    "chain": "eth",
                    "address": "0xecca809227d43b895754382f1fd871628d7e51fb",
                    "symbol": "LANLAN",
                    "logo": "https://gmgn.ai/external-res/dd62c13d6d5052c95f71f91dca4f17fb.webp",
                    "price": 0.0026437156,
                    "price_change_percent": -5.8824727,
                    "price_change_percent1m": 0.70290878,
                    "price_change_percent5m": 0.53128744,
                    "price_change_percent1h": 2.0284031,
                    "swaps": 1725,
                    "volume": 1743889.7,
                    "liquidity": 534762.209641217,
                    "market_cap": 23499694,
                    "call_number": 0,
                    "smart_buy_24h": 88,
                    "smart_sell_24h": 3,
                    "pool_creation_timestamp": 1747707203,
                    "open_timestamp": 1747708259,
                    "holder_count": 2078,
                    "total_supply": 8888888888,
                    "buy_tax": "0.00000000000000000000",
                    "sell_tax": "0.00000000000000000000",
                    "is_honeypot": 0,
                    "is_open_source": 1,
                    "renounced": 1,
                    "twitter_username": "LanLanCoin",
                    "website": "https://www.lanlancat.com/",
                    "telegram": "https://t.me/LANLANCOIN",
                    "buys": 860,
                    "sells": 865,
                    "initial_liquidity": null,
                    "twitter_rename_count": 0,
                    "creator_created_inner_count": 0,
                    "creator_created_open_count": 0,
                    "creator_created_open_ratio": 0,
                    "lockInfo": {
                    "isLock": true,
                    "lockDetail": [
                        {
                        "percent": "0.9999999999999996645898033582610356264094",
                        "pool": "burnt🔥",
                        "isBlackHole": true
                        }
                    ],
                    "lockTag": [
                        "blackhole"
                    ],
                    "lockPercent": 0.95,
                    "leftLockPercent": 0.05
                    },
                    "creator_close": false,
                    "rat_trader_amount_rate": 0,
                    "creator": "",
                    "cto_flag": 0,
                    "bluechip_owner_percentage": 0.0288739172281039,
                    "rug_ratio": null,
                    "sniper_count": 4,
                    "smart_degen_count": 3,
                    "renowned_count": 2
                },
                {
                    "id": 770605,
                    "chain": "eth",
                    "address": "0x0f7dc5d02cc1e1f5ee47854d534d332a1081ccc8",
                    "symbol": "ZEUS",
                    "logo": "https://gmgn.ai/external-res/f6e7cb93dfe7d7782c4a938d7feef367.webp",
                    "price": 9.9891725e-9,
                    "price_change_percent": 49.093504,
                    "price_change_percent1m": 0.58993888,
                    "price_change_percent5m": -2.3838824,
                    "price_change_percent1h": -6.7349699,
                    "swaps": 1004,
                    "volume": 1151441.9,
                    "liquidity": 237281.99224447,
                    "market_cap": 4202345,
                    "call_number": 0,
                    "smart_buy_24h": 10,
                    "smart_sell_24h": 5,
                    "pool_creation_timestamp": 1747863815,
                    "open_timestamp": 1747864319,
                    "holder_count": 1054,
                    "total_supply": 420690000000000,
                    "buy_tax": "0.00000000000000000000",
                    "sell_tax": "0.00000000000000000000",
                    "is_honeypot": 0,
                    "is_open_source": 1,
                    "renounced": 1,
                    "twitter_username": "zeuscoineth",
                    "website": "https://www.zeuscoin.vip/",
                    "telegram": "https://t.me/zeuscoincommunity",
                    "buys": 556,
                    "sells": 448,
                    "initial_liquidity": null,
                    "twitter_rename_count": 0,
                    "creator_created_inner_count": 0,
                    "creator_created_open_count": 0,
                    "creator_created_open_ratio": 0,
                    "lockInfo": {
                    "isLock": true,
                    "lockDetail": [
                        {
                        "percent": "0.9999999999999999984582324325863841744381",
                        "pool": "burnt🔥",
                        "isBlackHole": true
                        }
                    ],
                    "lockTag": [
                        "blackhole"
                    ],
                    "lockPercent": 0.95,
                    "leftLockPercent": 0.05
                    },
                    "creator_close": false,
                    "rat_trader_amount_rate": 0,
                    "creator": "",
                    "cto_flag": 0,
                    "bluechip_owner_percentage": 0.0521821631878558,
                    "rug_ratio": null,
                    "sniper_count": 7,
                    "smart_degen_count": 4,
                    "renowned_count": 1
                },
                ...
            ]
        }
      ```

If you wanna see the whole response, please click [here](./data/eth_6h_txnNumber.json)

## Response Field Explanations

| Field | Type | Description |
|-------|------|-------------|
| `id` | Integer | Unique token identifier |
| `chain` | String | Blockchain network |
| `address` | String | Token contract address |
| `symbol` | String | Token symbol |
| `logo` | String | Token logo URL |
| `price` | Float | Current token price |
| `price_change_percent` | Float | 24h price change percentage |
| `price_change_percent1m` | Float | 1-minute price change |
| `price_change_percent5m` | Float | 5-minute price change |
| `price_change_percent1h` | Float | 1-hour price change |
| `swaps` | Integer | Number of swaps in time period |
| `volume` | Float | Trading volume |
| `liquidity` | Float | Available liquidity |
| `market_cap` | Float | Market capitalization |
| `smart_buy_24h` | Integer | Smart money buy transactions (24h) |
| `smart_sell_24h` | Integer | Smart money sell transactions (24h) |
| `holder_count` | Integer | Number of token holders |
| `total_supply` | Integer | Total token supply |
| `buy_tax` | String | Buy transaction tax percentage |
| `sell_tax` | String | Sell transaction tax percentage |
| `is_honeypot` | Integer | Honeypot flag (0 = safe, 1 = honeypot) |
| `is_open_source` | Integer | Open source flag |
| `renounced` | Integer | Ownership renounced flag |
| `buys` | Integer | Number of buy transactions |
| `sells` | Integer | Number of sell transactions |
| `bluechip_owner_percentage` | Float | Percentage of bluechip holders |
| `sniper_count` | Integer | Number of sniper transactions |
| `lockInfo` | Object | Liquidity lock information |

## Code Examples

### JavaScript/Node.js
```javascript
async function getTrendingTokens(chain = 'eth', timePeriod = '6h', orderBy = 'swaps') {
    const url = `https://gmgn.ai/defi/quotation/v1/rank/${chain}/swaps/${timePeriod}?&orderby=${orderBy}&direction=desc&filters[]=not_honeypot&filters[]=verified&filters[]=renounced`;
    
    try {
        const response = await fetch(url);
        const data = await response.json();
        
        if (data.code === 0) {
            return data.data.rank;
        } else {
            throw new Error(data.msg);
        }
    } catch (error) {
        console.error('Error fetching trending tokens:', error);
        return null;
    }
}

// Usage
getTrendingTokens('eth', '6h', 'volume').then(tokens => {
    console.log('Top trending tokens:', tokens);
});
```

### Python
```python
import requests

def get_trending_tokens(chain='eth', time_period='6h', order_by='swaps'):
    url = f"https://gmgn.ai/defi/quotation/v1/rank/{chain}/swaps/{time_period}"
    params = {
        'orderby': order_by,
        'direction': 'desc',
        'filters[]': ['not_honeypot', 'verified', 'renounced']
    }
    
    try:
        response = requests.get(url, params=params)
        data = response.json()
        
        if data['code'] == 0:
            return data['data']['rank']
        else:
            raise Exception(data['msg'])
    except Exception as e:
        print(f"Error fetching trending tokens: {e}")
        return None

# Usage
tokens = get_trending_tokens('sol', '24h', 'marketcap')
if tokens:
    print(f"Found {len(tokens)} trending tokens")
```

### cURL
```bash
curl -X GET "https://gmgn.ai/defi/quotation/v1/rank/eth/swaps/6h?&orderby=swaps&direction=desc&filters[]=not_honeypot&filters[]=verified&filters[]=renounced"
```

## Rate Limits

- This API is protected by Clouflare, so its required to use third-party captcha solving services.
- No official rate limits are documented
- Recommended: Implement reasonable delays between requests
- Monitor response times and implement exponential backoff if needed

## Error Handling

The API uses standard HTTP status codes and returns error information in the response:

```json
{
    "code": 1,
    "msg": "Error description",
    "data": null
}
```

Common error codes:
- `code: 0` - Success
- `code: 1` - General error
- Check the `msg` field for specific error details

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is licensed under the [MIT License](./LICENSE).

## Contact Information

- Gmail: [steven0822.dev@gmail.com](mailto:steven0822.dev@gmail.com)
- GitHub: [Steven Leal(stevendev0822)](https://github.com/stevendev0822)
- Telegram: [@stevendev0822](https://t.me/stevendev0822)
- Twitter: [@stevendev0822](https://twitter.com/stevendev0822)
- Instagram: [@stevendev0822](https://www.instagram.com/stevendev0822/)


