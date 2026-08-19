---
name: Investigate wireless client experience
description: Trace a degraded wireless client or SSID on a Catalyst Center controller from the client record through its assurance events and the AAA, DHCP and DNS services behind it.
api: openapi/cisco-catalyst-center-clients1-openapi.yml
operations:
  - readClients
  - readClientById
  - readClientsCount
  - queryClients
  - clientTrendAnalyticsById
  - queryClientsTopNAnalytics
  - readEvents
  - readEventDetails
  - readEventChildren
  - readAAAServices
  - readDHCPServices
  - readDNSServices
generated: '2026-08-19'
method: generated
source: openapi/cisco-catalyst-center-clients1-openapi.yml, openapi/cisco-catalyst-center-assurance-events-openapi.yml, openapi/cisco-catalyst-center-aaaservices-openapi.yml
---

# Investigate wireless client experience

A wireless complaint is almost never about the client. It is about the AP, the SSID, or one of the three services
every association depends on. Work outward, in that order.

## 1. Authenticate

`POST /dna/system/api/v1/auth/token` with HTTP Basic, then `X-Auth-Token` on everything after. 60-minute lifetime.

## 2. Find the clients, ranked

`queryClientsTopNAnalytics` over the complaint window (`startTime`/`endTime` in UTC epoch milliseconds), scoped by
`siteHierarchyId` and optionally `ssid`, gives you the worst-experience clients immediately. `readClientsCount`
first tells you the size of the population you are ranking inside.

Clients are keyed by **MAC address**, not UUID — `clientMac` / `macAddress`. That is the single most common mistake
when moving between this surface and the device surface, which uses UUIDs.

## 3. Read one client and its trend

`readClientById` for the record, `clientTrendAnalyticsById` for the time series. A client that is bad continuously
and a client that is bad every morning at 09:00 are different problems with different owners.

Use `queryClients` (POST filter document) when you need to slice by several facets at once — SSID plus band plus
health, say — instead of stacking query parameters.

## 4. Pull the events

`readEvents` filtered by `clientMac` and the same window, `readEventDetails` for a specific event, and
`readEventChildren` to expand a wireless client event into the onboarding steps underneath it. The child events are
where association, authentication and DHCP timing actually show up.

## 5. Check the three services

If onboarding is failing rather than performing badly, the answer is usually in one of:

- `readAAAServices` — authentication latency and failures
- `readDHCPServices` — address assignment latency and failures
- `readDNSServices` — resolution latency and failures

Each has a `*Count` sibling and `query*SummaryAnalytics` / `query*TrendAnalytics` / `query*TopNAnalytics`
projections. Compare the service trend against the client trend over the same window before blaming the radio.

## Rules

- Time is **UTC epoch milliseconds** everywhere. Do not send ISO 8601.
- Page with `limit` (max 500) and `offset` (1-based); ask the `/count` operation first.
- `429` means the controller rate limiter fired (default roughly 100 requests/minute). No `Retry-After` is sent —
  back off on your own schedule.
- This whole flow is read-only. Keep it that way: the shipped Catalyst Center MCP bundle contains write operations
  and enforces no read-only mode, so an agent must impose the boundary itself.
