# CoinEx

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
