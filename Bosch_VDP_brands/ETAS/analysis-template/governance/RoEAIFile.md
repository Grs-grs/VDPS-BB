# Rules of Engagement Template

## Authority

- Program page:
- Disclosure policy:
- Target-specific terms:
- Local operator approval:

## Scope Confirmation Template

```markdown
## Scope Confirmation
- Date/time (local, ISO 8601):
- Researcher / operator:
- Program page reviewed:
- Exact asset being tested:
- Exact hostname:
- Exact URL/path(s):
- Scope status: Explicitly in scope / Explicitly out of scope / Ambiguous
- Scope evidence:
- Relevant exclusions / special rules:
- Test account(s) owned by researcher:
- Planned test families:
- Planned request budget:
- Approval decision: ACTIVE TESTING ALLOWED / RECON ONLY / STOP
```

## Operating Rules

- Use the minimum number of requests necessary.
- Do not fuzz, brute force, scan aggressively, or attempt exploitation.
- Do not submit forms, authenticate, upload, download large files, or change state without explicit approval.
- Stop on rate limits, instability, unexpected sensitive data, redirects to unapproved hosts, or credible vulnerability evidence.
