# False Positives

Use this file for items that were checked and should not be reported.

## Current Non-Findings

- Public SPA/CMS `apiKey` value in unauthenticated ETAS pages: public configuration only without evidence of unauthorized capability.
- Public CSRF metadata and `_authorized=false`: expected unauthenticated rendering context.
- Navigation search form markup: not a finding by itself.
- Public search route canonicalization with inert marker: marker was not reflected in returned HTML.
