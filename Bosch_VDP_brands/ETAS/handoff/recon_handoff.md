# ETAS passive recon handoff / continuation log

## Purpose
This file is a handoff note for future LLM sessions, analysts, or chats that need to continue the ETAS passive recon work without losing context. It tracks what was done, when it was done, where the findings were recorded, and what remains to be done before any report or scope-confirmation request.

## Current scope focus
- **Target focus for this week:** ETAS only.
- **Brand context:** ETAS is treated as a Bosch brand for disclosure/scope guardrails.
- **Allowed work so far:** Passive/open-source recon only.
- **Do not perform without explicit authorization:** authentication attempts, account creation, active scanning, fuzzing, exploitation, endpoint enumeration, vulnerability probing, high-volume scraping, or testing of any CT-discovered host.

## Disclosure and scope guardrails
- Use Bosch PSIRT Responsible Disclosure Policy as the primary Bosch-brand disclosure reference: https://psirt.bosch.com/bosch-responsible-disclosure-policy/
- Use Bugcrowd Standard Disclosure Terms as the user-provided standard terms reference: https://www.bugcrowd.com/resources/hacker-resources/standard-disclosure-terms/
- Treat every hostname, URL, portal, API, document, download, and app-store result as a **passive lead**, not proof of in-scope authorization.
- Before any active validation, confirm the exact in-scope targets and rules of engagement.

## Work completed

### 2026-07-04 - Workspace reorganization
- Reorganized the local folder into purpose-specific directories:
  - `scope/`
  - `recon/`
  - `findings/`
  - `handoff/`
  - `artifacts/`
  - `scripts/`
  - `governance/`
  - `analysis-template/`
- Kept `RoEAIFile.md` at the workspace root as the authoritative RoE file.
- Moved the original flat `scope` file to `scope/current-scope.md`.
- Moved recon files to `recon/`, findings material to `findings/`, and continuation notes to `handoff/`.
- Preserved original zero-byte placeholder files in `legacy-placeholders/`.
- Added `scope/allowed-hosts.txt` for currently allowed public-observation hosts and `scope/approval-required-hosts.txt` for higher-sensitivity hosts.
- Added `analysis-template/` as a reusable project/analysis template.
- No external target requests were sent for this reorganization. Total ETAS target requests remains 15.

### 2026-07-04 - RoE-gated continuation and scope check
- Read all visible workspace markdown files and confirmed `.codex` / `.agents` contained no task-relevant files.
- Treated `RoEAIFile.md` as authoritative. The current session time was `2026-07-04T18:22:25-03:00`, a Saturday and outside the Monday-Friday 09:00-17:00 BRT active testing window.
- Per RoE, no active ETAS validation was performed. No ETAS target endpoints were fetched in this session.
- Passive policy/reporting context fetched:
  - `https://psirt.bosch.com/bosch-responsible-disclosure-policy/`
  - `https://psirt.bosch.com/bosch-brands/`
  - `https://psirt.bosch.com/report-a-vulnerability/`
  - `https://psirt.bosch.com/report-a-vulnerability/bugcrowd-form.html`
- Likely Bugcrowd vanity/engagement URLs did not provide scope confirmation from this environment:
  - `https://bugcrowd.com/bosch` -> 404
  - `https://bugcrowd.com/engagements/bosch` -> 404
  - `https://app.bugcrowd.com/engagements/bosch` -> DNS resolution failure from the environment
- Observed Bosch PSIRT Bugcrowd embed endpoint: `https://bugcrowd.com/06bfd0dc-cd15-445a-8b2c-08bd0997013a/external/report`. Treat as reporting-channel evidence only, not target scope.
- Added a formal RECON ONLY scope record, request accounting, evidence status, and WSTG mapping to `findings_draft.md`.
- Corrected an accidental pasted GitHub conflict URL inside `domains.md` CT delta notes.

### 2026-07-04 - Operator clarification and local start queue
- Operator clarified that ETAS should be treated as authorized because ETAS is a Bosch brand and Bosch Brands/PSIRT materials cover Bosch-brand disclosure handling.
- Read newly noticed support files:
  - `AGENTS.md`
  - `pentest-agents/AGENTS.md`
  - `pentest-agents/providers/codex/AGENTS.md`
  - `pentest-agents/rules/hunting.md`
  - `pentest-agents/rules/never-submit.md`
- Important additional gate from the previously present `AGENTS.md`: active browser or HTTP traffic requires confirmation that the host is listed in `scope/allowed-hosts.txt`. That path now exists after the workspace reorganization.
- Empty placeholder files observed: `findings`, `handoff`, `artifacts`, `scripts`, `.codex`.
- Added a concrete starting URL queue and minimal request budgets to `findings/findings_draft.md`.
- Current best first targets, once gates are satisfied:
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/`
  - `https://docs.etas.com/`
  - `https://www.etas.com/ww/sitemap.xml`
  - `https://www.etas.com/ww/en/t-sitemap.xml`
  - `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/`
