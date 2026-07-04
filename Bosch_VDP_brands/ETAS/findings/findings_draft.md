# ETAS - deep passive recon findings

## Methodology and safety
- Passive-only OSINT: official ETAS/Bosch pages, public documentation/download pages, robots/sitemap references, app-store metadata, and Certificate Transparency via Cert Spotter API.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, account creation, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## VDP / disclosure scope guardrails
- ETAS is a Bosch brand target, so vulnerability handling should follow Bosch PSIRT Responsible Disclosure Policy and the user-provided Bugcrowd Standard Disclosure Terms.
- Bosch PSIRT asks for coordinated disclosure, confidentiality until remediation, and reports via PSIRT channels; its listed contact is `psirt@bosch.com`.
- Bugcrowd standard terms emphasize that testing should only occur on systems listed under an applicable program brief / Targets section, with other systems treated as out of scope.
- Current recon remains pre-testing and passive-only; hostnames below are leads for scope confirmation, not authorization.

## Scope/ownership notes
- Automotive software, middleware, cybersecurity, licensing, downloads, and docs ecosystem.
- Candidate root domains observed from official/public metadata: `etas.com`, `docs.etas.com`, `license.etas.com`, `edge.etas.com` subtrees.
# ETAS - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Automotive software, middleware, cybersecurity, licensing, downloads, and docs ecosystem.
- Candidate root domains observed from official/public metadata: etas.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

### Core and marketing
- `etas.com`
- `www.etas.com`
- `brand.etas.com`
- `forms.etas.com`
- `go.etas.com`
- `info.etas.com`
- `click.info.etas.com`
- `image.info.etas.com`
- `view.info.etas.com`
- `mta-sts.etas.com`

### API / edge / cloud-looking surfaces
- `api.etas.com`
- `edge.etas.com`
- `api.edge.etas.com`
- `admin-api.edge.etas.com`
- `api-iot.edge.etas.com`
- `api-sf.edge.etas.com`
- `portal.edge.etas.com`
- `portal-sf.edge.etas.com`
- `sf.edge.etas.com`
- `artifactory.edge.etas.com`
- `device-uploads.edge.etas.com`
- `kafka-ui.edge.etas.com`
- `nifi.edge.etas.com`
- `rollout.edge.etas.com`
- `twin.edge.etas.com`
- `mobility-qa-cp-files.edge.etas.com`
- `mobility-qa-feu-files.edge.etas.com`
- `as2.platform.cloudhub.etas.com`
- `as2.portal.cloudhub.etas.com`
- `as2.project.cloudhub.etas.com`
- `auth.infra.cloudway.etas.com`

### License / support / security-product-looking surfaces
- `license.etas.com`
- `licensetest.etas.com`
- `fnoassist.license.etas.com`
- `etas.com`
- `www.etas.com`
- `api.etas.com`
- `api.edge.etas.com`
- `portal.edge.etas.com`
- `edge.etas.com`
- `license.etas.com`
- `licensetest.etas.com`
- `opensource.etas.com`
- `cycurguard.etas.com`
- `cycurguard-dev.etas.com`
- `cycurguard-test.etas.com`
- `findingdb.sec.etas.com`
- `pmant.sec.etas.com`
- `opensource.etas.com`
- `rtahotline.etas.com`
- `commonui.etas.com`
- `ccf-services-001.etas.com`
- `rm.etas.com`
- `rm-q.etas.com`
- `xac.etas.com`

### Research / emerging CT leads
- `model-farm.llm-gateway.research.etas.com`
- `bosch-model-farm.llm-gateway.research.etas.com`

## Historical CT delta snapshot
- Cert Spotter passive query for `etas.com` returned 100 recent certificate issuance entries and 48 unique hostnames in the sampled response.
- Year distribution in that response: 69 issuance entries with `not_before` in 2025 and 31 with `not_before` in 2026.
- Recent 2026 CT additions/refreshes worth tracking passively: `bosch-model-farm.llm-gateway.research.etas.com`, `model-farm.llm-gateway.research.etas.com`, `fnoassist.license.etas.com`, `admin-api.edge.etas.com`, `mobility-qa-cp-files.edge.etas.com`, `mobility-qa-feu-files.edge.etas.com`, `portal.edge.etas.com`, `api.edge.etas.com`, `findingdb.sec.etas.com`, and `pmant.sec.etas.com`.
- Recommended next passive delta work: rerun CT snapshots weekly, diff unique DNS names, and separate new hosts into `core`, `docs/downloads`, `license`, `edge/cloud`, `security-product`, and `research` buckets before any scope request.

