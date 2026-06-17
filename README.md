# PSX Simple Live Site

This is the simple/easy version for Pakistan Stock Exchange market-watch data.

## What it does

- Shows PSX market-watch data from `https://dps.psx.com.pk/market-watch`
- Search exact symbol, for example `BIPL`, `HBL`, `OGDC`
- Shows current price, open, high, low, change, percent change and volume
- Shows a simple rules-based bot signal
- Shows all shares in one table
- No fake prices, no demo fallback

## Free hosting without terminal

1. Extract this ZIP.
2. Create a free GitHub account or open your GitHub account.
3. Create a new repository, for example: `psx-simple-live-site`.
4. Upload these files/folders into the repository:
   - `api`
   - `public`
   - `package.json`
   - `vercel.json`
   - `README.md`
5. Go to Vercel.com and sign in with GitHub.
6. Click **Add New → Project**.
7. Select your GitHub repository.
8. Framework preset: **Other**.
9. Click **Deploy**.
10. Open your Vercel URL.

## Test URLs after deploy

- `https://YOUR-SITE.vercel.app/api/health`
- `https://YOUR-SITE.vercel.app/api/market`
- `https://YOUR-SITE.vercel.app/api/quote?symbol=BIPL`

## Important

PSX market data usage may require authorization/license depending on use case. This site is for personal/educational testing. It does not place trades and does not guarantee profit.