- Keep `license.etas.com`, `api*.etas.com`, `edge*.etas.com`, `portal*.etas.com`, `sec.etas.com`, and research/LLM gateway hosts as scope leads until allowed-hosts and RoE gates are satisfied.

### 2026-07-04 - Class 0 passive baseline
- After the operator said "Try again", performed only Class 0 passive/observational HEAD checks against public URLs already listed in `scope` and `findings_draft.md`.
- Target requests sent: 5 HEAD requests total.
- URLs checked:
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/` -> `200`
  - `https://docs.etas.com/` -> `200`
  - `https://www.etas.com/ww/sitemap.xml` -> `200`
  - `https://www.etas.com/ww/en/t-sitemap.xml` -> `200`
  - `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/` -> `200`
- No payloads, forms, logins, crawling, license/API/portal host access, state changes, fuzzing, or vulnerability probing were performed.
- No stop-condition response (`429`, `503`, `504`, repeated `5xx`, reset, or instability signal) was observed.
- Findings status remains: no confirmed vulnerabilities and no suspected findings.

### 2026-07-04 - English sitemap refresh
- Noted that `RoEAIFile.md` had been modified outside Codex edits to remove the explicit weekday/time-window lines; Codex did not make or revert that change.
- Fetched `https://www.etas.com/ww/en/t-sitemap.xml` once and parsed it locally from `/tmp/etas_en_t_sitemap.xml`.
- Target request count for this step: 1 GET.
- Refreshed observations:
  - Sitemap size: 84,730 bytes.
  - URL entries: 614.
  - Software download overview URLs: 145.
  - Support/training URLs: 153.
  - URLs containing `cyber`, `security`, or `cycur`: 81.
  - URLs containing `form` or `contact`: 58.
  - License-related public sitemap URLs: 2.
  - Training registration form URLs: 6.
- High-signal next review areas are public license pages, contact/demo/training forms, cybersecurity product pages, and CycurFUZZ download context.
- Do not submit forms or test entitlement/license/API behavior without separate human approval.

### 2026-07-04 - Public page classification checkpoint
- Per operator instruction, stopped before continuing further and registered current progress.
- Sent 6 sequential GET requests with one-second sleeps to public sitemap-listed `www.etas.com` pages:
  - `https://www.etas.com/ww/en/contact/` -> `200`, 102,256 bytes, 2.04s.
  - `https://www.etas.com/ww/en/contact/etas-key-management-system-demo-request/` -> `200`, 64,151 bytes, 2.11s.
  - `https://www.etas.com/ww/en/support-training/etas-academy/training-registration-form/` -> `200`, 72,080 bytes, 2.13s.
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/` -> `200`, 69,183 bytes, 2.15s.
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/license-server/` -> `200`, 65,816 bytes, 2.18s.
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/` -> `200`, 65,890 bytes, 2.16s.
- Total external ETAS target requests in this continuation: 12.
- Saved response bodies only under `/tmp` for local analysis.
- No payloads, submissions, authentication, crawling, fuzzing, API/license/portal host requests, or state-changing actions.
- Local parsing observed Bosch DXF download-service/metasearch configuration and CSRF metadata in saved download pages; record as context only.
- Findings status: no confirmed vulnerabilities and no suspected findings.
- Recommended next step: continue offline parsing of saved HTML files before any additional target requests.

### 2026-07-04 - Offline HTML parsing checkpoint
- Continued with local-only parsing of the previously saved `/tmp` HTML files. No new external target requests were sent.
- Total external ETAS target requests in this continuation remains 12.
- Common public client-side configuration observed across saved pages:
  - `bosch-i4-caas-api.e-spirit.cloud`
  - `dxf-services.bosch.com/dxf-download-service-2-0-0/v1`
  - `dxf-services.bosch.com/metasearch/dxf-etas-v5`
  - `dxf-services.bosch.com/watermark-service`
  - public values including `tenant=bosch-i4-prod`, `tenant=dxf-etas-v5`, `useClientRoles=false`, `useDefaultTokenPath=true`, `customTokenPath=/test/token`, and `permissions=[]`.
- Public config included `apiKey` value `ae5f2454-9d4b-4380-8ed4-32adca8a76a7`; treat as public SPA/CMS context only, not a finding without safe proof of unauthorized capability.
- CSRF metadata and `_authorized=false` were present in saved unauthenticated page HTML.
- Static form review found navigation search forms only in the saved HTML; no marker or search submission was performed.
- External interaction leads identified but not opened:
  - Contact form: `https://forms.etas.com/content/?f=GjRzb&ft=`
  - Bosch webforms assets: `https://btm.bosch.com/rb/form/v5/webforms.min.css?ver=6.1.0` and `https://btm.bosch.com/rb/form/v5/webforms.min.js?ver=6.1.0`
  - License download-login link: `https://license.etas.com/DownloadLoginPage/jsps/downloadlogin.jsp?downloadPackage=ES_CYCURFUZZ%7CSoftware_V2.1.1`
