[Euipo Trademark Search](https://apify.com/ryanclinton/euipo-trademark-search?fpr=data)

EUIPO Trademark Search is a tool that lets you check if a brand name is available in the EU and understand the risk instantly.

It searches the official EUIPO trademark database and tells you whether your brand is safe, what's risky, and what to do next. It returns structured EU trademark records with clearance risk scoring, composite similarity analysis, lifecycle tracking, and alert-ready output for automated monitoring.

EUIPO Trademark Search is a tool for searching and analysing EU trademarks using the official EUIPO database. It is a ready-to-use EU trademark search and clearance tool built on the official EUIPO API — the easiest way to search, analyse, and monitor EU trademarks without building your own integration.

Also known as: EU trademark lookup, European trademark database search, EUIPO trademark API, trademark clearance search EU, check EU trademark availability

**Use this actor if:**

- You need to know if a brand name conflicts with existing EU trademarks
- You want automated trademark monitoring with alerts on new risks
- You need batch clearance, portfolio expiry tracking, or competitor filing intelligence

**Do not use this if:**

- You need UK, US, or national trademark data
- You need logo or image similarity search
- You need legal clearance opinions

**Requires:** Free EUIPO Developer Portal credentials ([dev.euipo.europa.eu](https://dev.euipo.europa.eu/)) — Client ID and Client Secret

**Start here:** Enter a trademark name like "Northstar", set maxResults to 25, paste your EUIPO credentials, and run. Results appear in 10-30 seconds. Add your own mark in the "Your Mark" field to see similarity scores. You can run this actor manually, via API, or on a schedule to monitor trademarks continuously.

## What does EUIPO Trademark Search do?

EUIPO Trademark Search lets you check if a brand name is available in the EU and understand the risk instantly using the official EUIPO database.

## What is EUIPO Trademark Search?

EUIPO Trademark Search is an EU trademark clearance and monitoring engine that searches the official EUIPO database and returns risk-scored results via API.

It connects to the official EUIPO Trademark Search REST API (not the public web interface) and adds clearance risk scoring, composite similarity analysis (text + phonetic + token), lifecycle tracking, change detection across runs, and alert-ready output on top of the raw register data.

## How do I search EU trademarks?

Enter a trademark name and your own mark in the "Your Mark" field. EUIPO Trademark Search returns risk-scored results showing which existing marks pose a conflict, why they're risky, and what to do next. Use preset modes (clearance, monitoring, competitor) for one-click optimization.

## Can I check trademark expiry dates?

Yes. Every result includes `daysUntilExpiry` and a computed `lifecycleStage`. Marks within 365 days of expiry show RENEWAL_WINDOW; within 180 days, NEARING_EXPIRY. Schedule weekly runs to monitor your portfolio automatically.

## Can I search EU trademarks by applicant?

Yes. Set the `applicantName` filter to the company or person name. Wildcards are supported — `Adidas*` finds all marks filed by entities starting with "Adidas". Combine with `dateFrom` to track recent filings.

## Does this cover UK trademarks?

No. Since Brexit, UK trademarks are managed by the UK Intellectual Property Office (UKIPO). EUIPO Trademark Search covers the 27 current EU member states and international registrations designating the EU via the Madrid Protocol.

## How to check if a trademark is registered in the EU

The fastest way to check if a trademark is registered in the EU is to search the EUIPO database by name, class, or applicant. Tools like EUIPO Trademark Search can automate that process and add risk scoring, so you can immediately see whether your brand conflicts with existing registrations.

## Is there an API to search EU trademarks?

Yes. The EUIPO provides a Trademark Search API via its developer portal. The easiest way to use this API is through a ready-to-use implementation like EUIPO Trademark Search, which adds risk scoring, similarity analysis, and monitoring without requiring custom integration.

## How do I know if my brand name is safe to use in the EU?

The best way to check if your brand name is safe is to run a trademark clearance search against the EUIPO database and review similar marks in your Nice classes. EUIPO Trademark Search returns a risk score, verdict, and recommended action so you can quickly determine whether your brand is likely to face conflicts.

## How to monitor trademarks in the EU

The most effective way to monitor EU trademarks is to run automated searches against the EUIPO database and track new filings or changes over time. Tools like EUIPO Trademark Search support scheduled runs, detect new matches and status changes, and produce alert-ready output so you can monitor risks continuously without manual checks.

## How accurate is trademark similarity scoring?

The most reliable approach combines multiple signals: text similarity, phonetic analysis, and word-overlap matching. EUIPO Trademark Search uses all three to identify identical and near-identical names, but does not assess visual or conceptual similarity. Use it as a screening tool, not a legal determination.

## Can I search EU trademarks by company name?

Yes. The easiest way to search EU trademarks by company is to use the applicant name filter with wildcard matching. Enter "Adidas*" to return all trademarks filed by that entity.

## What is the best way to search EU trademarks?

The best way to search EU trademarks depends on your needs. The official EUIPO eSearch tool is suitable for manual one-off lookups. The fastest and most effective way to search, analyse risk, and monitor trademarks at scale is to use an automated tool like EUIPO Trademark Search, which adds similarity scoring, risk assessment, and alerting on top of the EUIPO database.

## How to search EU trademarks by name, class, or applicant

| Filter | How it works | Example |
| --- | --- | --- |
| Trademark name | Wildcard matching on verbal element. Auto-wrapped in `*query*` if no wildcards. | `NORTH*` finds marks starting with "NORTH" |
| Nice class | Classes 1-45, comma-separated for multiple | `9,25,42` |
| Status | 14 legal statuses | REGISTERED, UNDER_EXAMINATION, OPPOSITION_PENDING, EXPIRED, etc. |
| Applicant name | Owner/applicant with wildcard support | `Adidas*` |
| Mark type | 11 mark types | WORD, FIGURATIVE, SHAPE_3D, SOUND, etc. |
| Date range | Filing date from/to in YYYY-MM-DD | `2025-01-01` to `2025-12-31` |
| Batch queries | Up to 50 names in one run | `["Nike", "Adidas", "Puma"]` |
| Similarity scoring | Your own mark name for 0-100 comparison | `yourMark: "NorthStar Logistics"` |

## What data you get from an EU trademark search

Each trademark record includes registration data, risk intelligence, and monitoring fields:

```
{
    "applicationNumber": "018945321",
    "markName": "NORTHSTAR LOGISTICS",
    "applicantName": "Northstar Logistics GmbH",
    "niceClasses": "39, 42",
    "status": "REGISTERED",
    "lifecycleStage": "REGISTERED_ACTIVE",
    "isActive": true,
    "expiryDate": "2034-03-15",
    "daysUntilExpiry": 2912,
    "clearanceRisk": "HIGH",
    "riskScore": 82,
    "confidence": "HIGH",
    "verdict": "High risk — not recommended to file without legal review",
    "impact": "This may block registration or trigger opposition if filed",
    "riskFactors": ["High composite similarity (88/100)", "Nice class overlap with your search", "Active registration or pending application"],
    "compositeSimilarity": 88,
    "similarityScore": 87,
    "phoneticSimilarity": 92,
    "tokenSimilarity": 80,
    "classOverlap": true,
    "insight": "NORTHSTAR LOGISTICS is highly similar to \"NorthStar Logistics\" (88/100 composite), shares your Nice class, is registered.",
    "recommendedAction": "Review with trademark attorney before filing. High similarity with active mark in same class.",
    "alert": { "trigger": true, "severity": "HIGH", "reason": "High-risk match: NORTHSTAR LOGISTICS (88/100 similarity, same class)" },
    "changeType": "NEW_MATCH",
    "previousState": null,
    "euipoUrl": "https://euipo.europa.eu/eSearch/#basic/1+1+1+1/50+50+50+50/018945321"
}
```

**Intelligence fields** computed beyond raw EUIPO data:

- **verdict** — Quick human-readable decision: "High risk — not recommended to file without legal review"
- **riskScore** — Numeric 0-100 risk score (sortable, dashboard-ready). Weighted: similarity 50%, class overlap 30%, active status 20%
- **clearanceRisk** — HIGH, MEDIUM, LOW, or NONE classification
- **confidence** — Assessment confidence: HIGH (3 signals), MEDIUM (2), LOW (1)
- **impact** — Potential consequence: "This may block registration or trigger opposition if filed"
- **riskFactors** — Array of plain-English reasons explaining the risk level
- **compositeSimilarity** — Weighted score combining text (40%), phonetic/Soundex (35%), and word-overlap (25%)
- **insight** — Plain-English sentence explaining why this result matters
- **recommendedAction** — Concrete next step based on risk level
- **alert** — Structured alert object (trigger, severity, reason) for Slack, email, or Zapier
- **changeType** — What changed since last run: NEW_MATCH, STATUS_CHANGE, SIMILARITY_INCREASE
- **previousState** — Previous run's similarity and status for audit trail
- **lifecycleStage** — 7 stages from UNDER_EXAMINATION to TERMINATED

## Modes

Choose a preset mode or configure filters manually:

**Clearance mode** — Finds conflicts and ranks by risk. Auto-filters to active/registered marks. Set `yourMark` and `niceClass` for best results. Output sorted by risk score.

**Monitoring mode** — Detects new filings and changes over time. Stores state across runs. Flags NEW_MATCH, STATUS_CHANGE, and SIMILARITY_INCREASE. Schedule weekly for continuous protection.

**Competitor mode** — Tracks filings by company. Auto-filters to last 30 days. Set `applicantName` to the competitor you want to watch.

## Who should use it

**If you are a trademark attorney or IP paralegal,** use it for clearance searches. Enter your proposed mark in both the query and "Your Mark" fields to get similarity scores against existing registrations, filtered by relevant Nice classes.

**If you are a brand manager or franchise team,** use it for portfolio monitoring. Enter all your marks as batch queries and schedule weekly runs. The lifecycle stage and days-until-expiry fields flag marks entering the renewal window.

**If you are a competitive intelligence analyst,** use it for tracking competitor filings. Filter by applicant name and date range to detect new product launches or market entry signals.

**If you are doing M&A due diligence,** use it for IP audits. Batch-search the target company's known marks and review status, lifecycle stage, and expiry dates for a complete portfolio health check.

## Input parameters

| Parameter | Type | Required | Default | Description |
| --- | --- | --- | --- | --- |
| `query` | String | Yes | `"Nike"` | Trademark name to search. Supports `*` wildcards. |
| `queries` | String[] | No | — | Batch: up to 50 names in one run. Overrides `query`. |
| `yourMark` | String | No | — | Your mark name for similarity scoring + risk analysis. |
| `mode` | String | No | — | Preset: `clearance` (active marks, risk-sorted), `monitoring` (change detection), `competitor` (recent filings). |
| `niceClass` | String | No | — | Nice class 1-45. Comma-separated for multiple (e.g., `9,25,42`). |
| `status` | String | No | — | Legal status filter (REGISTERED, UNDER_EXAMINATION, EXPIRED, etc.). |
| `applicantName` | String | No | — | Owner/applicant name with wildcard support. |
| `markFeature` | String | No | — | Mark type (WORD, FIGURATIVE, SHAPE_3D, SOUND, etc.). |
| `dateFrom` | String | No | — | Filed on or after (YYYY-MM-DD). |
| `dateTo` | String | No | — | Filed on or before (YYYY-MM-DD). |
| `clientId` | String | Yes | — | EUIPO Developer Portal Client ID. Free at [dev.euipo.europa.eu](https://dev.euipo.europa.eu/). |
| `clientSecret` | String | Yes | — | EUIPO Developer Portal Client Secret. |
| `useSandbox` | Boolean | No | `false` | Use sandbox environment (test data). |
| `maxResults` | Integer | No | `25` | Maximum results to return (1-500). |
| `outputProfile` | String | No | `full` | Output verbosity: `minimal` (decision-only — mark/applicant/status/lifecycle/similarity/clearanceRisk/nextActionTag/summary), `standard` (above + filing/registration/expiry + similarity components), `llm` (decision + confidence + agentContract for AI consumers), `full` (every field). |
| `watchlistName` | String | No | — | Name this run as a separate watchlist. Cross-run state (`PREVIOUS_RESULTS` map for change detection) is namespaced per-watchlist, so the same actor runs as N independent monitors. |
| `webhookUrl` | String | No | — | Slack or Discord incoming webhook URL. Posts a rich embed on completion with portfolio totals + alerts + top blocking matches + a link to the run. Auto-detects vendor. |
| `circuitBreakerThreshold` | Integer | No | `0` | Reserved for future EUIPO 5xx failure-streak abort (per-page retry-with-backoff already retries up to 3 times). |
| `includeAgentContract` | Boolean | No | `true` | Add a top-level `agentContract` `{ decision, confidence, nextAction, costToAct }` to every record (and run-level on the SUMMARY) for MCP/AI-agent consumers. |

### Example inputs

**Clearance search with risk scoring:**

```
{
    "query": "Northstar",
    "yourMark": "NorthStar Logistics",
    "mode": "clearance",
    "niceClass": "39,42",
    "maxResults": 100,
    "clientId": "YOUR_EUIPO_CLIENT_ID",
    "clientSecret": "YOUR_EUIPO_CLIENT_SECRET"
}
```

**Batch portfolio monitoring:**

```
{
    "queries": ["Northstar", "Pinnacle", "Acme Corp", "Meridian"],
    "maxResults": 200,
    "clientId": "YOUR_EUIPO_CLIENT_ID",
    "clientSecret": "YOUR_EUIPO_CLIENT_SECRET"
}
```

**Competitor filing tracker:**

```
{
    "query": "*",
    "applicantName": "Northstar Logistics",
    "dateFrom": "2025-01-01",
    "maxResults": 50,
    "clientId": "YOUR_EUIPO_CLIENT_ID",
    "clientSecret": "YOUR_EUIPO_CLIENT_SECRET"
}
```

## How to search EU trademarks using the API

### Python

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")

run = client.actor("ryanclinton/euipo-trademark-search").call(run_input={
    "query": "Northstar",
    "yourMark": "NorthStar Logistics",
    "niceClass": "39,42",
    "maxResults": 50,
    "clientId": "YOUR_EUIPO_CLIENT_ID",
    "clientSecret": "YOUR_EUIPO_CLIENT_SECRET",
})

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(f"{item['applicationNumber']} | {item['markName']} | Score: {item.get('similarityScore', 'N/A')} | {item['lifecycleStage']}")
```

### JavaScript

```
import { ApifyClient } from "apify-client";

const client = new ApifyClient({ token: "YOUR_API_TOKEN" });

const run = await client.actor("ryanclinton/euipo-trademark-search").call({
    query: "Northstar",
    yourMark: "NorthStar Logistics",
    niceClass: "39,42",
    maxResults: 50,
    clientId: "YOUR_EUIPO_CLIENT_ID",
    clientSecret: "YOUR_EUIPO_CLIENT_SECRET",
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
for (const item of items) {
    console.log(`${item.applicationNumber} | ${item.markName} | Score: ${item.similarityScore ?? "N/A"} | ${item.lifecycleStage}`);
}
```

## How to do a trademark clearance search in the EU

Enter your proposed mark name in both the "Trademark Name" and "Your Mark" fields. Set Nice class filters matching your intended goods or services. EUIPO Trademark Search returns all matching marks with a 0-100 similarity score, sorted by relevance. Review high-scoring matches (above 70) to identify potential conflicts before filing. Export as CSV for your trademark attorney to review. Formal clearance requires an attorney's assessment of phonetic, visual, and conceptual similarity beyond what string-based scoring provides.

## How to monitor EU trademark expiry dates

Schedule EUIPO Trademark Search to run weekly with your portfolio marks as batch queries. Each result includes `lifecycleStage` and `daysUntilExpiry`. Filter for RENEWAL_WINDOW (within 365 days) and NEARING_EXPIRY (within 180 days) to identify marks needing renewal action. Connect to Zapier or Make to send automatic alerts when marks enter these stages.

## How much does it cost to search EU trademarks?

EUIPO Trademark Search uses pay-per-event pricing — you pay per trademark result returned (PPE event: `trademark-fetched`). Check the actor's pricing page on Apify for the current per-result rate.

The EUIPO API credentials are free — register at [dev.euipo.europa.eu](https://dev.euipo.europa.eu/). Apify's free tier includes $5 of monthly credits. Set a spending limit in your Apify account to control costs.

## How EUIPO Trademark Search compares to manual eSearch

| Capability | EUIPO Trademark Search | Manual EUIPO eSearch |
| --- | --- | --- |
| Output format | JSON, CSV, Excel via API | On-screen, PDF |
| Batch searching | Up to 50 queries per run | One at a time |
| Lifecycle tracking | 7 computed stages + days-until-expiry | Manual review |
| Similarity scoring | Levenshtein 0-100, auto-sorted | Not available |
| Nice class descriptions | Human-readable labels included | Codes only |
| Scheduling | Daily, weekly, or custom via Apify | Manual |
| API access | REST via Apify API | Not available |

## How it works under the hood

```
input (query | queries[] | yourMark | niceClass | applicantName | dateFrom/To | mode)
       │
       ▼
   OAuth2 client_credentials → EUIPO CAS access token
       │
       ▼
   build RSQL filter (verbal ==*q*; niceClasses=in=(...); status; dateFrom/To)
       │
       ▼
   paginate /trademarks (100/page, retry-with-backoff on 429/5xx)
       │
       ▼
  transform → lifecycleStage · similarity (Levenshtein + Soundex + Jaccard) · clearanceRisk · riskScore
       │
       ▼
  per-record premium fields:
    eventId · summary · confidenceComponents · nextActionTag · dataGaps · agentContract
       │
       ▼
  cross-run change detection (NEW_MATCH | STATUS_CHANGE | SIMILARITY_INCREASE)
       │
       ▼
  per-record decoration: insight · recommendedAction (prose) · verdict · impact · alert · rank · isBlockingRisk
       │
       ┌────────┴────────┐
       ▼                 ▼
   dataset            KV SUMMARY (portfolio + monitoring + alerts + run-level agentContract)
   per-record         KV OUTPUT (full deterministic shape, all profiles)
                      euipo-monitor-state[-watchlistName] (PREVIOUS_RESULTS map for change detection)
       │
       └─► optional Slack/Discord webhook (portfolio + alerts + top blocking)
```

1. **Authentication** — Sends a client credentials OAuth2 request to the EUIPO CAS server. Retries up to 3 times with backoff on network or server errors.
2. **Query construction** — Builds an RSQL filter from your parameters. Verbal element uses `*query*` wildcards. Multiple Nice classes use `niceClasses=in=(9,25,42)`. All filters combine with AND logic.
3. **Paginated retrieval** — Fetches results in pages of up to 100, sorted by application date descending. Handles HTTP 429 rate limits and 5xx server errors with automatic retry. For batch queries, the maxResults budget is distributed across queries.
4. **Transformation** — Maps EUIPO codes to human-readable labels, extracts English-preferred goods and services, computes lifecycle stage and similarity scores, generates eSearch links and image URLs.

## Premium output fields

Beyond the existing per-trademark fields, every record now includes:

| Field | Type | Description |
| --- | --- | --- |
| `recordType` | string | `trademark` for results, `summary` for the run summary record, `error` for failures. Use to filter the dataset. |
| `schemaVersion` | string | Output schema version (semver). Bumped on shape changes; safe to branch on. |
| `eventId` | string | Idempotent canonical id `sha256(watchlist::applicationNumber)`. Same id across re-runs — safe join key for downstream diffing. |
| `summary` | string | Plain-English one-line summary (≤280 chars). Drop into a Slack message, CRM note, or LLM context. |
| `confidenceComponents` | object[] | Confidence breakdown: signalStrength + classOverlapEvidence + activeStatus + dataRichness, each with `{ name, weight, value }`. |
| `nextActionTag` | string | Stable enum: `block-filing` | `proceed-with-caution` | `low-risk-monitor` | `low-risk-proceed` | `archive` | `unknown`. Use this for AI-agent routing alongside the existing prose `recommendedAction`. |
| `dataGaps` | object[] | `[{ field, reason, suggestedFix }]` listing per-record missing data with named upstream actors / input changes that fill the gap. |
| `agentContract` | object | `{ decision, confidence, nextAction, costToAct }` decision surface for MCP and AI-agent consumers (set when `includeAgentContract=true`). |

## KV store mirrors

Every run writes:

- **`SUMMARY` key** — totals + `portfolio` (active/expiring/risk counts) + `monitoring` (newMatches/statusChanges/isFirstRun) + `coverage` block + run-level `agentContract` decision surface + `alerts[]`. Best for triggering downstream actors with a single read.
- **`OUTPUT` key** — full deterministic per-trademark output (regardless of `outputProfile`) plus run-level `agentContract`, `coverage`, and the same `portfolio` block. Use when you need every field even though the dataset is filtered.
- **`euipo-monitor-state[-watchlistName]` named store** — `PREVIOUS_RESULTS` map of `{ applicationNumber → { status, highestSim } }` for cross-run change detection. Survives dataset purges. Watchlist namespacing lets the same actor run as N independent monitors.

## Stable enums

The actor commits to **additive-only** evolution of these enums (new values may be added in minor versions; existing values never removed or renamed):

- **`nextActionTag`** — `block-filing`, `proceed-with-caution`, `low-risk-monitor`, `low-risk-proceed`, `archive`, `unknown`
- **`clearanceRisk`** — `HIGH`, `MEDIUM`, `LOW`, `NONE` (existing)
- **`confidence`** (legacy string field) — `HIGH`, `MEDIUM`, `LOW`
- **`agentContract.decision`** — `qualified-A`, `qualified-B`, `review`, `low-priority`, `reject`
- **`lifecycleStage`** (existing) — `REGISTERED_ACTIVE`, `NEARING_EXPIRY`, `RENEWAL_WINDOW`, `PENDING_REGISTRATION`, `UNDER_EXAMINATION`, `EXPIRED`, `TERMINATED`
- **`changeType`** (existing) — `NEW_MATCH`, `STATUS_CHANGE`, `SIMILARITY_INCREASE`, or `null` if no change
- **`alert.severity`** (existing) — `HIGH`, `MEDIUM`, `LOW`
- **`recordType`** — `trademark`, `summary`, `error`
- **`failureType`** (error records) — `invalid-input`, `blocked`, `no-data`, `parse-error`

Branching on these in Dify, n8n, Make, or your own code is safe across `schemaVersion` minor bumps.

## Limits and caveats

- **Credentials required** — Free EUIPO Developer Portal Client ID and Client Secret needed. Register at [dev.euipo.europa.eu](https://dev.euipo.europa.eu/). Production API access may require EUIPO review; sandbox access is available for immediate testing.
- **EU trademarks only** — Covers EU trademarks and international registrations designating the EU. Does not cover national registers (UK IPO, USPTO, DPMA, INPI, etc.).
- **500 results per run** — For larger datasets, use narrower date ranges or Nice class filters across multiple runs.
- **Text search only** — Queries match the verbal (word) element. Cannot search by image similarity for figurative marks.
- **Similarity does not assess visual or conceptual similarity** — The composite score covers text, phonetic (Soundex), and word overlap, but does not evaluate visual resemblance of figurative marks or conceptual association. Use as a screening tool, not a legal determination.
- **Rate limits** — The EUIPO API enforces rate limits. Retries are automatic, but large batch runs may experience delays.
- **Image URLs may require auth** — The `markImageUrl` points to the EUIPO API thumbnail endpoint, which may need authentication headers outside this actor.

## FAQ

**Can I search EU trademarks by image or logo?**
No. EUIPO Trademark Search queries the verbal (word) element. You can filter by mark type "Figurative" and review `markImageUrl` thumbnails, but the search itself is text-based.

**What Nice classes should I search for software?**
Class 9 covers computer software and downloadable applications. Class 42 covers SaaS, cloud computing, and IT services. Class 35 covers advertising and business management. Many software companies register across all three.

**Is the EUIPO API free?**
The EUIPO Developer Portal credentials are free and EUIPO does not charge per API query. EUIPO Trademark Search charges per trademark result through Apify's pay-per-event model.

**How accurate is the similarity scoring?**
The composite score combines three signals: text similarity (Levenshtein), phonetic similarity (Soundex — catches "NIKE" vs "NYKE"), and word-overlap (catches reorderings like "NORTH STAR" vs "STAR NORTH"). A composite of 100 means identical across all signals. Scores above 80 indicate high risk. The scoring does not evaluate visual similarity or conceptual association. Use it for screening, not legal determination.

**What does the lifecycle stage mean?**
UNDER_EXAMINATION (application under review), PENDING_REGISTRATION (published or in opposition), REGISTERED_ACTIVE (registered, more than 365 days until expiry), RENEWAL_WINDOW (within 365 days of expiry), NEARING_EXPIRY (within 180 days), EXPIRED, TERMINATED (refused, withdrawn, cancelled, or surrendered).

**Can I export results to Google Sheets or Excel?**
Yes. Download as JSON, CSV, or Excel from the Apify console. Use the Google Sheets integration for automatic export, or connect via Zapier or Make for scheduled exports.

**Is it legal to search the EUIPO trademark database?**
EU trademark registrations are public records. EUIPO provides a public API for programmatic access. Legitimate uses include clearance, monitoring, research, and due diligence. Consult legal counsel if your use case involves bulk data redistribution or commercial resale.

## Troubleshooting

**Authentication fails (401/403).** Verify your Client ID and Client Secret. Confirm you subscribed to the "Trademark Search" API product in the EUIPO Developer Portal. Check that you are not using production credentials with sandbox mode or vice versa.

**No results for a known trademark.** Try broader wildcards or remove restrictive filters. Sandbox data differs from production data.

**Run times out on large batches.** Reduce batch size or lower maxResults. For large portfolios, split into runs of 10-20 queries each.

**Similarity scores seem off.** The Levenshtein score measures character edits, not phonetic or conceptual similarity. For formal clearance opinions, consult a trademark attorney.

## Responsible use

EUIPO Trademark Search connects to the official EUIPO Trademark Search REST API and accesses public register data in accordance with EUIPO's developer portal terms of service. Users are responsible for compliance with applicable laws, EUIPO API usage policies, and data protection regulations. Trademark search results are informational — consult a qualified IP attorney for legal interpretation, filing decisions, or enforcement actions.

## Support

Found a bug or have a feature request? Open an issue in the [Issues tab](https://console.apify.com/actors/YOUR_ACTOR_ID/issues) on this actor's page.