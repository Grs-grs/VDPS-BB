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

### 2026-07-04 - Initial multi-brand passive baseline
- Created or expanded passive recon notes across the prioritized Bosch-related brand folders.
- For ETAS, added an initial baseline in:
  - `Bosch_VDP_brands/ETAS/findings_draft.md`
  - `Bosch_VDP_brands/ETAS/domains.md`
- Initial ETAS buckets identified:
  - Downloads
  - License portals
  - Security/cybersecurity product surfaces
  - Edge/cloud portals
  - Public documentation
- Safety note added: passive-only OSINT, no authentication, no exploitation, no fuzzing, no port scanning, no vulnerability probing, no account creation, no high-volume scraping.

### 2026-07-04 - ETAS-focused deep passive enrichment
- Expanded `findings_draft.md` with:
  - Bosch/Bugcrowd disclosure guardrails.
  - ETAS scope/ownership notes.
  - Categorized passive subdomain leads.
  - Historical CT delta snapshot.
  - Public downloads/docs pivots.
  - Robots/sitemap observations.
  - App-store/package-ID pivots.
  - Safe next passive steps.
- Expanded `domains.md` with:
  - Candidate ETAS zones.
  - Full passive CT/public hostname list from the sampled Cert Spotter response.
  - CT delta notes and recent 2026 hostnames to track.
- Expanded `docs.md` with:
  - Official documentation/download hubs.
  - Observed download overview product buckets.
  - Observed documentation hub product buckets.
  - Robots/sitemap references.
- Expanded `apps.md` with:
  - Apple App Store developer page for ETAS GmbH.
  - Apple developer ID.
  - Note that no ETAS-owned Google Play package ID was confirmed in the passive pass.

## Files to read first in the next session
1. `Bosch_VDP_brands/ETAS/findings_draft.md` - primary narrative findings and next steps.
2. `Bosch_VDP_brands/ETAS/domains.md` - passive CT/public hostname inventory and CT delta notes.
3. `Bosch_VDP_brands/ETAS/docs.md` - public docs/download pivots and robots/sitemap observations.
4. `Bosch_VDP_brands/ETAS/apps.md` - app-store/package-ID status.
5. `Bosch_VDP_brands/ETAS/notes.md` - general ETAS notes if future analysts add observations there.

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
