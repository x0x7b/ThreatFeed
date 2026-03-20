# Overview

ThreatFeed is a real-time vulnerability alerting service designed to help security teams detect relevant CVEs quickly and act on them with less noise.

## How It Works

The platform ingests vulnerability data from multiple sources, normalizes records into a consistent alert format, and delivers relevant events through Telegram and a public API.

Every alert includes:

- CVE identifier and publication timestamp
- CVSS score and severity rating
- CWE type classification
- Affected vendor and product
- Short human-readable summary
- Tags and reference links

## Filtering Model

Filtering is applied through configurable matching rules. These rules reflect vendor names, product families, severity thresholds, and keyword signals — so teams only receive alerts relevant to their stack.

Free tier limits filtering to CVSS 7.0–8.0. Pro unlocks the full range plus CWE and product-level filters.

## Delivery

ThreatFeed delivers alerts via Telegram in near real-time (~90 seconds from CVE publication). A public API is also available for teams that want to integrate alerts into dashboards, SIEMs, or automation pipelines.

## Design Goals

- **Speed** — alerts reach teams before exploit PoCs circulate
- **Signal over noise** — only relevant CVEs, shaped to your stack
- **Operational format** — structured enough for tooling, readable enough for immediate triage
