# Azena - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Camera/security app platform; appears associated with Bosch-funded Security and Safety Things/Azena history and shutdown reporting.
- Candidate root domains observed from official/public metadata: azena.com, securityandsafetythings.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `azena.com`
- `www.azena.com`
- `developer.azena.com`
- `console.azena.com`
- `support.azena.com`
- `media.azena.com`
- `static.azena.com`
- `bossstore-adminconsole.azena.com`
- `bossstore-backoffice.azena.com`
- `developer.securityandsafetythings.com`
- `securityandsafetythings.com`

## Public sources and documentation/app pivots
- https://techcrunch.com/2022/12/06/bosch-shuts-down-its-app-store-for-ai-powered-internet-connected-cameras/
- https://visagetechnologies.com/case-studies/ip-camera-app-marketplace/

## Recon value / next passive steps
- Scope needs confirmation because public reporting indicates wind-down; keep to docs/metadata and archived/public marketplace/developer information.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
