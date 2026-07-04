# Bosch Service - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Bosch Car Service, Bosch Service Solutions, aftermarket portals, workshop/service support.
- Candidate root domains observed from official/public metadata: boschcarservice.com, boschservicesolutions.com, boschaftermarket.com.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `boschcarservice.com`
- `www.boschcarservice.com`
- `app.boschcarservice.com`
- `app-qa.boschcarservice.com`
- `brandguide.boschcarservice.com`
- `bcs-portal.boschaftermarket.com`
- `portal.boschaftermarket.com`
- `shop.boschaftermarket.com`
- `store.boschaftermarket.com`
- `licenses.store.boschaftermarket.com`
- `helpcenter.boschaftermarket.com`
- `boschservicesolutions.com`
- `my.boschservicesolutions.com`
- `monitoring-portal.boschservicesolutions.com`
- `notification.boschservicesolutions.com`

## Public sources and documentation/app pivots
- https://www.boschcarservice.com/xc/en/
- https://www.boschservicesolutions.com/en/
- https://www.bcs-portal.boschaftermarket.com/gb/en/

## Recon value / next passive steps
- Workshop locator, BCS portal, aftermarket shop/licenses/helpcenter, and service-solution customer portals are useful passive pivots.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
