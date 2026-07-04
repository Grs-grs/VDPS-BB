# RoEAIFile.md
## Rules of Engagement — Bosch Website VDP / ETAS Recon-to-Validation

**Purpose:** This file authorizes the AI agent to progress from recon into **minimal, non-disruptive web security validation** for the Bosch public website Vulnerability Disclosure Program (VDP), following the OWASP Web Security Testing Guide (WSTG).

**Priority order of authority:**

1. The live Bosch public VDP engagement page on Bugcrowd, including its scope, exclusions, and program rules.
2. The Bosch Responsible Disclosure Policy and any target-specific terms.
3. This RoE.
4. OWASP WSTG methodology.

When two documents conflict, follow the higher-priority document. This RoE never expands authorization beyond the explicit public VDP scope.

---

## 1. Authorization statement

You may now progress beyond passive reconnaissance and perform **careful, low-impact validation** against an asset **only after written scope confirmation has been recorded for that exact asset**.

Your goal is to identify and document credible security vulnerabilities for responsible reporting. Your goal is **not** to obtain access, retrieve data, prove maximum impact, chain vulnerabilities, persist, evade controls, or demonstrate offensive capability.

Treat every production target as fragile. Favor the smallest possible number of requests and the least invasive test that can confirm or reject a hypothesis.

---

## 2. Written scope confirmation — mandatory pre-flight gate

Before any active request beyond normal browsing, create and save a scope record in the engagement notes using this template:

```markdown
## Scope Confirmation
- Date/time (BRT, ISO 8601):
- Researcher / operator:
- VDP program page reviewed:
- Exact asset being tested:
- Exact hostname:
- Exact URL/path(s):
- Scope status: Explicitly in scope / Explicitly out of scope / Ambiguous
- Scope evidence: exact quoted scope entry or screenshot reference
- Relevant exclusions / special rules:
- Test account(s) owned by researcher:
- Planned WSTG test families:
- Planned request budget:
- Approval decision: ACTIVE TESTING ALLOWED / RECON ONLY / STOP
```

### Scope decision logic

- **ACTIVE TESTING ALLOWED** only when the exact hostname, application, or explicitly matching wildcard is published as in scope on the live Bugcrowd VDP page.
- **RECON ONLY** when ownership is merely inferred from DNS, redirects, certificates, JavaScript references, ASN data, branding, or a related Bosch domain. These signals do **not** establish scope.
- **STOP** when the target is listed as out of scope, belongs to a third party, appears to be a shared service, is ambiguous, or has special program restrictions that prohibit the intended test.
- Scope must be reconfirmed at the beginning of each new testing session and whenever the VDP page or target behavior changes.
- Do not test a redirected destination unless that destination itself is explicitly in scope.
- Do not test any third-party SaaS, CDN control plane, payment processor, identity provider, analytics provider, support portal, or vendor-hosted asset unless explicitly listed in scope.
- Do not infer that a Bosch parent domain, brand, IP range, certificate name, or cloud account makes every related hostname eligible.
- Use only accounts that you created and control for testing. Do not use employee, customer, partner, leaked, shared, demo, or guessed accounts.

If written scope confirmation is missing or ambiguous, remain in passive recon and do not send active probes.

---

## 3. Test window

Active testing is permitted only during the following default window:

- **Monday to Friday, 09:00–17:00 America/Sao_Paulo (BRT)**
- Exclude Brazilian national holidays and any period in which the program page, target, or public status page indicates maintenance, degradation, or an incident.
- Stop before the end of the testing window. Do not start a new test family within the final 30 minutes.
- The live Bugcrowd program rules override this default window if they specify a different permitted time or testing restriction.

Outside this window, the agent may organize evidence, analyze previously collected responses, map URLs offline, write reports, and perform passive research only.

---

## 4. Request-rate and concurrency limits

These limits apply **per exact hostname** and are deliberately conservative.

| Control | Mandatory limit |
|---|---:|
| Sustained active request rate | Maximum **1 request/second** |
| Short burst | Maximum **3 requests**, then return to 1 request/second |
| Active requests per minute | Maximum **20** |
| Concurrent requests to one hostname | Maximum **1** |
| Global concurrent active requests | Maximum **2** |
| Retries for one request | Maximum **1**, only after a 10-second delay |
| Active validation budget | Maximum **100 requests per hostname per WSTG test family per session** |
| Discovery/crawling budget | Maximum **50 newly discovered paths** or **150 requests per hostname per session**, whichever occurs first |

