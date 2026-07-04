# COBI / COBI.Bike - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Connected e-bike/mobile app ecosystem now referenced in Bosch eBike Systems material.
- Candidate root domains observed from official/public metadata: cobi.bike, cobibike.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `cobi.bike`
- `www.cobi.bike`
- `cdn.cobi.bike`

## Public sources and documentation/app pivots
- https://www.bosch.com/stories/connected-e-bike/
- https://www.bosch.com/stories/history-bosch-ebike-systems/

## Recon value / next passive steps
- Look for app-store metadata for COBI.Bike, Bosch eBike Systems pages, support/deprecation notices, and CDN-hosted static assets.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
