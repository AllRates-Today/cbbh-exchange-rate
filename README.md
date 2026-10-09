# Central Bank of Bosnia and Herzegovina Exchange Rates API — cbbh-exchange-rate

[![npm version](https://img.shields.io/npm/v/cbbh-exchange-rate.svg)](https://www.npmjs.com/package/cbbh-exchange-rate)
[![license](https://img.shields.io/npm/l/cbbh-exchange-rate.svg)](https://github.com/AllRates-Today/cbbh-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/cbbh-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![EUR/BAM today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbbh%3Fsource%3DEUR%26target%3DBAM&query=%24.rate&label=EUR%2FBAM%20published%20by%20Central%20Bank%20of%20Bosnia%20and%20Herzegovina&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbbh/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbbh%3Fsource%3DEUR%26target%3DBAM&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbbh/)

**Official Central Bank of Bosnia and Herzegovina (Bosnia and Herzegovina) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Central Bank of Bosnia and Herzegovina itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Central Bank of Bosnia and Herzegovina's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Central Bank of Bosnia and Herzegovina itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Central Bank of Bosnia and Herzegovina table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/cbbh?source=EUR&target=BAM"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/cbbh').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Central Bank of Bosnia and Herzegovina table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by Central Bank of Bosnia and Herzegovina — 49 rates. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AUD | BAM | buy | 1.211012 |
| AUD | BAM | middle | 1.214047 |
| AUD | BAM | sell | 1.217082 |
| CAD | BAM | buy | 1.22293 |
| CAD | BAM | middle | 1.225995 |
| CAD | BAM | sell | 1.22906 |
| CHF | BAM | buy | 2.091937 |
| CHF | BAM | middle | 2.09718 |
| CHF | BAM | sell | 2.102423 |
| CNY | BAM | buy | 0.260223 |
| CNY | BAM | middle | 0.260875 |
| CNY | BAM | sell | 0.261527 |
| CZK | BAM | buy | 0.079947 |
| CZK | BAM | middle | 0.080147 |
| CZK | BAM | sell | 0.080347 |
| DKK | BAM | buy | 0.261034 |
| DKK | BAM | middle | 0.261688 |
| DKK | BAM | sell | 0.262342 |
| EUR | BAM | buy | 1.95583 |
| EUR | BAM | middle | 1.95583 |
| EUR | BAM | sell | 1.95583 |
| GBP | BAM | buy | 2.303408 |
| GBP | BAM | middle | 2.309181 |
| GBP | BAM | sell | 2.314954 |
| HUF | BAM | buy | 0.0053268 |
| HUF | BAM | middle | 0.00534015 |
| HUF | BAM | sell | 0.0053535 |
| JPY | BAM | buy | 0.01101915 |
| JPY | BAM | middle | 0.01104677 |
| JPY | BAM | sell | 0.01107439 |
| NOK | BAM | buy | 0.182042 |
| NOK | BAM | middle | 0.182498 |
| NOK | BAM | sell | 0.182954 |
| RSD | BAM | buy | 0.01662143 |
| RSD | BAM | middle | 0.01666309 |
| RSD | BAM | sell | 0.01670475 |
| RUB | BAM | buy | 0.020485 |
| RUB | BAM | middle | 0.020536 |
| RUB | BAM | sell | 0.020587 |
| SEK | BAM | buy | 0.174284 |
| SEK | BAM | middle | 0.174721 |
| SEK | BAM | sell | 0.175158 |
| TRY | BAM | buy | 0.035438 |
| TRY | BAM | middle | 0.035527 |
| TRY | BAM | sell | 0.035616 |
| USD | BAM | buy | 1.744091 |
| USD | BAM | middle | 1.748462 |
| USD | BAM | sell | 1.752833 |
| XDR | BAM | middle | 2.366163 |

Source: [Official rates published by CBBH, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/cbbh/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install cbbh-exchange-rate
```

```bash
yarn add cbbh-exchange-rate
```

```bash
pnpm add cbbh-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/cbbh-exchange-rate`](https://www.npmjs.com/package/@allratestoday/cbbh-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'cbbh-exchange-rate';

const pair = await getRate('EUR', 'BAM', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Central Bank of Bosnia and Herzegovina rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('EUR', 'BAM', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'cbbh',
  name: 'Central Bank of Bosnia and Herzegovina',
  rate_date: '2026-10-08',   // Central Bank of Bosnia and Herzegovina's own publication date
  source: 'EUR',
  target: 'BAM',
  rate: 1.95583,
  rate_type: 'middle',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'cbbh-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'cbbh',
  name: 'Central Bank of Bosnia and Herzegovina',
  rate_date: '2026-10-08',
  rates: [
    { "base": "EUR", "quote": "BAM", "type": "middle", "value": 1.95583 },
    { "base": "EUR", "quote": "BAM", "type": "sell", "value": 1.95583 },
    { "base": "EUR", "quote": "BAM", "type": "buy", "value": 1.95583 },
    // … the rest of the published table (17 currencies vs BAM)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'cbbh-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'EUR', target: 'BAM' });
```

**Response:**

```javascript
{
  bank: 'cbbh',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'cbbh-exchange-rate';

const series = await getHistory(
  { source: 'EUR', target: 'BAM', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'cbbh',
  source: 'EUR',
  target: 'BAM',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 1.95583, rate_type: 'middle', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'EUR' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Central Bank of Bosnia and Herzegovina currently publishes rates covering **17 currencies** against the BAM (as of the latest table):

🇦🇺 `AUD` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇨🇿 `CZK` · 🇩🇰 `DKK` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇭🇺 `HUF` · 🇯🇵 `JPY` · 🇳🇴 `NOK` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇸🇪 `SEK` · 🇹🇷 `TRY` · 🇺🇸 `USD` · `XDR`

## 🏛️ Source

The Central Bank of Bosnia and Herzegovina operates a currency board: the convertible mark is fixed at 1.95583 BAM per euro. It publishes an official daily exchange rate list with buy, middle, and sell rates for major currencies.

- Publisher's own page: [Currency exchange rate list](https://www.cbbh.ba/CurrencyExchange/) · [www.cbbh.ba](https://www.cbbh.ba)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Central Bank of Bosnia and Herzegovina rates page](https://allratestoday.com/central-bank-rates-api/cbbh/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Central Bank of Bosnia and Herzegovina quotes **BAM per 1 unit of foreign currency** (e.g. `base: "USD", quote: "BAM"` means BAM per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`middle` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Central Bank of Bosnia and Herzegovina rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/cbbh/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('cbbh')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate cbbh ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Central Bank of Bosnia and Herzegovina does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via BAM from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('EUR', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Central Bank of Bosnia and Herzegovina |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'cbbh-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('cbbh-exchange-rate');

getRate('EUR', 'BAM', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/cbbh.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/cbbh/latest.json`

## 🔗 Links

- [Central Bank of Bosnia and Herzegovina rates page](https://allratestoday.com/central-bank-rates-api/cbbh/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/cbbh-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/cbbh-exchange-rate)

## 📜 License

MIT
