# ETAS - Notes

Passive recon notes go here.

## 2026-07-04 RoE-gated continuation
- Active validation blocked: current session was Saturday 2026-07-04 at 18:22 BRT, outside the RoE test window.
- Exact ETAS in-scope active-test targets remain unconfirmed. Bosch PSIRT reporting pages support disclosure routing but do not replace a Bugcrowd Targets-section scope confirmation.
- Current decision: RECON ONLY. No active ETAS endpoint requests, payloads, authentication attempts, account creation, form submissions, or state-changing actions were performed.
- Next useful safe step: obtain the live Bugcrowd/Bosch target list or a screenshot/export of the Targets section, then create one RoE scope record per exact ETAS hostname before any future low-impact WSTG validation.

## 2026-07-04 operator clarification
- Operator clarified that ETAS is considered authorized because ETAS is a Bosch brand covered by Bosch Brands / Bosch PSIRT disclosure handling.
- Active execution gate from the previously present `AGENTS.md` is now represented by `scope/allowed-hosts.txt`.
- Start from the public URLs already in `findings/findings_draft.md`: downloads overview, docs hub, main sitemap, support-portal privacy policy, LiMa/License Manager public pages, and CycurFUZZ public download/product pages.

## 2026-07-04 Class 0 passive baseline
- Sent 5 HEAD requests to public ETAS starting URLs from `scope/current-scope.md` / `findings/findings_draft.md`.
- All five returned `200`.
- No vulnerabilities confirmed; header/status observations only.
- No active payload testing, login, form submission, crawling, or API/license/portal interaction was performed.

## 2026-07-04 sitemap refresh
- Sent 1 GET request to `https://www.etas.com/ww/en/t-sitemap.xml`.
- Parsed locally from `/tmp/etas_en_t_sitemap.xml`.
- Current counts: 614 total English URLs, 145 software download URLs, 153 support/training URLs, 81 cyber/security/Cycur URLs, 58 form/contact URLs, 2 license-related public URLs, and 6 training registration form URLs.
- No findings confirmed.

## 2026-07-04 checkpoint before further usage
- Stopped per operator instruction to register completed work before continuing.
- Sent 6 additional sequential GET requests to public sitemap-listed pages for local classification.
- Total external ETAS target requests in this continuation: 12.
- Saved HTML files in `/tmp` for offline review.
- No findings confirmed and no suspected findings opened.

## 2026-07-04 offline HTML parsing checkpoint
- Performed local-only parsing of the saved `/tmp` HTML files; no new external target requests.
- Total external ETAS target requests in this continuation remains 12.
- Observed public CAAS/DXF/metasearch configuration, public `apiKey`, CSRF metadata, and `_authorized=false` in saved unauthenticated HTML. These are context only, not findings.
- Observed navigation search forms only; no marker or search submission was sent.
- Identified external leads requiring approval before interaction: `forms.etas.com`, `btm.bosch.com` webforms assets, `dxf-services.bosch.com` service endpoints, and a `license.etas.com` CycurFUZZ download-login link for a 2.99 GB ZIP package.
- Current status: no confirmed vulnerabilities, no suspected findings, and no stop-condition response observed.

## 2026-07-04 local-only sitemap product inventory
- Parsed the saved English sitemap only; no new external target requests.
- Updated `recon/passive_sitemap_inventory.md` with refreshed counts: 614 English URLs, 145 software-download URLs, and 153 support/training URLs.
- Main public download clusters observed: RTA-CAR V12, RTA-CAR FSQP, ISOLAR-A V12, target/compiler-specific RTA-OS installers, INCA V7, ASCET, MDA V8, RTA-FBL STLA, and RTA-FBL GM.
- Security/training leads observed: CycurFUZZ protocol fuzz testing, automotive security, AUTOSAR security, cloud security, threat modeling, web application security, Windows security, and regional training registration routes.
- Current status remains observations only; no confirmed or suspected vulnerabilities.

## 2026-07-04 inert search-marker route check
- Sent 3 live GET requests with the inert marker `codex-etas-inert` to public ETAS search endpoints.
- Total external ETAS target requests in this continuation is now 15.
- Observed canonical redirects from `/search` to `/ww/en/index.html` and then to `/ww/en/`; the marker was preserved in the query string but not reflected in HTML.
- No external callback or state change occurred.
- Current status remains observations only; no confirmed or suspected vulnerabilities.

## 2026-07-04 workspace reorganization
- Reorganized the workspace into `scope/`, `recon/`, `findings/`, `handoff/`, `artifacts/`, `scripts/`, `governance/`, and `analysis-template/`.
- Kept `RoEAIFile.md` at the root as the authoritative RoE entry point.
- Moved the original flat `scope` file to `scope/current-scope.md`.
- Preserved zero-byte placeholder files in `legacy-placeholders/`.
- Added a reusable `analysis-template/` for future projects or target analyses.
- No external target requests were sent; total ETAS target requests remains 15.
