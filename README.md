# Outback Monitor - remote view

A single static page that shows the current battery/generator snapshot from
the Outback Monitor's "Live status" Google Sheet, styled to match the local
dashboard.

It reads the sheet directly from your browser via the same Apps Script Web
App the monitor pushes readings to (see README, "Live status"), using a
**read-only** key that can only fetch that one row - visible in this page's
source to anyone who looks, but unable to change anything. Because it talks
to Google's servers rather than the shed PC, it works from anywhere, not just
the home wifi.

Unlike the local dashboard, this page has no 24-hour chart: the sheet side
only keeps the single latest snapshot (to avoid growing without bound), so
there's no history to draw a chart from. It refreshes every 60 seconds.

Published via GitHub Pages - see repository settings.

If you rotate `VIEW_SECRET` in the Apps Script (`heartbeat_watchdog.gs`),
update `VIEW_KEY` in `index.html` to match and re-deploy the script (**Deploy
→ Manage deployments → pencil icon → Version: New version → Deploy** -
editing the script alone does not update the live Web App).
