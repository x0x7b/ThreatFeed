# Public API

Public demo API for ThreatFeed. All payloads in this document are illustrative examples.

> Field names and response formats may change in the production service.  
> Authentication, rate limits, and subscription tiers are omitted from this demo spec.

---

## `GET /alerts`

Returns a list of recent CVE alerts.

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `limit` | integer | Max number of results to return |
| `severity` | string | Filter by severity: `critical`, `high`, `medium`, `low` |

### Example Request

```http
GET /alerts?limit=2&severity=critical
```

### Example Response

```json
{
  "data": [
    {
      "id": "CVE-2026-12345",
      "published_at": "2026-03-20T09:18:00Z",
      "severity": "CRITICAL",
      "score": 9.4,
      "vendor": "ExampleSoft",
      "product": "Gateway Manager",
      "summary": "Unauthenticated remote code execution in the management interface.",
      "tags": ["rce", "network", "edge"]
    },
    {
      "id": "CVE-2026-12001",
      "published_at": "2026-03-20T07:02:00Z",
      "severity": "HIGH",
      "score": 8.1,
      "vendor": "Northwind",
      "product": "Container Hub",
      "summary": "Privilege escalation in deployment pipelines.",
      "tags": ["privesc", "ci-cd"]
    }
  ],
  "meta": {
    "limit": 2,
    "next_cursor": "demo_cursor_002"
  }
}
```

---

## `GET /cve/{id}`

Returns full details for a single CVE alert record.

### Example Request

```http
GET /cve/CVE-2026-12345
```

### Example Response

```json
{
  "id": "CVE-2026-12345",
  "published_at": "2026-03-20T09:18:00Z",
  "updated_at": "2026-03-20T10:11:00Z",
  "severity": "CRITICAL",
  "score": 9.4,
  "vendor": "ExampleSoft",
  "product": "Gateway Manager",
  "summary": "Unauthenticated remote code execution in the management interface.",
  "description": "A crafted request to the management interface may allow remote code execution without prior authentication.",
  "affected_versions": ["<= 4.8.2"],
  "tags": ["rce", "network", "edge"],
  "references": [
    "https://example.com/advisories/CVE-2026-12345",
    "https://nvd.nist.gov/vuln/detail/CVE-2026-12345"
  ]
}
```

---

## Alert Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | CVE identifier |
| `published_at` | ISO 8601 | Original publication timestamp |
| `updated_at` | ISO 8601 | Last modification timestamp |
| `severity` | string | `CRITICAL`, `HIGH`, `MEDIUM`, `LOW` |
| `score` | float | CVSSv3 base score |
| `vendor` | string | Affected vendor name |
| `product` | string | Affected product name |
| `summary` | string | Short human-readable description |
| `description` | string | Full technical description |
| `affected_versions` | array | Version range strings |
| `tags` | array | Keyword tags for triage |
| `references` | array | Advisory and NVD URLs |
