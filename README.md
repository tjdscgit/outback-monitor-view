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

It also draws the same battery-voltage and power-usage charts as the local
dashboard, from a "History" sheet the Apps Script appends one row to on every
live push (separate from "Live status", which is just the latest snapshot,
overwritten in place). A dropdown picks the window (6h/12h/24h/3 days/7
days) - longer than the local dashboard's fixed 24 hours, since this page
isn't limited to WattPlot's local hourly files. There are no generator/grid
shading bands on this chart, unlike the local one - that history doesn't
leave the shed PC. It refreshes every 60 seconds.

Published via GitHub Pages - see repository settings.

If you rotate `VIEW_SECRET` in the Apps Script (`heartbeat_watchdog.gs`),
update `VIEW_KEY` in `index.html` to match and re-deploy the script (**Deploy
→ Manage deployments → pencil icon → Version: New version → Deploy** -
editing the script alone does not update the live Web App).