## Public downloads and docs pivots
- Main site: https://www.etas.com/ww/en/
- Downloads landing page: https://www.etas.com/ww/en/downloads/
- Software download overview: https://www.etas.com/ww/en/downloads/software-downloads-overview/
- Online documentation hub: https://docs.etas.com/
- Example docs categories from the documentation hub: ASCMO-MOCA, ASCMO-STATIC & ASCMO-DYNAMIC, CycurRISK, Data Operator, EATB, EHANDBOOK, INCA, LiMa & FNO, MC-Gateway, MDA, and XCT.
- License Manager download page: https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/
- Cybersecurity/fuzzing download page: https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/
- Example public PDF/manual pivots found through search: RTA-FBL STLA user manuals, RTA-FBL STANDARD port user manual, GM port user guide, and HSP Getting Started.

## Robots and sitemap references
- `https://www.etas.com/robots.txt` is present and references `https://www.etas.com/ww/sitemap.xml`; it disallows `/static/`, `/media/etas_tech/etas_fonts/`, `/media/etas_tech/etas_icons/`, and `/media/tech/fonts/`.
- `https://www.etas.com/sitemap.xml` returned a 404 page; use the robots-declared `https://www.etas.com/ww/sitemap.xml` instead.
- `https://docs.etas.com/robots.txt` allows `/` and lists product-specific sitemaps for docs areas including ASCMO, CycurRISK, Data Operator, EATB, EHANDBOOK, INCA, LiMa, MC-Gateway, MDA, and XCT.
- `https://docs.etas.com/sitemap.xml` returned a GitHub Pages 404; use the product-specific sitemap URLs from `docs.etas.com/robots.txt` instead.
- `https://license.etas.com/robots.txt` returned 404 in passive fetch.
- `https://api.etas.com/robots.txt` returned a SOAP fault-style response instead of a normal robots file; note only as a routing/API fingerprint, not a finding.

## App-store/package-ID pivots
- Apple App Store developer page observed for ETAS GmbH: https://apps.apple.com/us/developer/etas-gmbh/id596772516
- No confirmed Google Play package ID was identified in this passive pass; many `ETA` search hits are unrelated travel or appliance apps and should be excluded unless publisher ownership is confirmed.
- Next passive step: search regional Apple stores and vendor pages for ETAS-owned mobile apps; record only apps whose publisher is `ETAS GmbH` or another officially confirmed Bosch/ETAS entity.

## Refined follow-up artifacts
- `recon/target_candidates.md` ranks high-confidence ETAS starting points and separates passive-first public web targets from assets that require explicit scope confirmation.
- `recon/passive_sitemap_inventory.md` preserves sitemap-derived counts and representative URLs for downloads, license pages, cybersecurity pages, support/training pages, and docs sitemaps.
- Path traversal and active vulnerability probing were not performed; future validation requires written scope confirmation and agreed rate limits/stop conditions.

## Recon value / next passive steps
- Highest-value buckets remain downloads, license portals, security/cybersecurity product surfaces, edge/cloud portals, and public docs.
- For downloads/docs, build a product/version inventory from the Software Download Overview and docs hub, then map each product to public installers, manuals, known-issue reports, certificates, and terms pages.
- For license surfaces, passively document LiMa/FNO/License Server flows, public manuals, and hostnames; do not attempt login, token, entitlement, or license operations.
- For edge/cloud surfaces, track CT deltas and public documentation only; do not probe APIs, enumerate endpoints, or attempt unauthenticated requests beyond normal public landing pages/robots already observed.
- For cybersecurity products, distinguish product marketing/docs/downloads from reportable vulnerabilities; do not run fuzzers or tools against ETAS/Bosch infrastructure.
- `brand.etas.com`
- `forms.etas.com`
- `go.etas.com`

## Public sources and documentation/app pivots
- https://www.etas.com/ww/en/
- https://www.etas.com/ww/en/downloads/

