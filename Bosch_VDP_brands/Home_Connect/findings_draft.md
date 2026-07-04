# Home Connect - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Smart-appliance mobile app, cloud API, developer portal, and BSH/Bosch connected-appliance ecosystem.
- Candidate root domains observed from official/public metadata: home-connect.com, developer.home-connect.com, api-docs.home-connect.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `home-connect.com`
- `developer.home-connect.com`
- `api-docs.home-connect.com`
- `api.home-connect.com`
- `simulator.home-connect.com`

## Public sources and documentation/app pivots
- https://developer.home-connect.com/
- https://api-docs.home-connect.com/
- https://www.bosch-home.com/us/experience-bosch/home-connect
- https://apps.apple.com/hr/app/home-connect-app/id901397789

## Recon value / next passive steps
- Public API docs, OAuth/app registration flows, simulator, mobile apps, and SingleKey/BSH account dependencies are useful recon pivots.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
