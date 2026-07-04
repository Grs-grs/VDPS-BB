# ctrlX OS - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Bosch Rexroth industrial automation OS/ecosystem; exact public naming is ctrlX OS / ctrlX AUTOMATION, not ctrIX.
- Candidate root domains observed from official/public metadata: ctrlx-os.com, boschrexroth.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `ctrlx-os.com`
- `www.ctrlx-os.com`
- `mta-sts.ctrlx-os.com`
- `snapstore.boschrexroth.com`
- `marketplace.boschrexroth.com`
- `store.marketplace.boschrexroth.com`
- `assets.marketplace.boschrexroth.com`
- `community-stage.mybodas.boschrexroth.com`
- `developer-stage.community.boschrexroth.com`
- `ctrlx-configurator-platform.boschrexroth.com`
- `licensing.boschrexroth.com`

## Public sources and documentation/app pivots
- https://www.ctrlx-os.com/en/
- https://www.boschrexroth.com/en/us/rexrothi40/products/ctrlx-automation/
- https://community.boschrexroth.com/

## Recon value / next passive steps
- Prioritize store/marketplace, snap/app distribution, licensing, community, and documentation surfaces.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