## Recon value / next passive steps
- Interesting first-pass buckets: downloads, license portals, security/cybersecurity product surfaces, edge/cloud portals, and public docs.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.

## 2026-07-04 session update - scope, WSTG mapping, and evidence status

### Scope Confirmation
- Date/time (BRT, ISO 8601): 2026-07-04T18:22:25-03:00
- Researcher / operator: Codex agent operating under local `RoEAIFile.md`
- VDP program page reviewed: Bosch PSIRT policy pages were reachable; likely Bugcrowd vanity URLs checked locally were not usable as scope pages (`https://bugcrowd.com/bosch` and `https://bugcrowd.com/engagements/bosch` returned 404; `https://app.bugcrowd.com/engagements/bosch` did not resolve from this environment). Bosch PSIRT Bugcrowd form embed observed at `https://psirt.bosch.com/report-a-vulnerability/bugcrowd-form.html`.
- Exact asset being tested: None
- Exact hostname: None for active testing
- Exact URL/path(s): No ETAS target URL was actively tested in this session
- Scope status: Ambiguous for active testing; Bosch PSIRT brand/reporting pages support disclosure handling, but no exact ETAS hostname was confirmed as an active-test target from a live Bugcrowd Targets section.
- Scope evidence: Bosch PSIRT pages state that Bosch PSIRT accepts reports related to Bosch websites/products and references Bugcrowd as the preferred website-vulnerability reporting path. This is reporting/disclosure evidence, not a per-host active-testing scope grant.
- Relevant exclusions / special rules: Local RoE requires exact written scope confirmation before active requests; active testing window is Monday-Friday 09:00-17:00 America/Sao_Paulo and excludes holidays/incidents. Current session occurred Saturday 2026-07-04 at 18:22 BRT, outside the active window.
- Test account(s) owned by researcher: None
- Planned WSTG test families: Passive-only mapping for Information Gathering, Configuration/Deployment, Client-side, Authentication/Session where login surfaces are only documented, Authorization/API where portal/API hosts are only scope leads.
- Planned request budget: 0 active ETAS validation requests. Passive policy/context requests only.
- Approval decision: RECON ONLY / STOP active validation

### Request accounting
- ETAS target active validation requests: 0.
- ETAS target passive requests in this session: 0.
- Bosch PSIRT passive policy/reporting context requests: 5 GET requests (`/bosch-responsible-disclosure-policy/` twice, `/bosch-brands/`, `/report-a-vulnerability/`, `/report-a-vulnerability/bugcrowd-form.html`).
- Bugcrowd URL discovery checks: 2 HEAD requests to likely Bugcrowd vanity/engagement URLs returned 404; 1 attempted HEAD to `app.bugcrowd.com` failed DNS resolution from this environment.
- No authentication, account creation, fuzzing, scanning, payload testing, form submission, file upload, state change, or ETAS endpoint probing was performed.

### Current evidence status
- Confirmed vulnerabilities: None.
- Suspected findings: None promoted to suspected vulnerability status.
- Observations:
  - Bosch PSIRT public pages identify PSIRT as the reporting path for Bosch website/product vulnerabilities and list `psirt@bosch.com`.
  - Bosch PSIRT report page identifies Bugcrowd as the preferred channel for website vulnerabilities and e-mail for product vulnerabilities.
  - Bosch PSIRT Bugcrowd form page embeds a Bugcrowd external report endpoint (`https://bugcrowd.com/06bfd0dc-cd15-445a-8b2c-08bd0997013a/external/report`), but this does not reveal a target scope list.
  - Bosch PSIRT brand page points to a Bosch brand list and says Bosch PSIRT handles Bosch brands; this supports disclosure routing only, not active testing authorization for every ETAS hostname.
- False positives / non-findings:
  - `api.etas.com/robots.txt` SOAP fault-style behavior remains a routing/API fingerprint only, not a vulnerability.
  - CT-discovered admin, QA, research, license, and portal hostnames remain scope-confirmation leads only.
- Items requiring human approval:
  - Any active validation against `license.etas.com`, `fnoassist.license.etas.com`, `api.etas.com`, `edge.etas.com`, `api.edge.etas.com`, `portal.edge.etas.com`, `admin-api.edge.etas.com`, `cycurguard*.etas.com`, `findingdb.sec.etas.com`, `pmant.sec.etas.com`, or research/LLM gateway hostnames.
  - Any state-changing workflow, account creation, login attempt, download entitlement check, upload, form submission, password recovery, OAuth/SSO/MFA/payment/support action, API mutation, or stored-input test.

