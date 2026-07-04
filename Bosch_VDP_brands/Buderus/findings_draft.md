# Buderus - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Bosch Home Comfort HVAC/heating brand with country portals, documents, partner apps, training and customer/extranet surfaces.
- Candidate root domains observed from official/public metadata: buderus.com, bosch-homecomfort.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `buderus.com`
- `www.buderus.com`
- `docs.buderus.com`
- `documents.buderus.com`
- `de.documents.buderus.com`
- `at.documents.buderus.com`
- `customer.buderus.com`
- `customer-qa.buderus.com`
- `extranet.buderus.com`
- `brandbook.buderus.com`
- `bosch-homecomfort.com`
- `docs.bosch-homecomfort.com`
- `service.bosch-homecomfort.com`
- `training-de.bosch-homecomfort.com`
- `training-nl.bosch-homecomfort.com`

## Public sources and documentation/app pivots
- https://www.buderus.com/en/
- https://www.bosch-homecomfortgroup.com/en/brands/buderus/
- https://play.google.com/store/apps/details?id=com.bosch.tt.buderus.partnerportal&hl=en_US

## Recon value / next passive steps
- Documents/manuals, extranet/customer portals, partner apps, training sites, and regional document hosts are prime recon categories.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
