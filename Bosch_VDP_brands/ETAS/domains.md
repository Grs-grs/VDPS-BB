# ETAS - domains and subdomains

## Methodology and safety
- Passive-only OSINT: official/public metadata and Certificate Transparency via Cert Spotter API.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, account creation, or high-volume scraping was performed.
- Hostnames are reconnaissance leads for authorization/scope confirmation only.

## Candidate root domains / zones
- `etas.com`
- `docs.etas.com`
- `license.etas.com`
- `edge.etas.com`
- `sec.etas.com`
- `research.etas.com`

## Passive CT/public hostname leads
- `admin-api.edge.etas.com`
- `api-iot.edge.etas.com`
- `api-sf.edge.etas.com`
- `api.edge.etas.com`
- `api.etas.com`
- `artifactory.edge.etas.com`
- `as2.platform.cloudhub.etas.com`
- `as2.portal.cloudhub.etas.com`
- `as2.project.cloudhub.etas.com`
- `auth.infra.cloudway.etas.com`
- `bosch-model-farm.llm-gateway.research.etas.com`
- `brand.etas.com`
- `ccf-services-001.etas.com`
- `click.info.etas.com`
- `commonui.etas.com`
- `cycurguard-dev.etas.com`
- `cycurguard-test.etas.com`
- `cycurguard.etas.com`
- `device-uploads.edge.etas.com`
- `edge.etas.com`
- `etas.com`
- `findingdb.sec.etas.com`
- `fnoassist.license.etas.com`
- `forms.etas.com`
- `go.etas.com`
- `image.info.etas.com`
- `info.etas.com`
- `kafka-ui.edge.etas.com`
- `license.etas.com`
- `licensetest.etas.com`
- `mobility-qa-cp-files.edge.etas.com`
- `mobility-qa-feu-files.edge.etas.com`
- `model-farm.llm-gateway.research.etas.com`
- `mta-sts.etas.com`
- `nifi.edge.etas.com`
- `opensource.etas.com`
- `pmant.sec.etas.com`
- `portal-sf.edge.etas.com`
- `portal.edge.etas.com`
- `rm-q.etas.com`
- `rm.etas.com`
- `rollout.edge.etas.com`
- `rtahotline.etas.com`
- `sf.edge.etas.com`
- `twin.edge.etas.com`
- `view.info.etas.com`
- `www.etas.com`
- `xac.etas.com`

## CT delta notes
- Passive Cert Spotter sample: 100 recent issuance entries, 48 unique hostnames.
- Sample year distributihttps://github.com/Grs-grs/VDPS-BB/pull/5/conflict?name=Bosch_VDP_brands%252FETAS%252Fdomains.md&ancestor_oid=51b140b09cf794f7c5d3ef2aecce917f812b26cb&base_oid=059ef852e318cde2ebc91092c20968761737eaf5&head_oid=d6ce212f64ed6c134d6018aa724f489783526435on: 2025 = 69 issuance entries; 2026 = 31 issuance entries.
- Recent 2026 names to watch passively: `bosch-model-farm.llm-gateway.research.etas.com`, `model-farm.llm-gateway.research.etas.com`, `fnoassist.license.etas.com`, `admin-api.edge.etas.com`, `mobility-qa-cp-files.edge.etas.com`, `mobility-qa-feu-files.edge.etas.com`, `portal.edge.etas.com`, `api.edge.etas.com`, `findingdb.sec.etas.com`, `pmant.sec.etas.com`.
- Passive-only OSINT: public search results, official web/app/documentation pages, Certificate Transparency via Cert Spotter API, and already-public metadata.
- No authentication, exploitation, fuzzing, port scanning, vulnerability probing, or high-volume scraping was performed.
- Treat development, QA, admin, portal, and partner-looking hosts as scope-confirmation leads only; do not test without explicit authorization.

## Candidate root domains
- etas.com

## Passive CT/public hostname leads
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