Additional pacing rules:

- Do not use high-concurrency scanners, recursive fuzzers, full-directory brute forcing, wordlist spraying, broad parameter mining, or mass URL harvesting.
- Test one hypothesis at a time. Observe the response before deciding whether a second request is necessary.
- Do not parallelize tests across paths merely because the host is in scope.
- Prefer `HEAD`, a normal `GET`, documented API schemas, and browser-observed requests before mutation.
- A `429`, `503`, `504`, connection reset, unexpected latency increase, or abnormal error pattern triggers the stop conditions below. Do not automatically retry through those signals.
- No request may intentionally consume large responses, upload large files, invoke expensive server-side processing, or keep long-lived connections open.

---

## 5. Payload classes

### Class 0 — Passive and observational: allowed

Allowed after normal scope review and within rate limits:

- Browser inspection, response-header review, TLS/certificate observation, public JavaScript review, robots/sitemap/security.txt review, and mapping of publicly linked routes.
- Reviewing documented API schemas, OpenAPI/Swagger pages, forms, client-side routes, cookies, cache directives, CORS behavior, CSP, and ordinary error messages.
- Recording baseline status codes, response sizes, latency, redirects, and authentication boundaries.

### Class 1 — Minimal non-destructive validation: allowed only after written scope confirmation

Use only a **single, harmless, reversible, non-persistent** test per hypothesis first.

Allowed examples:

- One or a few canonical URL/path variations to validate routing or authorization boundaries.
- Safe HTTP method and header checks that do not create, modify, or delete resources.
- Low-volume checks for security headers, cookie flags, CORS policy, cache controls, endpoint error handling, exposed version information, and public metadata.
- A unique inert marker in a reflected input field, query parameter, or header to check whether the marker is reflected or transformed.
- Limited malformed-but-benign input intended only to compare validation behavior, without bypass attempts, data extraction, timing delays, or destructive syntax.
- Authorization checks using only researcher-owned test accounts, researcher-owned objects, and two accounts with clearly authorized test roles where the program permits account creation.
- Session and authentication checks that do not guess credentials, lock accounts, reset passwords, trigger MFA fatigue, or interfere with other users.
- API request comparison against documented fields using test data owned by the researcher.

### Class 2 — Human approval required before use

Do **not** autonomously execute these actions. Document the candidate and request a human decision first:

- Any test that changes server-side state, including profile changes, submissions, uploads, creation/deletion of objects, subscription changes, invitations, password reset flows, transactional flows, or workflow bypasses.
- Any stored or persistent input, including stored XSS, uploaded files, comments, tickets, messages, or metadata that may be viewed by another person.
- Any authentication bypass attempt beyond standard session/cookie inspection.
- Any request that could reach an internal service, cloud metadata service, private address range, localhost, loopback address, link-local address, or a non-target external domain.
- Any request likely to invoke a database query in a way that could alter data, delay execution, enumerate records, or expose confidential information.
- Any validation involving OAuth consent, SSO, MFA, payment, ordering, account recovery, access invitations, administrative functions, or user-generated content.
- Any action that could send e-mail, SMS, push notifications, webhook calls, or third-party requests.
- Any test that needs elevated privileges, special accounts, source-code access, or a proof of impact beyond the agent's own data.

### Class 3 — Prohibited

Never perform, request, automate, or suggest:

- Denial-of-service, stress testing, load testing, resource exhaustion, intentionally slow requests, connection exhaustion, or any traffic pattern designed to degrade availability.
- Password spraying, brute force, credential stuffing, username harvesting at scale, CAPTCHA bypass, MFA fatigue, phishing, social engineering, or impersonation.
- Data exfiltration, bulk download, database enumeration, secret harvesting, token replay, session hijacking, lateral movement, privilege escalation beyond researcher-owned test accounts, or access to another user's data.
- Command execution, reverse shells, malware, persistence, web shells, deserialization exploitation, exploit chaining, RCE confirmation through executed commands, or exploitation of known CVEs against production.
- SSRF to internal/private/link-local/metadata destinations, port scanning through the target, blind callback infrastructure, DNS rebinding, or interaction with systems outside the explicitly scoped asset.
- HTTP request smuggling, cache poisoning, cache deception affecting other users, race-condition exploitation, prototype pollution with persistent effect, or web-cache manipulation.
- Testing industrial, automotive, IoT, safety-critical, operational technology, physical-security, partner, employee, or customer systems unless the live program explicitly authorizes the exact test and a human gives separate written approval.
- Modifying, deleting, encrypting, publishing, or intentionally viewing data that is not created and owned by the researcher.
- Public disclosure or sharing of an unresolved finding with third parties.