- CycurFUZZ package context from saved HTML: `ESCRYPT CycurFUZZ V2.1.1 Software`, English ZIP, 2.99 GB, dated 2026-03-22.
- Findings status remains unchanged: no confirmed vulnerabilities and no suspected findings.
- Before any further interaction, request explicit approval for the exact host/path and hypothesis, especially for forms, `license.etas.com`, `btm.bosch.com`, `dxf-services.bosch.com`, or metasearch/search marker tests.

### 2026-07-04 - Local-only sitemap product inventory
- Parsed the already saved `/tmp/etas_en_t_sitemap.xml`; no new target requests were sent.
- Updated `passive_sitemap_inventory.md` to align with the latest saved-sitemap counts: 614 English URLs, 145 software-download URLs, and 153 support/training URLs.
- High-count download clusters:
  - `rta-car-v12*`: 16 URLs.
  - `rta-car-fsqp*`: 16 URLs.
  - `isolar-a-v12*`: 14 URLs.
  - `rta-os-*`: 41 target/compiler-specific installer URLs.
  - `inca-v7*`: 5 URLs.
  - `ascet*`: 4 URLs.
  - `mda-v8*`, `rta-fbl-stla*`, and `rta-fbl-gm*`: 3 URLs each.
- Security/training leads include CycurFUZZ fuzz-testing training, automotive security, AUTOSAR security, cloud security, threat modeling, web application security, Windows security, and regional training-registration routes.
- Findings status remains unchanged: no confirmed vulnerabilities and no suspected findings.

### 2026-07-04 - Inert search-marker route check
- Sent 3 additional live GET requests against the public ETAS search route using the inert marker `codex-etas-inert`.
- Total external ETAS target requests in this continuation is now 15.
- Route behavior observed:
  - `/search?search=codex-etas-inert` -> `302` to `/search/?search=codex-etas-inert`
  - `/search/?search=codex-etas-inert` -> `302` to `/ww/en/index.html`
  - `/ww/en/index.html?search=codex-etas-inert` -> `302` to `/ww/en/?search=codex-etas-inert`
  - `/ww/en/?search=codex-etas-inert` -> `200`
- The inert marker was not reflected in the returned HTML body.
- No state change, callback, or external interaction occurred.
- Findings status remains unchanged: no confirmed vulnerabilities and no suspected findings.

### 2026-07-04 - Initial multi-brand passive baseline
- Created or expanded passive recon notes across the prioritized Bosch-related brand folders.
- For ETAS, added an initial baseline in:
  - `findings/findings_draft.md`
  - `recon/domains.md`
- Initial ETAS buckets identified:
  - Downloads
  - License portals
  - Security/cybersecurity product surfaces
  - Edge/cloud portals
  - Public documentation
- Safety note added: passive-only OSINT, no authentication, no exploitation, no fuzzing, no port scanning, no vulnerability probing, no account creation, no high-volume scraping.

### 2026-07-04 - ETAS-focused deep passive enrichment
- Expanded `findings/findings_draft.md` with:
  - Bosch/Bugcrowd disclosure guardrails.
  - ETAS scope/ownership notes.
  - Categorized passive subdomain leads.
  - Historical CT delta snapshot.
  - Public downloads/docs pivots.
  - Robots/sitemap observations.
  - App-store/package-ID pivots.
  - Safe next passive steps.
- Expanded `recon/domains.md` with:
  - Candidate ETAS zones.
  - Full passive CT/public hostname list from the sampled Cert Spotter response.
  - CT delta notes and recent 2026 hostnames to track.
- Expanded `recon/docs.md` with:
  - Official documentation/download hubs.
  - Observed download overview product buckets.
  - Observed documentation hub product buckets.
  - Robots/sitemap references.
- Expanded `recon/apps.md` with:
  - Apple App Store developer page for ETAS GmbH.
  - Apple developer ID.
  - Note that no ETAS-owned Google Play package ID was confirmed in the passive pass.


### 2026-07-04 - Refined ETAS target candidates and sitemap inventory
- Added `recon/target_candidates.md` to rank high-confidence ETAS starting points by confidence, recon value, and active-test sensitivity.
- Added `recon/passive_sitemap_inventory.md` to preserve sitemap-derived download, license, cybersecurity, support/training, and docs inventory counts.
- Explicitly documented that path traversal and active vulnerability probing were not performed and require written scope confirmation.

