# ETAS refined passive target candidates

## Purpose and safety boundary
This file narrows ETAS recon into high-confidence passive target candidates for later scope confirmation. It intentionally does **not** contain path traversal payloads, exploit strings, brute-force plans, endpoint enumeration instructions, or active test results. Any active validation must wait until Bosch/ETAS confirms the exact target is in scope and the rules of engagement permit that class of test.

## Candidate scoring model
- **Confidence:** likelihood the asset is ETAS/Bosch-owned based on official pages, CT, robots/sitemaps, or app-store publisher evidence.
- **Recon value:** usefulness for initial VDP scoping and low-risk follow-up.
- **Active-test sensitivity:** how risky the asset would be to touch beyond normal public browsing.

| Rank | Candidate | Type | Confidence | Recon value | Active-test sensitivity | Why it is a good starting point |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | `https://www.etas.com/ww/en/downloads/software-downloads-overview/` | Official download index | High | Very High | Medium | Public sitemap shows many software-download pages and product/version slugs; good for product inventory and version mapping without testing. |
| 2 | `https://docs.etas.com/` plus product sitemaps | Official docs hub | High | Very High | Low-Medium | Robots explicitly allows `/` and lists product-specific sitemaps; ideal for passive product/version/manual inventory. |
| 3 | `https://www.etas.com/ww/sitemap.xml` and `https://www.etas.com/ww/en/t-sitemap.xml` | Main-site sitemap | High | High | Low | Public sitemap has 616 English URLs including downloads, support/training, cybersecurity products, and use cases. |
| 4 | `license.etas.com` / `fnoassist.license.etas.com` | License/FNO surface | Medium-High | High | High | CT indicates license-related hosts; only passive documentation and scope clarification should be done before any interaction. |
| 5 | `api.etas.com` / `api.edge.etas.com` / `portal.edge.etas.com` | API/edge/cloud surface | Medium-High | High | High | CT indicates API and portal hosts; passive-only until explicit scope and API testing authorization exist. |
| 6 | `cycurguard.etas.com`, `cycurguard-dev.etas.com`, `cycurguard-test.etas.com` | Security-product-looking surface | Medium | Medium-High | High | CT names suggest product/dev/test surfaces; do not probe. Ask whether these are in scope. |
| 7 | `findingdb.sec.etas.com` / `pmant.sec.etas.com` | Security/internal-looking surface | Medium | Medium-High | Very High | Names are interesting for scope triage only; do not browse beyond public metadata unless explicitly authorized. |
| 8 | `model-farm.llm-gateway.research.etas.com` and Bosch variant | Research/LLM gateway-looking CT lead | Medium | Medium | Very High | Recent CT names; likely sensitive. Track passively and request explicit scope clarification only. |
| 9 | `https://apps.apple.com/us/developer/etas-gmbh/id596772516` | App-store publisher page | High | Medium | Low | Confirmed publisher lead for mobile/app inventory; no confirmed Google Play package yet. |
| 10 | `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/` | Support portal privacy policy | High | Medium | Low | Main sitemap contains a support-portal privacy-policy URL; useful for identifying official support-portal context without logging in. |

## Refined domain/category buckets

### Best passive-first public web targets
- `www.etas.com` - official corporate/product/download/support web estate.
- `docs.etas.com` - documentation hub with product sitemaps.
- `opensource.etas.com` - open-source/compliance-looking host from CT.
- `brand.etas.com` - brand/asset-looking host from CT.

### Best scope-confirmation targets before any active testing
- `license.etas.com`
- `fnoassist.license.etas.com`
- `api.etas.com`
- `edge.etas.com`
- `api.edge.etas.com`
- `portal.edge.etas.com`
- `admin-api.edge.etas.com`
- `cycurguard.etas.com`
- `findingdb.sec.etas.com`
- `pmant.sec.etas.com`
- `model-farm.llm-gateway.research.etas.com`

### Highest-value public documentation paths from sitemaps
- `/ww/en/downloads/software-downloads-overview/`
- `/ww/en/products-services/cybersecurity-products/`
- `/ww/en/products-services/cybersecurity-services/`
- `/ww/en/support-training/etas-academy/`
- `/ww/en/support-training/webinars/`
- `/ww/en/data-protection-policy/etas-support-portal-privacy-policy/`

## Product/documentation pivots worth inventorying first
- **Downloads:** RTA-CAR, RTA-FBL, ISOLAR-A, INCA, LABCAR, EATB, EHANDBOOK, Embedded AI Coder, ESCRYPT CycurFUZZ, ETAS ASCMO, Data Operator, ETK Tools, HSP, INTECRIO, RTA-OS.
- **Docs:** ASCMO-MOCA, ASCMO-STATIC/DYNAMIC, CycurRISK, Data Operator, EATB, EHANDBOOK, INCA, LiMa/FNO, MC-Gateway, MDA, XCT, hardware docs.
- **Cybersecurity public pages:** CycurHSM, CycurAnalyze, CycurFUZZ, CycurIDS, CycurLIB, CycurSOC, CycurRISK, CycurGATE, key-management, production-key, VSOC, vulnerability-management, penetration-testing services, security training.

## Non-disruptive business-logic hypotheses to research passively
These are not findings. They are safe hypotheses to convert into a scope question or documentation review item.

1. **Download entitlement clarity:** Determine from public pages whether installers are gated, export-controlled, license-gated, or freely downloadable. Do not bypass forms or controls.
2. **Version/support lifecycle mapping:** Compare public download versions with docs versions to identify stale public packages or unsupported versions that may need vendor clarification.
3. **License workflow documentation:** Review public LiMa/FNO docs for expected license borrowing, activation, return, and server flows. Do not attempt token/license operations.
4. **Support-portal data handling:** Use privacy-policy pages to identify support-portal data categories and official portal names before any account or workflow testing.
5. **Security-product demo/trial boundaries:** Determine whether CycurFUZZ/CycurRISK/security products expose trials, demos, downloads, or forms; do not submit forms with synthetic or misleading data.
6. **App ownership hygiene:** Confirm whether any mobile apps are still actively maintained by ETAS GmbH and whether store metadata points to official domains.
7. **Public docs disclosure hygiene:** Inventory docs that mention URLs, ports, license services, update servers, or API names; treat as architecture context, not as targets to probe.

## Path traversal / vulnerability probing note
The user asked whether a few URLs could be checked for path traversal or potential vulnerabilities. That was not performed because these are public Bosch/ETAS assets and the current confirmed boundary is passive recon only. Future active checks should only happen after written scope confirmation, with an agreed request rate, payload class, test window, and stop conditions.

- `xac.etas.com`