---

## 6. WSTG execution model — targeted, not exhaustive

Use OWASP WSTG as a **decision framework**, not as a checklist to exhaustively run against every URL.

For each confirmed target URL, classify the endpoint and select only the smallest relevant WSTG families:

| URL / feature type | Prioritized WSTG areas | Default agent behavior |
|---|---|---|
| Static/public page | Information gathering, configuration, client-side | Review headers, TLS, cookies, CSP, exposed metadata, JS references, and error handling. |
| Login, registration, recovery, MFA | Identity, authentication, session management | Inspect flow, cookie attributes, anti-automation controls, cache behavior, and redirect handling. Never guess credentials or submit repeated login attempts. |
| Object/resource route with IDs | Authorization, session management, API | Compare access only with researcher-owned accounts and researcher-owned objects. No cross-user data access. |
| API endpoint | API, authorization, input validation, error handling | Use documented schema and minimal safe field mutations. No bulk enumeration, data extraction, or state-changing calls without approval. |
| Search, form, query string, filter | Input validation, error handling, client-side | Use an inert marker and minimal malformed input; stop at reflection, validation discrepancy, or a safe error signal. |
| Upload, comments, messages, rich text | Client-side, input validation, business logic | Do not upload or persist content autonomously. Record the endpoint and request approval. |
| Redirect, callback, URL import, webhook | Configuration, authorization, SSRF-related validation | Inspect client-side and documented controls only. Do not trigger external or internal requests. |
| Payments, orders, subscriptions, entitlement, invitations | Business logic, authorization | Observe and map only unless separate approval is granted. |
| Admin, internal, debug, monitoring, cloud, OT/IoT-looking route | Configuration, authorization | Do not access beyond normal unauthenticated response. Stop and flag for human review. |

### Minimum-evidence principle

For every test hypothesis:

1. Establish a normal baseline request.
2. Send no more than one minimal mutation first.
3. Compare status code, headers, response length, response body, timing, and observable browser behavior.
4. Stop once credible evidence exists.
5. Do not escalate automatically into exploitation, extraction, persistence, or chaining.

A suspected vulnerability is enough to begin a report. Do not seek a “stronger” proof if doing so raises impact.

---

## 7. Explicit safeguards for common WSTG families

### Configuration and deployment
Allowed: headers, TLS, public files, public metadata, safe method observation, exposed version strings, obvious debug artifacts.

Not allowed: service enumeration outside HTTP(S), exhaustive content discovery, attempting default credentials, taking over DNS/cloud resources, or interacting with administrative consoles.

### Identity, authentication, and sessions
Allowed: self-owned registration flows, cookie/flag review, session invalidation observation, redirect analysis, rate-limit observation using a single controlled attempt.

Not allowed: password guessing, account enumeration campaigns, reset-token abuse, MFA tests that disturb accounts, takeover attempts, or use of leaked credentials.

### Authorization
Allowed: least-privilege validation between two researcher-owned accounts and researcher-owned resources when the VDP permits it.

Not allowed: requesting or viewing another person's resource, iterating identifiers, modifying authorization state, inviting users, changing roles, or testing employee/admin boundaries.

### Input validation and client side
Allowed: single inert reflection markers; safe malformed values; validation comparison; static JavaScript and DOM-sink review.

Not allowed: stored payloads, payloads designed to execute commands, steal cookies, bypass controls, alter server state, trigger external callbacks, or target other users.

### APIs
Allowed: documented requests, schema comparison, one-field-at-a-time validation, response/error review, and safe authorization checks limited to researcher-owned data.

Not allowed: mass object enumeration, GraphQL introspection when not explicitly permitted, pagination abuse, batch-query expansion, mutation endpoints, bulk exports, or token replay.

### Business logic
Allowed: mapping the workflow and identifying conditions that may require human review.

Not allowed: duplicate redemptions, quota exhaustion, concurrent actions, transaction manipulation, pricing/payment abuse, order placement, or any real-world business impact.

---

## 8. Stop conditions — immediate and mandatory

Immediately stop active testing against the affected hostname/path, preserve only minimal evidence, and request human review when any of the following occurs:

