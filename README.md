# Forex Swing Assistant V2 — GitHub Pages

Static, browser-run forex signal monitor. **Trading workflow is 5-minute triggers with 15-minute setup confirmation**, filtered by a daily EMA trend bias. It is not an H4 scanner.

## Deploy to GitHub Pages
1. Create a GitHub repository and upload all files from this folder to its root.
2. In **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, save.
3. Wait for deployment; open the GitHub Pages URL shown there.

No build step or server required. Scanning, settings, signal history, watchlist and Telegram credentials are stored in browser local storage. The tab must stay open for scanning and browser notifications. A browser notification permission is required.

## Included in V2
- Multi-timeframe: Daily trend bias + 15-minute confluence setup + 5-minute rejection/breakout trigger.
- 28-symbol watchlist (majors, crosses, select exotics, metals). Change the watchlist in Settings.
- Configurable minimum confluence score and scan frequency.
- BUY/SELL, entry, stop, TP1/2/3 (1R/2R/3R), setup score and rationale.
- Browser notifications, optional Telegram Bot notifications, persistent signal history.
- Manual news blackout windows, risk calculator, local 24-hour session countdown.
- GitHub Pages-compatible static site.

## Data caveats
This version retrieves Yahoo Finance chart data through a public CORS proxy (`corsproxy.io`) with a direct-fetch fallback. The proxy may be rate-limited, blocked, or unavailable; the app does not include a guaranteed market-data service. Symbols and data quality vary; XAU/XAG use futures proxies. **The original Pine indicator is approximated** with daily levels, pivots, 15m swing levels, round levels, clustering, and 5m trigger patterns, not executed by TradingView's Pine runtime.

## Alerts/security
Telegram credentials are saved locally in your browser and used directly to call the Telegram Bot API. Do not use a shared/public browser profile. A server-side Telegram relay is safer. GitHub Pages is static hosting and cannot run a persistent or 24-hour backend. This app's 24-hour timer is a browser session timer, not server shutdown.

This is an alerting/analysis tool, not an auto-trader or financial advice. Confirm setups and sizing independently.
