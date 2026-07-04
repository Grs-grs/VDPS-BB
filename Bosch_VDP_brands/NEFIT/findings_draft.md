# Nefit Bosch - passive recon findings

## Methodology and safety
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Scope/ownership notes
- Regional Bosch Home Comfort/HVAC brand in the Netherlands with partner portal, academy, docs, apps/tools.
- Candidate root domains observed from official/public metadata: nefit-bosch.nl, nefit.nl.

## Passive subdomain leads
The following hostnames were collected from public Certificate Transparency and public metadata. They are not proof of authorization or active scope.

- `nefit-bosch.nl`
- `nefit.nl`
- `www.nefit.nl`
- `partner.nefit.nl`
- `www.partner.nefit.nl`
- `academy.nefit.nl`
- `www.academy.nefit.nl`
- `nl.documents1.nefit.nl`
- `nl.documents2.nefit.nl`
- `cascadeselector.nefit.nl`
- `solarlineselector.nefit.nl`
- `mta-sts.nefit.nl`

## Public sources and documentation/app pivots
- https://www.nefit-bosch.nl/professioneel/installateurs/apps-en-online-tools/
- https://play.google.com/store/apps/details?id=com.bosch.tt.nefit.partnerportal&hl=en_US

## Recon value / next passive steps
- Partner portal/app, installer tools, document hosts, academy/training, and product selectors are useful passive leads.
- Confirm official VDP scope and rules of engagement before any active validation.
- Enrich with app-store package IDs, public docs/download URLs, robots/sitemap references, and historical CT deltas.