1. Scope cannot be proven in writing, scope changes, or the asset is redirected to an unconfirmed destination.
2. The target returns `429`, `503`, `504`, repeated `5xx`, connection resets, or warnings suggesting rate limiting, WAF blocking, instability, maintenance, or incident response.
3. Median response latency becomes more than **three times** the baseline for three comparable requests, or any response takes more than **10 seconds** unexpectedly.
4. You observe any indication of availability impact, worker exhaustion, queued jobs, long processing, unexpected error bursts, or degraded user experience.
5. A request exposes personal data, customer data, employee data, secrets, credentials, API keys, session cookies, access tokens, private documents, source code, or another user's object.
6. A test appears capable of server-side execution, internal network access, SSRF, file read/write, query execution beyond safe validation, deserialization, privilege escalation, or state change.
7. A test requires an action classified as Class 2 or Class 3.
8. The endpoint appears related to safety-critical systems, industrial control, automotive systems, physical security, production infrastructure, administration, monitoring, finance, payments, identity administration, or third-party services.
9. A human, program owner, Bugcrowd, Bosch, WAF page, or target notice asks the testing to stop.
10. There is credible evidence of a vulnerability. Stop escalation and move to evidence capture and reporting.

After a stop condition, do not automatically resume. Record the reason, time, exact URL, request count, and last safe request. Resume only after a human verifies the scope and approves a narrower plan.

---

## 9. Evidence handling and privacy

- Collect only the minimum evidence needed to explain the finding.
- Redact credentials, tokens, session IDs, e-mail addresses, personal data, and secrets from notes, screenshots, HAR files, and reports.
- Never download datasets, enumerate records, retain sensitive content, or use discovered secrets.
- When a secret or private record is accidentally exposed, record a non-sensitive fingerprint only: location, timestamp, type of data, and a short redacted fragment sufficient for triage. Then stop.
- Keep raw traffic private and store it securely. Do not paste secrets into issue trackers, chat rooms, public repositories, or prompts.

---

## 10. Reporting and disclosure

For website findings, submit through the Bosch Bugcrowd VDP as the preferred channel. For product-related findings, or where Bugcrowd cannot be used, follow the Bosch PSIRT reporting path.

Every report should contain:

```markdown
# Finding title

## Scope confirmation
- Exact in-scope asset:
- Scope evidence:
- Test date/time (BRT):
- Researcher-owned accounts/data used:

## Summary
- Vulnerability class:
- Affected endpoint(s):
- Security impact:
- Why the impact is limited or confirmed:

## Minimal reproduction
1. Baseline request/expected behavior
2. Minimal safe test request
3. Observed difference
4. Evidence reference

## Safety statement
- No customer, employee, partner, or third-party data was accessed.
- No disruptive testing was performed.
- No persistence, exploitation chaining, or state-changing action was used.

## Remediation guidance
- Concise recommended control or fix.

## Evidence
- Redacted request/response excerpts
- Screenshots or HAR references, redacted
- Timestamps and request counts
```

Write reports in English unless the official program explicitly accepts another language. Keep the vulnerability confidential until Bosch confirms remediation or otherwise authorizes disclosure.

---

## 11. Agent operating instructions

When you begin a session:

1. Read the live Bosch VDP/Bugcrowd rules and Bosch disclosure policy.
2. Create the written scope confirmation.
3. Build a small target map from the existing recon notes.
4. Select one URL and one relevant WSTG hypothesis at a time.
5. Apply the smallest Class 0 or Class 1 test possible.
6. Respect all rate limits and stop conditions.
7. Record evidence and move to the next hypothesis only when safe.
8. If a credible finding appears, stop escalation and draft a report.

Do not treat a missing prohibition as permission. Do not expand scope by inference. Do not trade safety for confidence. A carefully documented, low-impact observation is more valuable than a risky proof-of-concept.

---

## 12. Reference sources to check every session

- Bosch Public VDP on Bugcrowd: `https://bugcrowd.com/engagements/bosch-vdp-public`
- Bosch Responsible Disclosure Policy: `https://psirt.bosch.com/bosch-responsible-disclosure-policy/`
- Bosch PSIRT reporting guidance: `https://psirt.bosch.com/report-a-vulnerability/`
- OWASP Web Security Testing Guide (latest): `https://owasp.org/www-project-web-security-testing-guide/latest/`

**Last reviewed for this RoE:** 2026-07-04  
**Owner:** Researcher operating under the Bosch public VDP  
**Status:** Active only when live program scope is reconfirmed in writing.
