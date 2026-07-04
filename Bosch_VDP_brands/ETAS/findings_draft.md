# ETAS - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Automotive software, middleware, cybersecurity, licensing, downloads, and docs ecosystem.
- Candidate root domains observed from official/public metadata: etas.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `etas.com`
- `www.etas.com`
- `api.etas.com`
- `api.edge.etas.com`
- `portal.edge.etas.com`
- `edge.etas.com`
- `license.etas.com`
- `licensetest.etas.com`
- `opensource.etas.com`
- `cycurguard.etas.com`
- `cycurguard-dev.etas.com`
- `cycurguard-test.etas.com`
- `findingdb.sec.etas.com`
- `pmant.sec.etas.com`
- `brand.etas.com`
- `forms.etas.com`
- `go.etas.com`

## Public sources and documentation/app pivots
- https://www.etas.com/ww/en/
- https://www.etas.com/ww/en/downloads/

## Recon value / next passive steps
- Interesting first-pass buckets: downloads, license portals, security/cybersecurity product surfaces, edge/cloud portals, and public docs.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
