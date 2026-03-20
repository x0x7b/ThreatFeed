# ThreatFeed

Catch critical CVEs before they become headline incidents.  
Real-time vulnerability alerts with less noise, faster triage, and better signal for security teams.

→ **[t.me/ThreatFeedRobot](https://t.me/ThreatFeedRobot)**

---

## The Problem

Most CVE feeds are too slow, too broad, or too noisy. Security teams waste time on irrelevant alerts, duplicated advisories, and long streams of low-priority events that hide the issues that actually need action.

## The Solution

ThreatFeed turns raw vulnerability updates into filtered, real-time alerts delivered where teams already respond fastest. Instead of monitoring dozens of sources manually, teams receive a clean stream of relevant CVEs shaped around their products, vendors, and risk priorities.

## Features

- Real-time CVE alert delivery (~90s from publication)
- Filtered results by vendor, product, keyword, and severity range
- Multiple upstream data sources for broader coverage
- Clean alert formatting for fast triage
- Delivery via Telegram
- Historical alert lookup for recent CVEs
- API-ready alert feed for dashboards and automations

## Example Alert

```json
{
  "id": "CVE-2026-12345",
  "published_at": "2026-03-20T09:18:00Z",
  "severity": "CRITICAL",
  "score": 9.4,
  "vendor": "ExampleSoft",
  "product": "Gateway Manager",
  "summary": "Unauthenticated remote code execution in the management interface.",
  "tags": ["rce", "network", "edge"],
  "references": [
    "https://example.com/advisories/CVE-2026-12345"
  ]
}
```

## Pricing

| Plan | Price | CVSS Range | CWE Filter | Product Filter |
|------|-------|------------|------------|----------------|
| Free | $0/mo | 7.0 – 8.0 | — | — |
| Pro  | $2/mo | Any        | ✓ | ✓ |

Pro is free for the first 3 days. No credit card required.

## Docs

- [Overview](docs/overview.md)
- [Public API](docs/api.md)
- [FAQ](docs/faq.md)
- [Roadmap](docs/roadmap.md)
- [Changelog](docs/changelog.md)

## Repository Scope

This repository is a public product overview intended for demos and integrations. It does not include production logic, internal processing rules, or private infrastructure.
