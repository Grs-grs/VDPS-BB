# Observations

Stable non-vulnerability observations are recorded here for quick triage. Full request accounting and details remain in `findings_draft.md`.

## Current Observations

- Public ETAS pages expose expected SPA/CMS and DXF/metasearch configuration, including CAAS and `dxf-services.bosch.com` URLs.
- Public unauthenticated pages include CSRF metadata and `_authorized=false`.
- Navigation search forms are present in saved HTML.
- Public contact/demo/training pages reference `forms.etas.com` and Bosch webforms assets; interaction requires explicit approval.
- The CycurFUZZ public page references a `license.etas.com` download-login URL for a large ZIP package; interaction requires explicit approval.
- The inert search-marker check showed canonical redirects and no marker reflection in returned HTML.
- The saved sitemap inventory shows 614 English URLs, 145 software-download URLs, and 153 support/training URLs.
