<<<<<<< HEAD
# Public Dashboard
A **financial activity dashboard** that provides clear visibility into brokerage account activity — including trades, dividends, fees, and cash movement — in a single, easy-to-understand interface.

The dashboard is designed for **safety, transparency, and scalability**. It aggregates account activity from brokerage systems, stores it as a persistent event ledger, and presents both detailed history and high-level summaries without allowing any trading or account changes.

---

## Key Features
- 📊 **Unified activity feed** for trades, dividends, transfers, and fees  
- 🔍 **Read-only by design** — no trading or account mutations  
- 🧾 **Persistent event history** for reliable tracking and auditability  
- 🔁 **Broker-agnostic architecture** using adapter interfaces  
- 🧮 **Derived analytics** such as cash flow, income, and activity summaries  
- ⚙️ **Background ingestion** independent of user interaction  
- 🧪 **Automated testing** (unit, integration, and UI smoke tests)  
- 🚀 **CI/CD pipelines** with staging, production, and health checks  

---

## Who This Is For
- Investors who want a clear, organized view of account activity  
- Engineers building financial dashboards or fintech tools  
- Teams that need a safe, read-only financial reporting layer  
- Anyone interested in modern, production-ready web architecture  

---

## Technology Overview
- **Language:** TypeScript  
- **Front End:** React / Next.js 14  
- **Back End:** Node.js / Next.js API routes  
- **Database:** SQLite (local), PostgreSQL (staging & production)  
- **ORM:** Prisma  
- **CI/CD:** GitHub Actions  

---

## Design Philosophy
This project intentionally separates **data ingestion**, **persistence**, **analytics**, and **presentation**.  
By storing immutable activity events and deriving analytics dynamically, the system remains flexible, auditable, and easy to extend — including support for additional broker integrations in the future.

---

## Getting Started
This project is designed to run locally with minimal setup and no external dependencies.

### Prerequisites
- Node.js 18+
- npm
- Git

### Local Setup
Clone the repository:

```bash
git clone https://github.com/<your-username>/public-dashboard.git
cd public-dashboard
npm install
npx prisma migrate dev --name init
npm run dev

Open browser to: http://localhost:3000
=======
# Public Dashboard Starter (Next.js + TypeScript)

This repo is a **mock-first** starter for building an investment monitoring dashboard powered by the **Public.com Trading API**.

It ships with:
- Next.js 14 (App Router) + TypeScript
- TanStack Query for polling/caching
- Tailwind CSS for fast UI iteration
- Server-side Public API proxy routes (accounts, portfolio, quotes, options expirations/chain/greeks, history)
- Prisma + SQLite for watchlists, preferences, audit logs, and order tracking
- Order Blotter page (Public open orders + locally tracked submissions)
- Optional trading endpoints (preflight/place/status/cancel) behind strict safety gates
- A safe default **MOCK mode** so you can run the UI without any keys

## Quick start (mock mode)

1) Install

```bash
npm install
```

2) Configure env

```bash
cp .env.example .env.local
```

3) Run

```bash
npm run dev
```

Open: http://localhost:3000

## Initialize the database (recommended)

This repo uses SQLite by default.

```bash
npm run prisma:migrate
```

## Enable live Public API calls (optional)

1) Edit `.env.local`:

- Set `MOCK_PUBLIC_API=false`
- Set `PUBLIC_SECRET_TOKEN=...`

2) Restart `npm run dev`

### Important
- The secret token **must never** be exposed to the browser.
- Trading is **off by default**. To enable it, you must:
  1) set `ENABLE_TRADING=true` on the server
  2) enable trading in the Settings page (DB toggle)
  3) if `TRADING_UNLOCK_CODE` is set, store the matching unlock code locally in Settings

## Implemented proxy routes

- `GET /api/public/accounts`
- `GET /api/public/portfolio?accountId=`
- `POST /api/public/quotes?accountId=`
- `POST /api/public/options/expirations?accountId=`
- `POST /api/public/options/chain?accountId=`
- `GET /api/public/options/greeks?accountId=&osiSymbols=`
- `POST /api/public/options/greeks` (batched; body: `{ accountId, osiSymbols: string[] }`)
- `GET /api/public/history?accountId=&start=&end=&pageSize=&nextToken=`

### Trading routes (gated)

- `POST /api/public/orders/preflight/single`
- `POST /api/public/orders/preflight/multi`
- `POST /api/public/orders/place`
- `GET /api/public/orders/status?accountId=&orderId=`
- `DELETE /api/public/orders/cancel?accountId=&orderId=`

### App routes (DB-backed)

- `GET/POST /api/watchlists`
- `DELETE /api/watchlists/[watchlistId]`
- `POST/DELETE /api/watchlists/[watchlistId]/items`
- `GET/POST /api/prefs`
- `GET /api/audit?limit=`
- `GET /api/order-tracking?limit=&accountId=`

## Next steps

1) Replace local single-user mode with real authentication
2) Add risk controls (max order size, symbol allowlists, two-person rule)
3) Add rate limiting and circuit breakers for upstream failures
>>>>>>> 607fdb0 (Initial commit of existing code)
>>>>>>>
<img width="1752" height="1117" alt="Image" src="https://github.com/user-attachments/assets/5cc0c3c3-4d9f-41fb-ac48-7bda47750de3" />

