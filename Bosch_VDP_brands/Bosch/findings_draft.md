# Bosch - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Corporate/global Bosch web estate across country sites, accounts, brand assets, code/dev portals, and product/service ecosystems.
- Candidate root domains observed from official/public metadata: bosch.com, bosch.de, bosch.us.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `bosch.com`
- `www.bosch.com`
- `bosch.us`
- `brandguide.bosch.com`
- `code.bosch.com`
- `audit.bosch.com`
- `deviceportal.bosch.com`
- `digital.bosch.com`
- `inside.bosch.com`
- `inside-q.bosch.com`
- `kms.wam-sso.bosch.com`
- `assets.bosch.com`
- `downloads.bosch-automotive.com`
- `api.bosch.com`

## Public sources and documentation/app pivots
- https://www.bosch.com/
- https://www.bosch.us/
- https://www.bosch.com/company/facts-and-figures/

## Recon value / next passive steps
- Very broad surface; segment by official program scope before deeper review. Account/SSO, brandguide, downloads/assets, device portals, and developer/code surfaces are priority leads.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
