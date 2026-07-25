# Outback Monitor - remote view

A single static page that shows the current battery/generator snapshot from
the Outback Monitor's Airtable base, styled to match the local dashboard.

It reads Airtable directly from your browser using a **read-only** API
token (scoped to `data.records:read` on one base only) - visible in this
page's source to anyone who looks, but unable to change anything.

Unlike the local dashboard, this page has no 24-hour chart: the Airtable
side only keeps the single latest snapshot (to avoid growing without bound),
so there's no history to draw a chart from. It refreshes every 60 seconds.

Published via GitHub Pages - see repository settings.
