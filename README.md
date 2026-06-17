# PSX Live AI Trade Assistant

This is the correct version: **free-hostable web app + serverless backend proxy** for Pakistan Stock Exchange data.

It does **not** generate fake/demo prices. If PSX data is blocked or unavailable, the dashboard shows an error and refuses to create fake entry/target/signal.

## What is included

- Browser dashboard
- Serverless API backend for Vercel
- `/api/market` for all PSX shares from PSX market-watch
- `/api/quote?symbol=BIPL` for exact symbol quote
- `/api/history?symbol=BIPL&type=eod` for historical data if the PSX time-series endpoint responds
- All-share scanner
- Top gainers / losers / volume
- Symbol search and watchlist
- Portfolio calculator
- AI trade setup using RSI, MACD, SMA20, SMA50, ATR only when enough real history exists
- No fake fallback data

## Important truth

A perfect live all-PSX dashboard cannot run as a single browser-only `index.html` because PSX blocks direct browser access/CORS in many cases. This project uses a free online serverless backend to solve that.

## Files

```
psx_live_ai_app/
├── api/
│   ├── _lib/psx.js
│   ├── health.js
│   ├── market.js
│   ├── quote.js
│   └── history.js
├── public/
│   ├── index.html
│   ├── styles.css
│   └── app.js
├── package.json
├── vercel.json
└── README.md
```

## Free hosting guide — Vercel, no terminal needed

### Step 1 — Make GitHub account
Go to GitHub and sign in.

### Step 2 — Create new repository
1. Click **New repository**.
2. Name it: `psx-live-ai-app`.
3. Keep it **Public** or **Private**.
4. Click **Create repository**.

### Step 3 — Upload files in browser
1. Extract this ZIP on your computer.
2. Open your GitHub repo.
3. Click **Add file → Upload files**.
4. Drag all files/folders from `psx_live_ai_app` into GitHub.
5. Click **Commit changes**.

Make sure GitHub shows these folders:

- `api`
- `public`
- `package.json`
- `vercel.json`

### Step 4 — Deploy on Vercel free
1. Go to Vercel.
2. Sign in with GitHub.
3. Click **Add New → Project**.
4. Select your `psx-live-ai-app` repository.
5. Framework preset can stay **Other**.
6. Click **Deploy**.

After deploy you will get a live URL like:

```
https://psx-live-ai-app.vercel.app
```

### Step 5 — Test API first
Open these URLs after deployment:

```
https://YOUR-APP.vercel.app/api/health
https://YOUR-APP.vercel.app/api/market
https://YOUR-APP.vercel.app/api/quote?symbol=BIPL
```

If `/api/market` returns `ok: true` and many symbols, the dashboard will work.

## How to use dashboard

1. Open your Vercel live URL.
2. Wait for **Market loaded** status.
3. Search symbol like `BIPL`, `HBL`, `OGDC`, `MEBL`.
4. Click **Load Quote**.
5. Click **Load History + Signal** for RSI/MACD/ATR signal.
6. Use scanner for all PSX shares.

## Data limitations

- Market quote data comes from PSX Data Portal market-watch through your serverless function.
- Historical/time-series endpoint may sometimes fail or change. If it fails, app will show quote only and no technical signal.
- For reliable broker-level real-time tick feed, connect a licensed PSX/vendor API later.

## Safety

This is an analysis assistant, not guaranteed profit software and not financial advice. Always verify trades manually and use risk management.
