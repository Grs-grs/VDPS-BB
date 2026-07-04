# Bosch Rexroth - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Industrial automation, hydraulics, drives/controls, marketplaces, community, and support portals.
- Candidate root domains observed from official/public metadata: boschrexroth.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `boschrexroth.com`
- `www.boschrexroth.com`
- `community.boschrexroth.com`
- `marketplace.boschrexroth.com`
- `store.marketplace.boschrexroth.com`
- `assets.marketplace.boschrexroth.com`
- `backoffice.marketplace.boschrexroth.com`
- `licensing.boschrexroth.com`
- `snapstore.boschrexroth.com`
- `mybodas.boschrexroth.com`
- `hydraulic-hub.boschrexroth.com`
- `develop.hydraulic-hub.boschrexroth.com`
- `staging.hydraulic-hub.boschrexroth.com`
- `serialvault.boschrexroth.com`
- `qr.boschrexroth.com`

## Public sources and documentation/app pivots
- https://www.boschrexroth.com/en/us/
- https://community.boschrexroth.com/

## Recon value / next passive steps
- Focus on public docs/downloads, app marketplace, support/community, licensing, serial/QR workflows, and OT product documentation.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
