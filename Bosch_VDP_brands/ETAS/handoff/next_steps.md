# Next Steps

## Safe Without More Approval

- Continue local-only parsing of saved files in `/tmp`.
- Refine product/version inventory from `recon/passive_sitemap_inventory.md`.
- Draft report skeletons for confirmed future findings.
- Clean duplicate or stale notes while preserving evidence history.

## Requires Exact Human Approval

- Any interaction with `forms.etas.com`.
- Any request to `license.etas.com` or license/download entitlement workflows.
- Any request to `dxf-services.bosch.com` or Bosch webforms assets.
- Any additional live input-marker testing beyond the completed search canonicalization check.
- Any form submission, login, account creation, upload, download of large files, or API request.

## Stop Conditions To Watch

- `429`, `503`, `504`, repeated `5xx`, connection reset, or latency above RoE thresholds.
- Redirect to an unapproved host.
- Any indication of secrets, personal data, customer data, or access to non-public records.
- Any workflow requiring state change or Class 2/Class 3 activity.
