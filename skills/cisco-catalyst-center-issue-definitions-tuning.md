---
name: Tune issue and health score definitions
description: Read and adjust Catalyst Center system issue definitions, custom issue definitions and health score definitions, and resolve or ignore the issues they generate.
api: openapi/cisco-catalyst-center-issue-and-health-definitions-openapi.yml
operations:
  - readSystemsIssueDefinitions
  - readSystemIssueDefinitionById
  - putSystemIssueDefinitionById
  - readSystemIssueDefinitionsCount
  - readHealthDefinitions
  - readHealthDefinitionById
  - putHealthDefinitionById
  - postHealthDefinitions
  - readCustomIssueDefinitions
  - postCustomIssueDefinitions
  - readCustomIssueDefinitionById
  - putCustomIssueDefinitionById
  - deleteCustomIssueDefinitionById
  - resolveIssues
  - ignoreIssues
  - updateIssue
generated: '2026-08-19'
method: generated
source: openapi/cisco-catalyst-center-issue-and-health-definitions-openapi.yml, openapi/cisco-catalyst-center-assurance-user-defined-issue-apis-openapi.yml, openapi/cisco-catalyst-center-issues-lifecycle-openapi.yml
---

# Tune issue and health score definitions

This is the one Assurance flow that **writes**. Treat it accordingly.

## 1. Authenticate

Token first, `X-Auth-Token` after. 60 minutes.

## 2. Read before you write, always

- `readSystemsIssueDefinitions` / `readSystemIssueDefinitionById` — Cisco's built-in issue triggers
- `readHealthDefinitions` / `readHealthDefinitionById` — the health scoring rules
- `readCustomIssueDefinitions` / `readCustomIssueDefinitionById` — customer-authored triggers

Capture the current definition body before modifying it. There is no version history operation on this surface and
no way to diff a change after the fact from the API.

## 3. Modify deliberately

- `putSystemIssueDefinitionById` — change a threshold or enable/disable a built-in trigger
- `putHealthDefinitionById`, `postHealthDefinitions` — health scoring rules
- `postCustomIssueDefinitions`, `putCustomIssueDefinitionById`, `deleteCustomIssueDefinitionById` — customer triggers
- `bulkUpdateApplicationHealthDefinitions` and `updateApplicationHealthDefinitionById` — application health scoring

Changing a definition changes what the whole controller reports as unhealthy, for every operator, immediately. State
the blast radius before executing, and confirm.

## 4. Issue lifecycle

`resolveIssues`, `ignoreIssues` and `updateIssue` act on issue *instances*, not definitions. Resolving an issue that
the underlying condition still triggers will simply reopen it — fix the condition or tune the definition instead of
resolving repeatedly.

## Rules

- **No idempotency key exists.** A retried `postCustomIssueDefinitions` creates a duplicate definition. If a write
  times out, read the collection back and check before retrying.
- `409` on this surface means a concurrent edit. Re-read the definition and reapply rather than forcing the write.
- `403` means the account lacks the role. There is no scope to request — the operator must change the account.
- The published contract carries no response body schema for 401, 403, 405, 409 or 415, so failures on this surface
  return a status code and little else. Log the status and the operation, not a parsed error object.
- Only 400, 404 and 500 have JSON error schemas in the specification.
