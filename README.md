# Cisco Catalyst Center

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Cisco Catalyst Center, formerly DNA Center, is Cisco's intent-based networking controller for enterprise campus, branch and wireless networks. It covers network design and hierarchy, device discovery and provisioning, software image management, SD-Access fabric, policy, telemetry and Assurance analytics. Catalyst Center exposes a northbound REST Intent API under /dna/intent/api/v1 plus an Assurance data API under /dna/data/api/v1, authenticated with an X-Auth-Token bearer token obtained from a Basic-auth token endpoint. Cisco publishes 27 OpenAPI 3.0 documents for the Assurance surface in the cisco-en-programmability GitHub organization, a first-party open-source MCP server bundling 516 generated Catalyst Center API tools, Python and Go SDKs, Ansible collections and a Terraform provider. The controller is customer-deployed, so the API base URL is the customer's own appliance host; Cisco runs always-on DevNet sandboxes for anonymous evaluation.

**Areas:** Network Automation · Intent-Based Networking · Networking · Assurance · Enterprise · Campus · Wireless · SD-Access · Network Management · Observability · Telemetry · MCP

## Cisco Catalyst Center on APIs.io

Everything profiled for Cisco Catalyst Center is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/cisco-catalyst-center/](https://apis.io/providers/cisco-catalyst-center/)** — or go straight to one of the APIs or properties below.

### APIs (30)

- [Cisco Catalyst Center MCP Server](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-mcp-server/) — First-party open-source Model Context Protocol server for Catalyst Center, published by Cisco under Apache-2.0 at cisco-en-programmability/catc-mcp-oss. It…
- [Cisco Catalyst Center AAA Services API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-aaa-services-api/) — Operations related to Catalyst Center - Assurance Network Services
- [Cisco Catalyst Center Application Health Score Definitions API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-applicationhealthscoredefinitions-api/) — Operations related to application health score definitions.
- [Cisco Catalyst Center Assurance Events API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-assuranceevents-api/) — APIs related to assurance events
- [Cisco Catalyst Center Assurance Tasks API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-assurancetasks-api/) — Operations related to retrieving information regarding assurance tasks
- [Cisco Catalyst Center Clients API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-clients-api/) — Operations related to Catalyst Center - Assurance Network Clients
- [Cisco Catalyst Center Custom Issue Definitions API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-customissuedefinitions-api/) — Assurance Custom issue definition API documentation
- [Cisco Catalyst Center DHCP Services API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-dhcp-services-api/) — Operations related to Catalyst Center - Assurance Network Services
- [Cisco Catalyst Center Direct Deploy API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-direct-deploy-api/) — APIs to deploy ICAP configurations without previewing the intents.
- [Cisco Catalyst Center DNS Services API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-dns-services-api/) — Operations related to Catalyst Center - Assurance Network Services
- [Cisco Catalyst Center Energy API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-energy-api/) — Operations related to retrieving overall energy information for Catalyst Center Devices
- [Cisco Catalyst Center Fabric Site Health Summaries API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-fabricsitehealthsummaries-api/) — The fabricSiteHealthSummaries API from Cisco Catalyst Center — 4 operation(s) for fabricsitehealthsummaries.
- [Cisco Catalyst Center Fabric Summary API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-fabricsummary-api/) — The fabricSummary API from Cisco Catalyst Center — 1 operation(s) for fabricsummary.
- [Cisco Catalyst Center Filter Group Associations API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-filtergroupassociations-api/) — The filterGroupAssociations API from Cisco Catalyst Center — 2 operation(s) for filtergroupassociations.
- [Cisco Catalyst Center Filter Groups API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-filtergroups-api/) — Filter Group is a collection of predefined filters. When this Filter Group is associated with an entity, those filters are applied on that entity.This APIs…
- [Cisco Catalyst Center Icap API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-icap-api/) — Operations related to Catalyst Center - Assurance Intelligent Capture
- [Cisco Catalyst Center Interface List API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-interfacelist-api/) — The interfaceList API from Cisco Catalyst Center — 6 operation(s) for interfacelist.
- [Cisco Catalyst Center Issues API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-issues-api/) — Operations related to Catalyst Center - Assurance Issues
- [Cisco Catalyst Center Network Applications API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-networkapplications-api/) — Operations related to Catalyst Center - Appx Network Applications
- [Cisco Catalyst Center Preview Deploy API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-preview-deploy-api/) — APIs to preview, approve, and cancel (discard) ICAP provisioning intents.
- [Cisco Catalyst Center Resource API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-resource-api/) — APIs to retrieve the resources that were previewed or deployed.
- [Cisco Catalyst Center Site Analytics API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-siteanalytics-api/) — The siteAnalytics API from Cisco Catalyst Center — 8 operation(s) for siteanalytics.
- [Cisco Catalyst Center Site Health Summaries API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-sitehealthsummaries-api/) — Operations related to retrieving overall health information for Catalyst Center Sites
- [Cisco Catalyst Center Status API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-status-api/) — APIs to check the status of ICAP deployment operation.
- [Cisco Catalyst Center System Issue And Health Score Definitions API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-systemissueandhealthscoredefinitions-api/) — Operations related to system issue trigger definitions and health score definitions.
- [Cisco Catalyst Center Thousand Eyes Path Trace API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-thousandeyespathtrace-api/) — Operations related to path traces for ThousandEyes test results
- [Cisco Catalyst Center Thousand Eyes Test Results API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-thousandeyestestresults-api/) — Operations related to ThousandEyes test results
- [Cisco Catalyst Center Transit Network Health Summaries API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-transitnetworkhealthsummaries-api/) — The transitNetworkHealthSummaries API from Cisco Catalyst Center — 4 operation(s) for transitnetworkhealthsummaries.
- [Cisco Catalyst Center Virtual Network Health Summaries API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-virtualnetworkhealthsummaries-api/) — The virtualNetworkHealthSummaries API from Cisco Catalyst Center — 4 operation(s) for virtualnetworkhealthsummaries.
- [Cisco Catalyst Center Network Devices API](https://apis.io/apis/cisco-catalyst-center/cisco-catalyst-center-network-devices-api/) — Operations related to Catalyst Center - Gets the Network Device details

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Cisco Catalyst Center Webhooks](https://apis.io/asyncapis/cisco-catalyst-center/cisco-catalyst-center-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [catalyst-center](https://apis.io/servers/cisco-catalyst-center/catalyst-center/)

#### Overlays (27)

OpenAPI overlays, including conversational phrasing for each operation.

- [Cisco Catalyst Center Aaaservices Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-aaaservices-overlay/)
- [Cisco Catalyst Center Application Health Score Definitions Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-application-health-score-definitions-overlay/)
- [Cisco Catalyst Center Assurance Events Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-assurance-events-overlay/)
- [Cisco Catalyst Center Assurance Network Devices Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-assurance-network-devices-overlay/)
- [Cisco Catalyst Center Assurance Tasks Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-assurance-tasks-overlay/)
- [Cisco Catalyst Center Assurance User Defined Issue Apis Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-assurance-user-defined-issue-apis-overlay/)
- [Cisco Catalyst Center Clients1 Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-clients1-overlay/)
- [Cisco Catalyst Center Device Energy Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-device-energy-overlay/)
- [Cisco Catalyst Center Dhcpservices Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-dhcpservices-overlay/)
- [Cisco Catalyst Center Dnsservices Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-dnsservices-overlay/)
- [Cisco Catalyst Center Fabric Site Health Summaries Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-fabric-site-health-summaries-overlay/)
- [Cisco Catalyst Center Fabric Summary Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-fabric-summary-overlay/)
- [Cisco Catalyst Center Filter Groups Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-filter-groups-overlay/)
- [Cisco Catalyst Center Icap Apis Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-icap-apis-overlay/)
- [Cisco Catalyst Center Icap Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-icap-overlay/)
- [Cisco Catalyst Center Interfaces Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-interfaces-overlay/)
- [Cisco Catalyst Center Issue And Health Definitions Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-issue-and-health-definitions-overlay/)
- [Cisco Catalyst Center Issues Lifecycle Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-issues-lifecycle-overlay/)
- [Cisco Catalyst Center Issues List Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-issues-list-overlay/)
- [Cisco Catalyst Center Network Applications Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-network-applications-overlay/)
- [Cisco Catalyst Center Site Health Summaries Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-site-health-summaries-overlay/)
- [Cisco Catalyst Center Site Kpi Summaries Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-site-kpi-summaries-overlay/)
- [Cisco Catalyst Center Sites Energy Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-sites-energy-overlay/)
- [Cisco Catalyst Center Thousand Eyes Path Viz Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-thousand-eyes-path-viz-overlay/)
- [Cisco Catalyst Center Thousand Eyes Test Results Overlay](https://apis.io/overlays/cisco-catalyst-center/cisco-catalyst-center-thousand-eyes-test-results-overlay/)
- …and 2 more published on APIs.io

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Cisco Catalyst Center Authentication](https://apis.io/security/cisco-catalyst-center/cisco-catalyst-center-authentication/)
- [Cisco Catalyst Center Domain Security](https://apis.io/security/cisco-catalyst-center/cisco-catalyst-center-domain-security/)
- [Cisco Catalyst Center Trust Center](https://apis.io/security/cisco-catalyst-center/cisco-catalyst-center-trust-center/)
- [Cisco Catalyst Center Vulnerability Disclosure](https://apis.io/security/cisco-catalyst-center/cisco-catalyst-center-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Cisco Catalyst Center Plans Pricing](https://apis.io/plans/cisco-catalyst-center/cisco-catalyst-center-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Cisco Catalyst Center Rate Limits](https://apis.io/rate-limits/cisco-catalyst-center/cisco-catalyst-center-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.cisco.com/)
- [Documentation](https://developer.cisco.com/docs/catalyst-center/)
- [Getting started](https://developer.cisco.com/docs/catalyst-center/getting-started/)
- [API reference](https://developer.cisco.com/docs/catalyst-center/)
- [Pricing](https://www.cisco.com/site/us/en/products/networking/catalyst-center/index.html)
- [Sign up](https://id.cisco.com/signin/register)
- [Support](https://community.cisco.com/t5/cisco-catalyst-center/bd-p/discussions-dna-center)
- [Changelog](https://developer.cisco.com/docs/catalyst-center/api-changelog/)
- [Blog](https://blogs.cisco.com/tag/catalyst-center)
- [Security](https://sec.cloudapps.cisco.com/security/center/resources/security_vulnerability_policy.html)
- [Compliance](https://trustportal.cisco.com/c/r/ctp/trust-portal.html)
- [Terms of service](https://www.cisco.com/c/en/us/about/legal/cloud-and-software/end_user_license_agreement.html)
- [Privacy policy](https://www.cisco.com/c/en/us/about/legal/privacy-full.html)
- [GitHub](https://github.com/cisco-en-programmability)

## API Evangelist rating

**Kin Score 58.8** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 57.4 |
| Contract governance | 4.5 |
| Operational transparency | 65.8 |
| Developer ergonomics | 73.2 |
| Access clarity | 60.5 |

**Agent readiness 37.7** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | mostly |

**Regulatory alignment 35.3** — Education & Research

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/cisco-catalyst-center/](https://apis.io/providers/cisco-catalyst-center/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Cisco Catalyst Center: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/cisco-catalyst-center/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
