---
name: Report site, fabric and energy health across a hierarchy
description: Build a rolled-up health, KPI and energy report across the Catalyst Center site hierarchy, including SD-Access fabric and virtual/transit network summaries.
api: openapi/cisco-catalyst-center-site-health-summaries-openapi.yml
operations:
  - readSiteHealthSummaries
  - readSiteHealthSummaryById
  - readSiteHealthTrendById
  - readSiteCount
  - readSiteKpiSummaries
  - readSiteKpiSummariesById
  - querySiteKpiSummariesTrendAnalyticsTask
  - readFabricSitesSummary
  - readFabricSitesSummaryById
  - readFabricSitesTrendById
  - readVirtualNetworksSummary
  - readTransitNetworksSummary
  - readFabricSummary
  - readSitesEnergy
  - querySitesEnergyTask
  - readNetworkDevicesEnergy
generated: '2026-08-19'
method: generated
source: openapi/cisco-catalyst-center-site-health-summaries-openapi.yml, openapi/cisco-catalyst-center-site-kpi-summaries-openapi.yml, openapi/cisco-catalyst-center-fabric-site-health-summaries-openapi.yml, openapi/cisco-catalyst-center-sites-energy-openapi.yml
---

# Report site, fabric and energy health across a hierarchy

The Catalyst Center site hierarchy — area, building, floor — is the spine of every rollup. Resolve it first, then
hang each metric family off it.

## 1. Authenticate and resolve the hierarchy

Token first (`POST /dna/system/api/v1/auth/token`, then `X-Auth-Token`). `readSiteCount` gives you the size of the
hierarchy; `readSiteHealthSummaries` walks it. `siteHierarchyId` is a slash-delimited ancestor path — use it to scope
a report to one building without enumerating its children yourself.

## 2. Health, then KPI

- `readSiteHealthSummaries` / `readSiteHealthSummaryById` — the health rollup
- `readSiteHealthTrendById` — the same site over time
- `readSiteKpiSummaries` / `readSiteKpiSummariesById` — the KPI surface

Use the `attribute` parameter (repeatable) to select only the fields the report actually prints, and `view` for the
named projections. Both cut payload substantially on a wide hierarchy.

## 3. Long-running analytics are asynchronous

`querySiteKpiSummariesTrendAnalyticsTask` and `querySitesEnergyTask` create an analytics **task** and return a
`taskId`. Poll with the matching read operation using that `taskId` — do not re-POST while waiting, because there is
no idempotency key and a second POST creates a second task.

`readAssuranceTasks`, `readAssuranceTaskById` and `readAssuranceTaskCount` are the generic task-status operations.

## 4. Fabric, virtual and transit networks

For SD-Access deployments:

- `readFabricSummary` — the top-level fabric picture
- `readFabricSitesSummary` / `readFabricSitesSummaryById` / `readFabricSitesTrendById`
- `readVirtualNetworksSummary` and `readTransitNetworksSummary`

Skip this whole section for a non-fabric deployment rather than reporting empty fabric sections as a finding.

## 5. Energy

`readSitesEnergy` rolls energy to the site; `readNetworkDevicesEnergy` breaks it down per device. `countSitesEnergy`
before paging. Energy is the newest of these surfaces — treat a missing field as "this controller release does not
emit it yet", not as a zero.

## Rules

- Every collection has a `/count` sibling. Call it before paging; there is no total in the page envelope.
- `limit` maxes at 500, `offset` is 1-based.
- Time windows are UTC epoch milliseconds. Wide windows on trend operations are the most common cause of `504`.
- Back off on `429`; the controller default is roughly 100 requests per minute and no rate-limit headers are sent.
- Report only what the controller returns. Health scores are Cisco's computed values — do not recompute or
  reinterpret them.