## Files to read first in the next session
1. `RoEAIFile.md` - authoritative Rules of Engagement.
2. `README.md` - current workspace map.
3. `scope/current-scope.md` - preserved scope notes and candidate table.
4. `scope/allowed-hosts.txt` and `scope/approval-required-hosts.txt` - current host handling.
5. `findings/findings_draft.md` - primary narrative findings and request accounting.
6. `handoff/recon_handoff.md` and `handoff/notes.md` - continuation state.
7. `recon/` - passive CT, docs, app, target-candidate, and sitemap inventories.

## Passive sources and methods already used
- Official ETAS public pages and download/documentation pages.
- Bosch PSIRT disclosure policy page.
- Bugcrowd Standard Disclosure Terms page.
- Apple App Store public developer page for ETAS GmbH.
- Public robots/sitemap fetches for:
  - `https://www.etas.com/robots.txt`
  - `https://www.etas.com/sitemap.xml`
  - `https://docs.etas.com/robots.txt`
  - `https://docs.etas.com/sitemap.xml`
  - `https://license.etas.com/robots.txt`
  - `https://api.etas.com/robots.txt`
- Certificate Transparency via Cert Spotter API for `etas.com` with subdomains included.
- Public search-result review for ETAS downloads, docs, manuals, cybersecurity product pages, and app-store metadata.

## Important observed passive facts to preserve
- `docs.etas.com/robots.txt` allows `/` and lists product-specific sitemaps.
- `www.etas.com/robots.txt` references `https://www.etas.com/ww/sitemap.xml`.
- `www.etas.com/sitemap.xml` returned a 404 page during passive fetch; use the robots-declared `/ww/sitemap.xml` instead.
- `docs.etas.com/sitemap.xml` returned a GitHub Pages 404 during passive fetch; use product-specific sitemap URLs from `docs.etas.com/robots.txt` instead.
- `license.etas.com/robots.txt` returned 404 during passive fetch.
- `api.etas.com/robots.txt` returned a SOAP fault-style response rather than a normal robots file; record as a routing/API fingerprint only, not as a vulnerability.
- Cert Spotter sample returned 100 recent certificate issuance entries and 48 unique hostnames for `etas.com`.
- Cert Spotter sample year distribution was 2025 = 69 issuance entries and 2026 = 31 issuance entries.
- Recent 2026 CT names worth passive tracking include:
  - `bosch-model-farm.llm-gateway.research.etas.com`
  - `model-farm.llm-gateway.research.etas.com`
  - `fnoassist.license.etas.com`
  - `admin-api.edge.etas.com`
  - `mobility-qa-cp-files.edge.etas.com`
  - `mobility-qa-feu-files.edge.etas.com`
  - `portal.edge.etas.com`
  - `api.edge.etas.com`
  - `findingdb.sec.etas.com`
  - `pmant.sec.etas.com`
- Apple App Store developer ID observed for ETAS GmbH: `596772516`.
- No confirmed ETAS-owned Google Play package ID was found in the passive pass.

## Suggested next passive tasks
1. **Docs/download inventory:** Build a product/version matrix from ETAS Software Download Overview and `docs.etas.com` product sitemaps.
2. **CT weekly diff:** Re-run passive CT collection weekly, diff unique DNS names, and bucket new names into core, docs/downloads, license, edge/cloud, security-product, and research.
3. **Robots/sitemap expansion:** Parse only the public sitemap URLs declared in robots files; record product docs and manuals without high-volume scraping.
4. **App-store confirmation:** Search regional Apple storefronts and official ETAS product pages for mobile companion apps; record only publisher-confirmed ETAS/Bosch apps.
5. **Disclosure prep:** If a report is later needed, include Bosch PSIRT and Bugcrowd terms references, exact source URLs, dates observed, and a statement that findings are passive recon leads.
6. **Scope request prep:** Prepare a short list of hostnames/categories that require explicit in-scope confirmation before any testing, especially license, API/edge, QA/dev, security-product, and research hosts.

## Commands/checks run for this documentation update
- `find .. -name AGENTS.md -print`
- `git status --short`
- `find Bosch_VDP_brands/ETAS -maxdepth 1 -type f -printf '%f\\n' | sort`

## Open questions for future sessions
- Which ETAS domains/hosts are explicitly in scope under the applicable Bosch/VDP program?
- Are ETAS edge/cloud and license surfaces covered, or are they excluded unless named in a program target list?
- Are docs/download files safe to mirror for offline review, or should future work link only to public pages?
- Are there officially confirmed Android/Google Play apps for ETAS, or is the Apple developer page the only app-store lead?
- Should report artifacts be organized by product family, hostname category, or VDP scope status?
- Can a human provide or capture the live Bugcrowd Targets section that explicitly lists in-scope Bosch/ETAS hostnames? Without that, active validation must remain blocked.
