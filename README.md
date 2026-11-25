# Forex Swing Assistant V2 (GitHub Pages)

Static browser-based forex scanner for **Daily trend context + 15-minute setups + 5-minute triggers**. No server or build step is required.

## Publish to GitHub Pages
1. Create a public repository.
2. Upload these files to the repository root: `index.html`, `app.js`, `style.css`, `.nojekyll`, `README.md`.
3. Open **Settings → Pages**.
4. Set Source to **Deploy from a branch**, branch **main**, folder **/(root)** and Save.
5. Wait for deployment to finish in Actions, then open the URL shown under Settings → Pages.

## Use
- **Scan now**: fetch candles and scan the selected watchlist.
- **All / Signals / BUY / SELL**: filter market cards.
- **Enable browser alerts**: request notification permission.
- **Settings**: watchlist, minimum confluence score, scan interval, manual news blackout UTC windows, and risk calculator.
- Signals are saved in the browser's local storage. Browser alerts and scanning require this page to remain open.

## Data / limitations
- The scanner requests Yahoo Finance chart data through a public CORS proxy. Public proxy and Yahoo data availability, rate limits, CORS behavior, symbol coverage and data freshness are not guaranteed. A market-data error will be shown in the market cards instead of silently hiding it.
- GitHub Pages is static hosting. This app has no backend; settings/history are local to each browser/device. Telegram bot token/chat ID are stored in local browser storage and Telegram calls may be blocked by browser CORS. Do not use Telegram tokens on shared devices.
- Trend calculation and confluence logic are simplified approximations of the source indicator, not a Pine Script runtime. Gold/silver futures symbols are used as proxies.
- Informational only; not investment advice or automated trading.


### Market-data connectivity note

This GitHub Pages-only build tries multiple public CORS relays to reach Yahoo Finance. Public relays can return 401/403, throttle, or go offline; this is not a guaranteed data feed. For reliable live scanning, use a small Cloudflare Worker or another server-side proxy with a reputable market-data provider. Yahoo Finance is unofficial and should not be treated as a stable API.