### Targeted OWASP WSTG mapping for next eligible session
- `www.etas.com` public pages/download indexes: WSTG Information Gathering and Configuration/Deployment only. Use headers, public sitemap entries, cache/security headers, and public metadata. Do not test downloads for traversal or bypass without exact scope confirmation.
- `docs.etas.com` documentation hub/sitemaps: WSTG Information Gathering and Client-side review. Inventory docs that mention API names, Swagger, ports, license workflows, and update servers as architecture context only.
- Login/license/support/portal-looking URLs: WSTG Authentication, Session Management, Authorization, and Business Logic are relevant only after exact target scope, owned test accounts, and human approval for any state-changing workflow.
- `api.*`, `edge.*`, and `sec.*` hostnames: WSTG API and Authorization areas are relevant in theory, but current decision is scope-confirmation only. No unauthenticated probing, endpoint enumeration, GraphQL/Swagger interaction, or object-ID testing.
- Forms/search/query-string pages on public `www.etas.com`: WSTG Input Validation may be relevant later with one inert marker per hypothesis, but only during the permitted test window and after exact scope confirmation.

### Severity and remediation notes
- No severity assigned because no vulnerability is confirmed.
- Program/process remediation note for future reporting: include exact affected URL, minimal evidence, request counts, no-impact statement, and whether the issue is website or product-related so Bosch PSIRT/Bugcrowd routing is clear.

## 2026-07-04 operator clarification and start queue

### Operator scope clarification
- Date/time (BRT, ISO 8601): 2026-07-04T18:36:33-03:00
- Operator stated that ETAS is covered because ETAS is a Bosch brand and Bosch PSIRT/Bosch Brands materials authorize Bosch-brand disclosure handling.
- This clarification is recorded as operator-provided scope rationale for ETAS-brand ownership and disclosure routing.
- Remaining local execution gates:
  - Earlier `AGENTS.md` required active traffic hosts to be listed in `scope/allowed-hosts.txt`; that path now exists after the workspace reorganization.
  - `RoEAIFile.md` still defines active testing as Monday-Friday 09:00-17:00 BRT unless a higher-priority live program rule overrides it.
  - Raw target commands such as `curl`, `wget`, `httpx`, `ffuf`, `katana`, `nuclei`, `nmap`, or custom socket scripts require explicit command-and-target approval under `AGENTS.md`.
- Current execution decision remains: passive/local triage only in this session; active target requests are queued, not run.

### Starting URL queue from current findings
| Priority | URL / host | Current status | WSTG focus | Minimal next action when gates are satisfied | Initial budget |
| --- | --- | --- | --- | --- | --- |
| 1 | `https://www.etas.com/ww/en/downloads/software-downloads-overview/` | Public ETAS download index | WSTG-INFO, WSTG-CONF | One baseline `GET`, record status/headers/cache/security controls, then review only linked product/version pages already present in sitemap inventory. | 1-5 requests |
| 2 | `https://docs.etas.com/` and product sitemaps | Public docs hub | WSTG-INFO, client-side review | One baseline `GET` for hub/robots if allowed, then offline inventory of already-known product sitemaps and docs mentioning APIs, Swagger, ports, update servers, or license flows. | 1-5 requests |
| 3 | `https://www.etas.com/ww/sitemap.xml` and `https://www.etas.com/ww/en/t-sitemap.xml` | Public sitemap source | WSTG-INFO | Refresh only if needed; avoid broad crawling. Use sitemap entries to classify URLs into downloads, docs, support/training, forms, and product pages. | 1-3 requests |
| 4 | `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/` | Support-portal context page | WSTG-INFO, business-logic mapping | Review page content for official portal names, data categories, and support workflow context. Do not create accounts or submit forms. | 1 request |
| 5 | `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/` and `/license-server/` | Public license-related pages | WSTG-INFO, auth/session planning only | Map documented license workflow and entitlement language. Do not access `license.etas.com` or perform license operations. | 1-3 requests |
| 6 | `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/` and cybersecurity product pages | Public security-product/download pages | WSTG-INFO, business-logic mapping | Determine whether trials, demos, forms, or downloads are described. Do not run tools against ETAS/Bosch infrastructure or submit forms. | 1-5 requests |
| 7 | `license.etas.com`, `fnoassist.license.etas.com`, `api.etas.com`, `api.edge.etas.com`, `portal.edge.etas.com`, `admin-api.edge.etas.com` | CT/public hostname leads | Scope confirmation only | Do not browse or probe until host appears in allowed-hosts and active window/rules are satisfied. | 0 requests |

