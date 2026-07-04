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
- English sitemap sample: `https://www.etas.com/ww/en/t-sitemap.xml` contained 614 URLs in the 2026-07-04 local refresh saved at `/tmp/etas_en_t_sitemap.xml`.

## High-value URL groups from the English sitemap

### Software downloads
- Count observed for `/downloads/software-downloads-overview/`: 145 URLs in the 2026-07-04 local refresh.
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
- Count observed for `/support-training/`: 153 URLs in the 2026-07-04 local refresh.
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

## Docs examples worth passive review
- CycurRISK docs include a page titled `Accessing Swagger UI Rest-API Endpoint Documentation`; record as a documentation lead only, not an API probing target.
- LiMa docs include license access, borrowing, check status, FNE/FNP license, migration, upgrade, command prompt, error code, architecture, firewall extension, and troubleshooting topics.
- INCA docs include versioned V7.6 documentation and many add-on/new-feature pages.
- Hardware docs include setup, commissioning, accessories, certification/conformity, open-source software, standards/norms, and maintenance topics.

## Recommended passive refinements
1. Export sitemap URLs to a local CSV/Markdown table with columns: URL, product, version, category, source sitemap, observed date, and notes.
2. Build a product/version map from download URLs and docs versions.
3. Compare docs versions to download versions to identify possible outdated public artifacts or lifecycle questions.
4. Use public pages only to identify forms, login portals, entitlement language, support channels, and contact paths.
5. Keep API/Swagger, license, and portal references as passive notes until scope explicitly permits interaction.

## 2026-07-04 local-only product/version matrix

Source: already saved `/tmp/etas_en_t_sitemap.xml`. No new target requests were sent for this section.

### Download family clusters
| Family / cluster | URL count in saved sitemap | Notes |
| --- | ---: | --- |
| `rta-car-v12*` | 16 | Versioned RTA-CAR download pages, including product-installer variants. |
| `rta-car-fsqp*` | 16 | Versioned RTA-CAR FSQP download pages, including product-installer variants. |
| `isolar-a-v12*` | 14 | Versioned ISOLAR-A V12 pages from V12.0.2 through V12.10.0 observed. |
| `rta-os-*` | 41 | Many target/compiler-specific RTA-OS installer pages; treat as product-support inventory, not active targets. |
| `isolar-a-v11*` | 3 | V11.1.1, V11.2.3, and V11.3.3 observed. |
| `rta-fbl-stla*` | 3 | STLA bootloader pages for V2.0.0, V2.1.0, and V2.2.0 observed. |
| `rta-fbl-gm*` | 3 | GM bootloader pages plus a generic GM page observed. |
| `mda-v8*` | 3 | MDA V8.5.7, V8.6.7 HF1, and V8.7.7 observed. |
| `inca-v7*` | 5 | INCA V7.2 SP17, V7.3 SP7.4 64-bit, V7.4 SP7.1 64-bit, V7.5 service pack, and V7.6 observed. |
| `ascet*` | 4 | ASCET developer and ASCET V6 hotfix pages observed. |
| License pages | 2 | `license-server` and `lima-etas-license-manager`; no `license.etas.com` request was sent in this matrix step. |
| CycurFUZZ download | 1 | `escrypt-cycurfuzz-v2-1`; saved page points to a large license download-login package, requiring approval before interaction. |

### Security and training leads
- Security-related academy pages observed in the saved sitemap include automotive protocol fuzz testing with CycurFUZZ, automotive security, automotive security monitoring, AUTOSAR security, cloud security, information-security standards, security risk analysis, security testing, threat modeling, web application security, and Windows security.
- Training registration URLs observed for the world/global page plus Brazil, India, Italy, UK, and USA variants.
- These are context and business-logic mapping leads only. Do not submit registration, demo, contact, or training forms without explicit approval.

### Current evidence status
- Confirmed vulnerabilities: None.
- Suspected findings: None.
- Observations only: public product/version inventory, public training/form route inventory, and public license/download route inventory.
