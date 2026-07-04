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
| 10 | `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/` | Support portal privacy policy | High | Medium | Low | Main sitemap contains a support-portal privacy-policy URL; useful for identifying official support

# ETAS passive sitemap inventory

## Collection boundary
This inventory uses public robots/sitemap resources only. No brute force, crawling beyond declared sitemap URLs, path traversal payloads, endpoint enumeration, authentication, or vulnerability testing was performed.

## Main ETAS sitemap structure
- `https://www.etas.com/robots.txt` points to `https://www.etas.com/ww/sitemap.xml`.
- `https://www.etas.com/ww/sitemap.xml` is a sitemap index with language-specific sitemap files:
  - `https://www.etas.com/ww/en/t-sitemap.xml`
  - `https://www.etas.com/ww/de/t-sitemap.xml`
  - `https://www.etas.com/ww/fr/t-sitemap.xml`
  - `https://www.etas.com/ww/ja/t-sitemap.xml`
  - `https://www.etas.com/ww/zh/t-sitemap.xml`
  - `https://www.etas.com/ww/ko/t-sitemap.xml`
- English sitemap sample: `https://www.etas.com/ww/en/t-sitemap.xml` contained 616 URLs at collection time.

## High-value URL groups from the English sitemap

### Software downloads
- Count observed for `/downloads/software-downloads-overview/`: 146 URLs.
- Representative URLs:
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/etas-ralo-xcp/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/isolar-a-v12-10-0/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/rta-car-v12-10-0/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/rta-fbl-stla-v2-2-0/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/labcar-operator-product-installer/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/eatb-v6-2-0-product-installer/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/ehandbook-navigator-product-installer/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/embedded-ai-coder-installation-package/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/escrypt-cycurfuzz-v2-1/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/etas-ascmo-software-package/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/etas-data-operator-product-installer/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/hsp-hardware-service-pack/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/inca-v7-6/`

### License-related public URLs
- Count observed for `license` in English sitemap URLs: 2.
- URLs:
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/license-server/`
  - `https://www.etas.com/ww/en/downloads/software-downloads-overview/lima-etas-license-manager/`

### Cybersecurity / Cycur public pages
- Count observed for `cycur` in English sitemap URLs: 13.
- Representative URLs:
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurhsm/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycuranalyze/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurfuzz/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurids/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurlib/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycursoc/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurrisk/`
  - `https://www.etas.com/ww/en/products-services/cybersecurity-products/escrypt-cycurgate/`

### Broader security pages
- Count observed for `security` in English sitemap URLs: 76.
- Notable categories:
  - Cybersecurity topics and use cases.
  - Security academy/training pages.
  - Webinars on IDPS, HSM, SDV security, vulnerability management, CRA compliance, and supply-chain maturity.
  - Cybersecurity services pages covering audit, security design, testing, training, post-quantum cryptography, vulnerability management, and penetration-testing services.

### Support/training pages
- Count observed for `/support-training/`: 154 URLs.
- This area looks valuable for passive business-logic context because it includes academy pages, webinars, support/training flows, and possible forms.

### Support portal privacy-policy lead
- `https://www.etas.com/ww/en/data-protection-policy/etas-support-portal-privacy-policy/`
- This is useful for identifying official support-portal context and data handling language without logging into any portal.

## Docs sitemap structure
- `https://docs.etas.com/robots.txt` allows `/` and lists product-specific sitemaps.
- Product sitemap URL counts observed in sampled fetches:
  - `https://docs.etas.com/ascmo-moca/sitemap.xml` - 1562 URLs.
  - `https://docs.etas.com/cycurrisk/sitemap.xml` - 287 URLs.
  - `https://docs.etas.com/lima/sitemap.xml` - 460 URLs.
  - `https://docs.etas.com/inca/sitemap.xml` - 1407 URLs.
  - `https://docs.etas.com/hardware/sitemap.xml` - 367 URLs.
