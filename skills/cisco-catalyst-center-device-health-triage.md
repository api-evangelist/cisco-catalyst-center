---
name: Triage unhealthy network devices at a site
description: Authenticate to a Catalyst Center controller, find network devices with degraded health inside a site, and pull the trend and issue context an engineer needs to act.
api: openapi/cisco-catalyst-center-assurance-network-devices-openapi.yml
operations:
  - readNetworkDevices
  - readNetworkDevicesCount
  - readNetworkDeviceById
  - queryNetworkDevicesWithFilter
  - queryNetworkDevicesTopNAnalytics
  - readDeviceTrendAnalytics
  - readIssues
  - readIssueById
generated: '2026-08-19'
method: generated
source: openapi/cisco-catalyst-center-assurance-network-devices-openapi.yml, openapi/cisco-catalyst-center-issues-list-openapi.yml
---

# Triage unhealthy network devices at a site

Catalyst Center is a **customer-deployed controller**. There is no shared vendor host — every call goes to the
customer's own appliance, `https://{catalyst-center-host}`. Cisco's always-on DevNet sandbox
(`sandboxdnac.cisco.com`) is a valid target for practice.

## 1. Get a token first

Every call needs one. `POST /dna/system/api/v1/auth/token` with HTTP Basic credentials returns an opaque token.
Send it as the `X-Auth-Token` header on every subsequent request. **The token lives 60 minutes**; a 401 means it
expired and you must re-authenticate, not that the credentials are wrong.

## 2. Scope by site, then by health

Do not page the whole inventory. Use `readNetworkDevices` with `siteHierarchyId` (or `siteId`) plus
`startTime`/`endTime` as **UTC epoch milliseconds**. Omitting the time window defaults to roughly the last 30
minutes, which is usually what you want for "right now" and never what you want for "what happened overnight".

Call `readNetworkDevicesCount` with the same filters before paging so you know whether the answer is 12 devices or
1,200. Page with `limit` (max 500) and `offset` (1-based).

For anything richer than a flat facet — several health categories, several device roles, a negation — POST the
filter document to `queryNetworkDevicesWithFilter` rather than trying to express it in the query string.

## 3. Rank instead of scanning

`queryNetworkDevicesTopNAnalytics` returns the ranked slice directly. Use it to answer "which ten devices are worst"
without pulling every record and sorting client-side.

## 4. Read the single device, then its trend

`readNetworkDeviceById` gives the current record. `readDeviceTrendAnalytics` gives the time series — use it to
separate a device that has been degraded for a week from one that fell over ten minutes ago. That distinction is the
whole point of the triage.

## 5. Attach the issues

`readIssues` filtered by the same site and time window, then `readIssueById` for the ones that matter, gives the
suggested-action text Catalyst Center already computed. Report those rather than inventing remediation.

## Rules

- **Never assume idempotency.** Catalyst Center publishes no idempotency key. Write operations return a `taskId` you
  poll; a replayed POST creates a *second* task. Do not retry a write blindly.
- **Respect the rate limit.** The controller default is about 100 requests per minute and returns `429` on
  exhaustion, with no `RateLimit-*` or `Retry-After` headers to guide you. Back off on 429 rather than tightening a
  retry loop.
- **`403` is a permissions answer, not a bug.** Tools run with the permissions of the account whose credentials were
  exchanged for the token. There is no scope model to narrow.
- **Errors are thin.** Only 400, 404 and 500 carry a JSON body schema in the published contract. For 401, 403, 409
  and the 5xx family you get a status code and nothing parseable — do not expect a structured error object.
- Send `X-CALLER-ID` so the customer can correlate your activity in their own audit trail.
