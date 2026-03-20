# FAQ

## What is ThreatFeed?

A real-time CVE alerting service for security teams. It monitors vulnerability feeds, filters by your criteria, and delivers relevant alerts via Telegram — typically within ~90 seconds of publication.

## How do I get started?

Open the bot on Telegram: [t.me/ThreatFeedRobot](https://t.me/ThreatFeedRobot)  
Pro features are free for the first 3 days. No credit card required.

## What's the difference between Free and Pro?

| | Free | Pro ($2/mo) |
|---|---|---|
| Real-time alerts | ✓ | ✓ |
| CVSS range | 7.0 – 8.0 | Any |
| CWE filter | — | ✓ |
| Product & vendor filter | — | ✓ |

## Does ThreatFeed use a single data source?

No. The service aggregates multiple upstream sources to improve coverage and reduce blind spots from any single feed.

## Who is ThreatFeed for?

Security engineers, MSSPs, platform teams, and anyone who needs faster awareness of vulnerabilities that affect their stack — without drowning in noise.

## Is there an API?

Yes. See [api.md](api.md) for the public demo spec. The API returns structured alert payloads suitable for dashboards, SIEM ingestion, or custom automation.

## Is this the production codebase?

No. This repository is a public-facing product and integration overview with illustrative examples only. It does not include internal processing logic or infrastructure details.

## Can I cancel anytime?

Yes. Pro is month-to-month with no lock-in.