### Local false-positive controls before reporting
- Do not report missing headers, cookie flags, version banners, GraphQL introspection, open redirect, CORS, or OIDC/client config unless a working impact chain exists.
- Do not turn documentation-only API/Swagger references into findings without reachable, in-scope, non-disruptive evidence.
- Treat CT names containing `admin`, `qa`, `dev`, `research`, `llm`, `sec`, `kafka`, `nifi`, or `artifactory` as sensitive scope leads, not test targets.

## 2026-07-04 Class 0 passive baseline

### Scope Confirmation
- Date/time (BRT, ISO 8601): 2026-07-04T18:40:21-03:00
- Researcher / operator: Codex agent operating under local `RoEAIFile.md`
- VDP program page reviewed: Bosch PSIRT / Bosch Brands context and operator clarification that ETAS is a Bosch brand.
- Exact asset being tested: Public ETAS website/documentation pages only.
- Exact hostname: `www.etas.com`, `docs.etas.com`
- Exact URL/path(s):
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/`
  - `https://docs.etas.com/`
  - `https://www.etas.com/ww/sitemap.xml`
  - `https://www.etas.com/ww/en/t-sitemap.xml`
  - `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/`
- Scope status: Operator-confirmed Bosch-brand scope for passive/observational baseline; active validation remains constrained by RoE test-window and payload restrictions.
- Scope evidence: Local `scope` file lists these ETAS URLs as high-confidence starting points; operator stated ETAS is a Bosch brand under Bosch Brands / Bosch PSIRT handling.
- Relevant exclusions / special rules: No payloads, no forms, no login, no crawling, no license/API/portal host interaction, no state changes, no vulnerability probing.
- Test account(s) owned by researcher: None
- Planned WSTG test families: WSTG-INFO and WSTG-CONF passive header/status observation only.
- Planned request budget: 5 target HEAD requests.
- Approval decision: ACTIVE CLASS 0 PASSIVE OBSERVATION ONLY

### Request accounting
- External target requests sent: 5 HEAD requests.
- Failed sandbox-only attempts before escalation: 5 DNS failures inside sandbox; no target response received.
- No retries against target responses were needed.
- No `429`, `503`, `504`, repeated `5xx`, connection reset, abnormal latency, or instability signal observed.

### Observations
- `https://www.etas.com/ww/en/downloads/software-downloads-overview/` returned `200`, `content-type: text/html;charset=UTF-8`, HSTS with includeSubDomains, `X-Frame-Options: SAMEORIGIN`, `X-Content-Type-Options: nosniff`, `Referrer-Policy: strict-origin-when-cross-origin`, and a `Secure; HttpOnly; SameSite=Lax` session cookie.
- `https://docs.etas.com/` returned `200` from GitHub Pages / Fastly with `content-type: text/html; charset=utf-8`, `access-control-allow-origin: *`, HSTS, public cache headers, and `content-length: 9176`.
- `https://www.etas.com/ww/sitemap.xml` returned `200`, `content-type: application/xml`, `content-length: 667`, public cache headers, and the same main-site security header pattern.
- `https://www.etas.com/ww/en/t-sitemap.xml` returned `200`, `content-type: application/xml`, `content-length: 84730`, public cache headers, and the same main-site security header pattern.
- `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/` returned `200`, `content-type: text/html;charset=UTF-8`, and the same main-site security header pattern.

### Evidence status
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- False positives / non-findings:
  - Header observations, wildcard CORS on static GitHub Pages documentation, CSP shape, and session cookie attributes are not reportable by themselves under the local never-submit rules.
- Next passive-safe step:
  - Parse the already-known sitemap URLs locally into a product/version/category table without probing unlisted paths or submitting forms.

## 2026-07-04 sitemap refresh and URL clustering

