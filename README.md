# CoinEx

CoinEx is a global cryptocurrency exchange offering REST and WebSocket APIs for spot trading, futures, perpetual contracts, market data, order management, asset operations, and sub-account administration.

**API Version**: v2 (launched January 2024; v1 discontinued September 2024)

**Base URL**: `https://api.coinex.com/v2`

**WebSocket - Spot**: `wss://socket.coinex.com/v2/spot`

**WebSocket - Futures**: `wss://socket.coinex.com/v2/futures`

## API Modules

- **Account** — Sub-account administration, API key management, trading fee inquiries
- **Asset** — Balance retrieval, margin borrowing/repayment, deposits/withdrawals, cross-account transfers
- **Spot** — Market data (depth, trades, K-line), order placement, modification, cancellation
- **Futures** — Perpetual contract market data, funding rates, position management, TP/SL orders
- **Referral** — Referee tracking, rebate records

## Authentication

HMAC-SHA256 signature. Required headers for authenticated requests:
- `X-COINEX-KEY` — your access_id
- `X-COINEX-SIGN` — HMAC-SHA256(method + path + body + timestamp, secret_key) as lowercase hex
- `X-COINEX-TIMESTAMP` — current timestamp in milliseconds

Public market data endpoints require no authentication.

## Rate Limits

- **IP limit**: 400 requests/second (all users on same IP)
- **Spot orders**: 30 req/s (place), 60 req/s (cancel), 50 req/s (query)
- **Futures orders**: 20 req/s (place), 40 req/s (cancel), 50 req/s (query)
- Long-cycle limits (1H/4H/8H/24H) trigger low-speed mode when exceeded

## Pricing

API access is free. Trading fees based on VIP tier:
- Base spot fees: 0.20% maker / 0.20% taker
- Top VIP spot fees: 0.012% maker / 0.024% taker
- Base futures fees: 0.03% maker / 0.05% taker
- CET token: pay fees in CET for up to 25% discount

## Links

- [API Documentation](https://docs.coinex.com/api/v2/)
- [Developer Console](https://www.coinex.com/en/apikey)
- [Authentication Guide](https://docs.coinex.com/api/v2/authorization)
- [Rate Limits](https://docs.coinex.com/api/v2/rate-limit)
- [Changelog](https://docs.coinex.com/api/v2/changelog)
- [Fees](https://www.coinex.com/en/fees)
- [GitHub Organization](https://github.com/coinexcom)
- [Python SDK (ccxt)](https://github.com/ccxt/coinex-python)
- [.NET SDK](https://www.nuget.org/packages/CoinEx.Net)
- [Help Center](https://support.coinex.com/)
