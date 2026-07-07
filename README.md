# MonitorSpider

**Website change & defacement detection, synthetic login monitoring, uptime, and server metrics — in one tool.**

🌐 **[monitorspider.com](https://monitorspider.com)** · [Sign up free](https://monitorspider.com/signup) · [Pricing](https://monitorspider.com/pricing) · [Blog](https://monitorspider.com/blog) · [Live status page](https://monitorspider.com/status?s=monitorspider)

---

## What is MonitorSpider?

MonitorSpider is a web and infrastructure monitoring service that watches your websites, endpoints, and servers and alerts you the moment something changes or breaks. It combines four things most teams otherwise buy separately:

1. **Full-site change & defacement detection** — crawls your site, fingerprints every page, and tells you *what* changed with line-by-line diffs.
2. **Synthetic login monitoring** — runs a real scripted login on a schedule and measures post-login latency, so you know customers can actually sign in (not just that the homepage is up).
3. **Uptime & endpoint monitoring** — HTTP/HTTPS, DNS records, FTP/SFTP, SOCKS proxies, and SSL certificate expiry.
4. **Server & agent metrics** — CPU, memory, and disk from your own servers via Prometheus, Nagios NCPA, and Telegraf.

It's built for **agencies, MSPs, and teams** that run many client sites: watch every site's uptime, content changes, logins, certs, and servers from one dashboard, and route alerts to email, Slack, Telegram, or a webhook.

MonitorSpider is a hosted SaaS. There is nothing to install for website monitoring — you add a monitor and MonitorSpider's probes do the rest. Optional lightweight agents (Prometheus exporters, NCPA, or Telegraf) enable server-level metrics.

## Why MonitorSpider

- **A green uptime check isn't enough.** Your homepage can return `200` while the login is broken, a page has been defaced, or a price was edited by mistake. MonitorSpider catches those.
- **See exactly what changed.** Change detection keeps version history and shows a colored, line-by-line diff — not just a "something changed" ping.
- **One tool, many signals.** Uptime, change detection, synthetic logins, SSL/DNS, *and* server metrics under one login and one bill.
- **Alerts where your team already works.** Email on every plan; Slack, Telegram, and signed webhooks on Premium — with debouncing so a single flap never pages you.
- **Public status pages.** Publish a branded status page for your customers with live status and 90-day uptime history.

## Monitor types

| Type | What it does |
|------|--------------|
| **Webpage / website change detection** | Recursive crawl with per-page content hashing; alerts on defacement, edits, broken deploys, or vanished pages. Keeps version history + line diffs. |
| **Login + latency (synthetic)** | Scripted login with success/failure assertions, per-element latency on the authenticated page, and latency-threshold alerts. |
| **HTTP / HTTPS** | Status-code and response-body checks, response-time tracking, uptime %. Supports expected non-200 codes and a "monitor for a redirect" mode. |
| **DNS record watch** | Alerts when an A, MX, TXT, or any DNS record changes out from under you. |
| **FTP / SFTP** | Confirms file servers are reachable and accepting connections. |
| **SOCKS proxies** | Health-checks SOCKS4/5 proxies from MonitorSpider's probes. |
| **SSL certificates** | Tracks expiry and chain health so a certificate never lapses unnoticed. |
| **Prometheus** | Scrapes a `/metrics` endpoint (node_exporter, Telegraf, Netdata) and alerts on thresholds. |
| **Nagios NCPA** | Pulls metrics from the NCPA agent (CPU, memory, load, disk) over its API. |
| **Telegraf** | Receives pushed metrics from a Telegraf agent — works through NAT/firewalls since the agent dials out. |

## Alerting

- **Email** on every plan.
- **Slack, Telegram, and signed webhooks** on Premium.
- **Debounced alerts** — a failure must repeat N consecutive checks before it pages you, so a single blip on the network doesn't wake anyone. Recovery ("back to OK") notifications too.
- **Company-wide recipients** — alerts go to every user on the account, not one inbox.

## Pricing

| | **Free** | **Premium — $20/month** |
|---|---|---|
| Monitors | Up to 15 | Up to 1,000 |
| Check frequency | Every 5 minutes | Every 1 minute |
| Uptime, HTTP(S), DNS, FTP/SFTP, SOCKS, SSL | ✅ | ✅ |
| Email alerts | ✅ | ✅ |
| Public status page | ✅ | ✅ (unbranded option) |
| Change & defacement detection (with version history & diffs) | — | ✅ |
| Synthetic login + latency monitoring | — | ✅ |
| Server & agent metrics (Prometheus / NCPA / Telegraf) | — | ✅ |
| Slack, Telegram & webhook alerts | — | ✅ |
| Team members | — | ✅ |

No credit card required for Free. Upgrade or cancel anytime from the dashboard. → **[See full pricing](https://monitorspider.com/pricing)**

## Who it's for

- **Agencies & MSPs** monitoring many client websites, logins, certs, and servers from one dashboard.
- **E-commerce & content teams** that need to know instantly when a page is defaced, a price is wrong, or content changes unexpectedly.
- **SaaS & product teams** that must confirm the *login flow* works, not just that the site responds.
- **Ops / SRE teams** wanting website checks and server metrics (Prometheus/NCPA/Telegraf) in one place, with a public status page for customers.

## How it works

1. **Sign up free** at [monitorspider.com/signup](https://monitorspider.com/signup) — no credit card.
2. **Add monitors** for your sites, endpoints, DNS records, certs, or servers.
3. **Set alert channels** (email, or Slack/Telegram/webhook on Premium) and latency/failure thresholds.
4. MonitorSpider checks on your schedule, debounces flaps, and alerts on real status changes.
5. Optionally **publish a public status page** for your customers.

## FAQ

**Is MonitorSpider free?**
Yes — the Free plan includes up to 15 monitors with 5-minute checks, email alerts, and a public status page, with no credit card. Premium is $20/month.

**What's the difference between change detection and uptime monitoring?**
Uptime monitoring tells you whether a site responds. Change detection tells you whether the *content* changed — a defacement, an edited price, a broken deploy, or a removed page — and shows you the exact diff. MonitorSpider does both.

**Can it monitor whether users can log in?**
Yes. Synthetic login monitoring runs a real scripted login on a schedule, asserts success or failure, and measures how long the authenticated page takes to load.

**Does it monitor servers, not just websites?**
Yes. MonitorSpider ingests server metrics (CPU, memory, disk, load) via Prometheus scrape, Nagios NCPA (pull), or Telegraf (push), and alerts on thresholds.

**How do I get alerts?**
Email on all plans; Slack, Telegram, and signed webhooks on Premium. Alerts are debounced to avoid false pages.

**Is MonitorSpider a good alternative to a website change monitor like Visualping, or to a standalone uptime monitor?**
MonitorSpider combines full-site change/defacement detection *and* synthetic login monitoring *and* uptime *and* server metrics in one $20/month plan, which those single-purpose tools don't. It's aimed especially at agencies and MSPs managing many sites.

**Can I show a status page to my customers?**
Yes — every plan can publish a public status page with live status and 90-day uptime history at your own slug.

## Links

- **Website:** https://monitorspider.com
- **Sign up (free):** https://monitorspider.com/signup
- **Pricing:** https://monitorspider.com/pricing
- **Blog & guides:** https://monitorspider.com/blog
- **Example status page:** https://monitorspider.com/status?s=monitorspider

---

*MonitorSpider — know when your site changes, and when your customers can't log in.*