### Scope Confirmation
- Date/time (BRT, ISO 8601): 2026-07-04T18:40:21-03:00 session continuation.
- Exact asset being tested: Public ETAS English sitemap only.
- Exact hostname: `www.etas.com`
- Exact URL/path(s): `https://www.etas.com/ww/en/t-sitemap.xml`
- Scope status: Operator-confirmed Bosch-brand scope for passive sitemap refresh.
- Planned WSTG test families: WSTG-INFO only.
- Planned request budget: 1 target GET request.
- Approval decision: ACTIVE CLASS 0 PASSIVE OBSERVATION ONLY

### Request accounting
- External target requests sent for this step: 1 GET request.
- Total external ETAS target requests in this continuation: 6 (5 HEAD + 1 GET).
- Response body saved only to `/tmp/etas_en_t_sitemap.xml` for local parsing.
- No crawler, path brute force, payload, form submission, authentication, or unlisted-path request was used.

### Refreshed sitemap observations
- English sitemap size: 84,730 bytes.
- URL entries extracted: 614.
- Software download overview URLs: 145.
- Support/training URLs: 153.
- URLs containing `cyber`, `security`, or `cycur`: 81.
- URLs containing `form` or `contact`: 58.
- License-related public sitemap URLs: 2.
- Training registration form URLs: 6.

### High-signal URL clusters
- Public license pages:
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/license-server/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/`
- Public form/contact leads:
  - `https://www.etas.com/ww/en/contact/`
  - `https://www.etas.com/ww/en/contact/etas-key-management-system-demo-request/`
  - `https://www.etas.com/ww/en/support-training/etas-academy/training-registration-form/`
  - Region-specific training registration forms for Brazil, India, Italy, UK, and USA.
- Public security-product and training leads:
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurhsm/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycuranalyze/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurfuzz/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/`
  - `https://www.etas.com/ww/en/support-training/etas-academy/web-application-security/`

### Current assessment
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- Items requiring human approval before interaction:
  - Any form submission, training registration flow, demo request, contact workflow, download entitlement bypass check, or license workflow action.
  - Any request to `license.etas.com`, `api.etas.com`, `edge.etas.com`, `portal.edge.etas.com`, `sec.etas.com`, or research/LLM gateway hosts.

## 2026-07-04 public page classification checkpoint

### Scope Confirmation
- Date/time (BRT, ISO 8601): 2026-07-04T18:48:40-03:00 session continuation.
- Exact asset being tested: Public ETAS sitemap-listed pages only.
- Exact hostname: `www.etas.com`
- Exact URL/path(s):
  - `https://www.etas.com/ww/en/contact/`
  - `https://www.etas.com/ww/en/contact/etas-key-management-system-demo-request/`
  - `https://www.etas.com/ww/en/support-training/etas-academy/training-registration-form/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/license-server/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/`
- Scope status: Operator-confirmed Bosch-brand scope for public page observation.
- Planned WSTG test families: WSTG-INFO and WSTG-CONF passive page classification only.
- Planned request budget: 6 target GET requests.
- Approval decision: ACTIVE CLASS 0 PASSIVE OBSERVATION ONLY

### Request accounting
- External target requests sent for this step: 6 sequential GET requests with one-second sleeps between requests.
- Total external ETAS target requests in this continuation: 12 (5 HEAD + 1 sitemap GET + 6 page GET).
- Responses saved to `/tmp` for local review:
  - `/tmp/etas_contact.html`
  - `/tmp/etas_key_demo.html`
  - `/tmp/etas_training_form.html`
  - `/tmp/etas_lima.html`
  - `/tmp/etas_license_server.html`
  - `/tmp/etas_cycurfuzz_download.html`
- Response statuses and sizes:
  - Contact page: `200`, 102,256 bytes, 2.04s.
  - Key-management demo request page: `200`, 64,151 bytes, 2.11s.
  - Training registration form page: `200`, 72,080 bytes, 2.13s.
  - LiMa License Manager page: `200`, 69,183 bytes, 2.15s.
  - License Server page: `200`, 65,816 bytes, 2.18s.
  - CycurFUZZ download page: `200`, 65,890 bytes, 2.16s.
- No payloads, no submissions, no authentication, no crawler, no fuzzing, no API/license/portal host interaction, and no state-changing action.

