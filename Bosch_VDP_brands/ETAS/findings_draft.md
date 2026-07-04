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

## Recon value / next passive steps
- Highest-value buckets remain downloads, license portals, security/cybersecurity product surfaces, edge/cloud portals, and public docs.
- For downloads/docs, build a product/version inventory from the Software Download Overview and docs hub, then map each product to public installers, manuals, known-issue reports, certificates, and terms pages.
- For license surfaces, passively document LiMa/FNO/License Server flows, public manuals, and hostnames; do not attempt login, token, entitlement, or license operations.
- For edge/cloud surfaces, track CT deltas and public documentation only; do not probe APIs, enumerate endpoints, or attempt unauthenticated requests beyond normal public landing pages/robots already observed.
- For cybersecurity products, distinguish product marketing/docs/downloads from reportable vulnerabilities; do not run fuzzers or tools against ETAS/Bosch infrastructure.
