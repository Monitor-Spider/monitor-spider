# MonitorSpider

**Website change & defacement detection, synthetic login monitoring, uptime, server metrics, and backup monitoring — in one tool.**

🌐 **[monitorspider.com](https://monitorspider.com)** · [Sign up free](https://monitorspider.com/signup) · [Pricing](https://monitorspider.com/pricing) · [Blog](https://monitorspider.com/blog) · [Live status page](https://monitorspider.com/status?s=monitorspider)

---

## What is MonitorSpider?

MonitorSpider is a web and infrastructure monitoring service that watches your websites, endpoints, and servers and alerts you the moment something changes or breaks. It combines five things most teams otherwise buy separately:

1. **Full-site change & defacement detection** — crawls your site, fingerprints every page, and tells you *what* changed with line-by-line diffs.
2. **Synthetic login monitoring** — runs a real scripted login on a schedule and measures post-login latency, so you know customers can actually sign in (not just that the homepage is up).
3. **Uptime & endpoint monitoring** — HTTP/HTTPS, DNS records, FTP/SFTP, SOCKS proxies, and SSL certificate expiry.
4. **Server & agent metrics** — CPU, memory, and disk from your own servers via Prometheus, Nagios NCPA, and Telegraf.
5. **Backup monitoring (dead-man's-switch)** — your backup job pings MonitorSpider after each run; you get alerted when a backup stops running, fails, hangs, or silently shrinks. Free, auditable [backup kit scripts](https://monitorspider.com/backup-kits/) for Windows/SQL Server and Linux are included.

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
| **Prometheus** | Scrapes a `/metrics` endpoint (node_exporter, Telegraf, Netdata) and alerts on thresholds. One-click **metric auto-detection** suggests the right metrics and limits for your exporter. |
| **Nagios NCPA** | Pulls metrics from the NCPA agent (CPU, memory, load, disk) over its API, with the same one-click metric auto-detection. |
| **Telegraf** | Receives pushed metrics from a Telegraf agent — works through NAT/firewalls since the agent dials out. |
| **Backup (dead-man's-switch)** | Your backup job pings after each run. Alerts when a backup misses its schedule, reports failure, hangs mid-run, or a "successful" backup is suddenly far smaller than usual (silent-shrinkage detection). Graphs backup size and duration over time. |

## Alerting

- **Email** on every plan.
- **Slack, Telegram, and signed webhooks** on Premium.
- **Debounced alerts** — a failure must repeat N consecutive checks before it pages you, so a single blip on the network doesn't wake anyone. Recovery ("back to OK") notifications too.
- **Alert routing** — choose which of your account's users receive alerts by default, and override the recipient list per monitor when one check should page a specific person. Alerts can also be switched off per monitor entirely.
- **Test alerts** — a one-click "Send test alert" per monitor exercises the real delivery path (email recipients + enabled channels) so you can verify who gets paged before an incident does it for you.
- **Silencing** — mute a monitor's alerts for an hour, a day, a week, or permanently (it keeps checking and recording history; only delivery is muted).

## Backup monitoring & free backup kits

Backups fail silently: the scheduled task gets disabled, the disk fills, the job hangs, or it "succeeds" while writing 40 MB where there used to be 10 GB. MonitorSpider's **backup monitor** is a dead-man's-switch: your backup job hits a per-monitor ping URL when it starts and finishes (a one-line `curl` works), and MonitorSpider alerts you when:

- no completed backup arrives within the expected schedule (+ a grace window),
- the job reports a **failure**,
- a run **starts but never finishes** (hung-run detection),
- a "successful" backup is suddenly **much smaller** than the trailing average (silent-shrinkage detection).

Backup size and duration are graphed over time, with up to ~13 months of history.

The **[backup kits](https://monitorspider.com/backup-kits/)** are free, single-file, auditable scripts with the ping built in:

- **Windows / SQL Server** — guided setup wizard (`START-HERE.cmd`): detects SQL instances, backs up with `CHECKSUM` + `VERIFYONLY`, compresses with AES-256 7-Zip split volumes, uploads over FTP/FTPS/SFTP, applies retention, registers the scheduled task, and pings the monitor.
- **Linux** — one-command install (`curl … setup.sh && sudo bash setup.sh`): detects MySQL/PostgreSQL and rclone remotes, tar+gzip with optional GPG encryption, uploads via rclone or curl, cron + retention + ping.
- **`Send-BackupPing.ps1`** — wrap any existing backup tool you already use with just the ping.

The scripts are served as plain text so you can read every line before running them. **The Free plan includes one backup monitor**, so you can put a watchdog on your most important backup without paying anything.

## Pricing

| | **Free** | **Premium — $20/month** |
|---|---|---|
| Monitors | Up to 15 | Up to 1,000 |
| Check frequency | Every 5 minutes | Every 1 minute |
| Uptime, HTTP(S), DNS, FTP/SFTP, SOCKS, SSL | ✅ | ✅ |
| Backup monitors (dead-man's-switch) | 1 included | ✅ |
| Email alerts (with per-user routing) | ✅ | ✅ |
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
3. **Set alert routing** — who gets emailed (per account, overridable per monitor), which channels fire (Slack/Telegram/webhook on Premium), and latency/failure thresholds. Send a test alert to confirm delivery.
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
Email on all plans; Slack, Telegram, and signed webhooks on Premium. Alerts are debounced to avoid false pages, and routing is configurable: pick which users receive alerts by default, override the recipients per monitor, silence a monitor temporarily, or send a one-click test alert to verify delivery.

**Can it tell me when my backups stop working?**
Yes — the backup monitor is a dead-man's-switch. Your backup job pings MonitorSpider after each run (one `curl` line, or use the free backup kit scripts for Windows/SQL Server and Linux). You're alerted when a backup misses its schedule, fails, hangs mid-run, or comes out suspiciously smaller than usual. One backup monitor is included on the Free plan.

**Is MonitorSpider a good alternative to a website change monitor like Visualping, or to a standalone uptime monitor?**
MonitorSpider combines full-site change/defacement detection *and* synthetic login monitoring *and* uptime *and* server metrics in one $20/month plan, which those single-purpose tools don't. It's aimed especially at agencies and MSPs managing many sites.

**Can I show a status page to my customers?**
Yes — every plan can publish a public status page with live status and 90-day uptime history at your own slug.

## Links

- **Website:** https://monitorspider.com
- **Sign up (free):** https://monitorspider.com/signup
- **Pricing:** https://monitorspider.com/pricing
- **Blog & guides:** https://monitorspider.com/blog
- **Free backup kits:** https://monitorspider.com/backup-kits/
- **Example status page:** https://monitorspider.com/status?s=monitorspider

---

*MonitorSpider — know when your site changes, and when your customers can't log in.*