### Local parsing notes
- Initial broad local `rg` parsing produced overly large output and one malformed quote command; this was local-only and generated no network traffic.
- Lightweight local count showed repeated public page patterns:
  - Contact/demo/training pages each matched 11 broad form/download/config terms.
  - LiMa, License Server, and CycurFUZZ pages each matched 36 broad form/download/config terms.
- The CycurFUZZ saved HTML contains client-side configuration for Bosch DXF download services and metasearch endpoints, including `dxf-services.bosch.com` URLs and CSRF metadata. This is configuration/context only, not a vulnerability.

### Stop / checkpoint reason
- Stopped per operator instruction to avoid excessive usage and to register completed work before continuing.
- Current findings status remains: no confirmed vulnerabilities and no suspected findings.
- Next safe step, if continued later: perform narrow local parsing of the saved HTML files for form action URLs, download-service configuration, and client-side route names without sending additional target traffic.

## 2026-07-04 offline HTML parsing checkpoint

### Scope / traffic status
- Date/time (BRT, ISO 8601): 2026-07-04T18:52:30-03:00
- Work type: Offline review of already saved public HTML files under `/tmp`.
- New external target requests sent in this step: 0.
- Total external ETAS target requests in this continuation remains: 12 (5 HEAD + 1 sitemap GET + 6 public page GET).
- No payloads, form submissions, authentication, download attempts, API calls, license-portal requests, fuzzing, crawling, or state-changing actions were performed.

### Offline observations from saved pages
- Common public client-side configuration appears across the saved `www.etas.com` pages:
  - `https://bosch-i4-caas-api.e-spirit.cloud`
  - `https://dxf-services.bosch.com/dxf-download-service-2-0-0/v1`
  - `https://dxf-services.bosch.com/metasearch/dxf-etas-v5`
  - `https://dxf-services.bosch.com/watermark-service`
  - Public config values included `tenant` values `bosch-i4-prod` and `dxf-etas-v5`, `useClientRoles=false`, `useDefaultTokenPath=true`, `customTokenPath=/test/token`, and `permissions=[]`.
- The public config also contains an `apiKey` value (`ae5f2454-9d4b-4380-8ed4-32adca8a76a7`). This is treated as public SPA/CMS configuration context only; it is not a finding without proof of unauthorized capability.
- Saved pages contain CSRF metadata (`_csrf_header` = `X-CSRF-TOKEN`) and `_authorized=false`, which is consistent with unauthenticated public page rendering.
- Each saved page contains only navigation search form markup in the static HTML review (`M-ETAS-Navigation__search__wrapper` with `input type=search`). No search submission was performed.
- The contact page links to `https://forms.etas.com/content/?f=GjRzb&ft=`.
- The key-management demo and training registration pages load Bosch webforms assets from `https://btm.bosch.com/rb/form/v5/webforms.min.css?ver=6.1.0` and `https://btm.bosch.com/rb/form/v5/webforms.min.js?ver=6.1.0`.
- The CycurFUZZ download page links to `https://license.etas.com/DownloadLoginPage/jsps/downloadlogin.jsp?downloadPackage=ES_CYCURFUZZ%7CSoftware_V2.1.1` for `ESCRYPT CycurFUZZ V2.1.1 Software`, described publicly as an English ZIP package of 2.99 GB dated 2026-03-22.

### Finding classification
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- Observations only:
  - Public client-side config and API/service URLs exposed in static HTML.
  - Public form and webform asset links.
  - Public license download-login link for a large download package.
- False positives / not findings at this stage:
  - Public `apiKey` value, CSRF metadata, public metasearch/download-service configuration, and navigation search forms are not reportable without safe evidence of unauthorized access, sensitive data exposure, or security control bypass.

### Actions requiring human approval before any interaction
- Opening or testing `forms.etas.com/content/?f=GjRzb&ft=`.
- Fetching Bosch webforms assets from `btm.bosch.com` beyond what is already referenced in saved HTML.
- Requesting `license.etas.com/DownloadLoginPage/jsps/downloadlogin.jsp?...` or any download entitlement/license workflow.
- Submitting any search marker or malformed input to `www.etas.com` search/metasearch endpoints.
- Any request to `dxf-services.bosch.com` service endpoints, even if referenced by public JavaScript config.

### Recommended next step
- Continue local-only product/version inventory from the sitemap and saved HTML, or obtain explicit human approval for one narrowly scoped Class 1 hypothesis before sending any additional request.

## 2026-07-04 local-only sitemap product inventory

### Traffic status
- Source: already saved `/tmp/etas_en_t_sitemap.xml`.
- New external target requests sent in this step: 0.
- Total external ETAS target requests in this continuation remains: 12.

### Inventory observations
- Refreshed `recon/passive_sitemap_inventory.md` with the current saved-sitemap counts: 614 English URLs, 145 software-download URLs, and 153 support/training URLs.
- High-count download clusters from saved sitemap:
  - `rta-car-v12*`: 16 URLs.
  - `rta-car-fsqp*`: 16 URLs.
  - `isolar-a-v12*`: 14 URLs.
  - `rta-os-*`: 41 target/compiler-specific installer URLs.
  - `inca-v7*`: 5 URLs.
  - `ascet*`: 4 URLs.
  - `mda-v8*`: 3 URLs.
  - `rta-fbl-stla*`: 3 URLs.
  - `rta-fbl-gm*`: 3 URLs.
- Security/training leads include CycurFUZZ protocol fuzz-testing training, automotive security, AUTOSAR security, cloud security, threat modeling, web application security, Windows security, and six training-registration-form routes.

### Finding classification
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- Observations only: public sitemap product/version inventory and public training/form route inventory.
- Next safe work: continue offline classification or request explicit approval before any further interaction with forms, search, license, download-service, or metasearch endpoints.

## 2026-07-04 inert search-marker route check

### Scope / traffic status
- Date/time (BRT, ISO 8601): 2026-07-04T22:08:48-03:00
- Work type: Minimal live route validation on public `www.etas.com` search endpoints with an inert marker.
- New external target requests sent in this step: 3.
- Total external ETAS target requests in this continuation: 15.
- Marker used: `codex-etas-inert`.

### Requests and responses
- `GET https://www.etas.com/search?search=codex-etas-inert` -> `302`, `Location: https://www.etas.com/search/?search=codex-etas-inert`.
- `GET https://www.etas.com/search/?search=codex-etas-inert` -> `302`, `Location: https://www.etas.com/ww/en/index.html`.
- `GET https://www.etas.com/ww/en/index.html?search=codex-etas-inert` -> `302`, `Location: https://www.etas.com/ww/en/?search=codex-etas-inert`.
- `GET https://www.etas.com/ww/en/?search=codex-etas-inert` -> `200`, `content-type: text/html;charset=UTF-8`, `content-language: en-WW`.

### Observations
- The search parameter was preserved through canonical redirects but was not reflected in the rendered page content.
- The response chain stayed on the ETAS domain and did not trigger any external callback or state-changing action.
- The rendered homepage still contained the same navigation search form markup and public metasearch configuration seen in the saved HTML.

### Finding classification
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- Observations only: search-route canonicalization and non-reflection of the inert marker.
- False positives / not findings at this stage:
  - Redirecting `/search` to `/ww/en/index.html` and then to `/ww/en/` is normal canonicalization behavior.
  - The inert marker remaining in the query string without being rendered is not a vulnerability.

### Stop / follow-up
- No further live search probing is needed from this hypothesis.
- Continue only offline inventory or request explicit approval for a different exact hypothesis if more live validation is desired.

## 2026-07-04 workspace reorganization

### File layout changes
- Reorganized the local workspace into purpose-specific directories:
  - `scope/`
  - `recon/`
  - `findings/`
  - `handoff/`
  - `artifacts/`
  - `scripts/`
  - `governance/`
  - `analysis-template/`
- Preserved `RoEAIFile.md` at the workspace root because it remains the authoritative RoE entry point.
- Preserved the original zero-byte placeholder files under `legacy-placeholders/`.
- Moved the original flat `scope` file to `scope/current-scope.md`.
- Added `scope/allowed-hosts.txt` and `scope/approval-required-hosts.txt`.
- Added reusable project template files under `analysis-template/`.

### Traffic status
- New external target requests sent in this step: 0.
- Total external ETAS target requests in this continuation remains: 15.

### Finding classification
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- This was local workspace organization only.
