# TEKORA — Color Contrast, Typography Validation & UX Prototype Acceptance

**Status: PARTIAL.** A preliminary numerical contrast calculation was performed against the proposed light palette. It is not a full accessibility audit. Dark theme and category accent combinations are not yet certified.

## 1. Preliminary contrast calculation (WCAG relative luminance)
Method: sRGB channel linearization and WCAG contrast ratio formula. Thresholds: 4.5:1 for normal text, 3:1 for large text. Ratios below are rounded to two decimals only for display; pass/fail used unrounded values.

| Foreground | Background | Ratio | Normal text 4.5:1 | Large text 3:1 |
|---|---|---:|---|---|
| #101828 | #FFFFFF | 17.75:1 | PASS | PASS |
| #101828 | #F7F8FC | 16.72:1 | PASS | PASS |
| #475467 | #FFFFFF | 7.69:1 | PASS | PASS |
| #475467 | #F7F8FC | 7.24:1 | PASS | PASS |
| #667085 | #FFFFFF | 4.97:1 | PASS | PASS |
| #667085 | #F7F8FC | 4.69:1 | PASS | PASS |
| #315EFB | #FFFFFF | 5.09:1 | PASS | PASS |
| #FFFFFF | #315EFB | 5.09:1 | PASS | PASS |
| #14B8A6 | #FFFFFF | 2.49:1 | FAIL | FAIL |
| #067647 | #FFFFFF | 5.69:1 | PASS | PASS |
| #B54708 | #FFFFFF | 5.43:1 | PASS | PASS |
| #B42318 | #FFFFFF | 6.57:1 | PASS | PASS |
| #175CD3 | #FFFFFF | 5.99:1 | PASS | PASS |
| #244AD6 | #FFFFFF | 6.94:1 | PASS | PASS |

### Required correction
- Keep #14B8A6 as a decorative/graphic accent only on white until tested; do not use it for small text, icons conveying essential meaning, or component boundaries that need 3:1.
- Candidate darker teal for text: #0F766E; still test against each actual surface before approval.
- Category accents are not semantic status colors. Do not use an accent as text by default.
- Validate focus ring against adjacent surfaces, control borders, disabled states, chart lines and dark theme separately.

## 2. Theme acceptance
For Light, Dark and System: complete token matrix for canvas/surface/elevated surface/text/muted text/border/interactive/focus/success/warning/danger/info/category accents. Test every pair actually used. Ensure no theme inversion shortcuts. Test OS preference changes and persisted preference behavior. High-contrast/forced-colors mode must retain meaningful affordances.

## 3. Font selection experiment
Candidates: Manrope (display), Source Sans 3 (body/UI), IBM Plex Mono (code/data); compare Geist Sans/Mono and Geist Serif only as alternatives. Before selection:
- Confirm license and allowed self-hosting/redistribution for each exact font file.
- Test Swahili/English, Latin Extended, punctuation, combining marks, numerals, currency, code and long identifiers.
- Test variable/static files, weights, hinting, WOFF2 subsets, fallback and font-display.
- Compare line wrapping, x-height, legibility at 12–16px, table density, mobile and 200% zoom.
- Measure transferred bytes and LCP/CLS impact on cold mobile connections.
- Produce specimens with: “Huduma za TEKORA”, “Namba ya malipo”, “Shughuli zilizokamilika”, “TZS 1,250,000.50”, “Müller, José, Łukasz”, “IPv6 / OAuth 2.0 / webhook_id”.
No font is approved by name alone.

## 4. Prototype screens required before design sign-off
1. Public home and 22-category catalogue; category detail with availability, provider/delivery model, inclusions/exclusions and price caveats.
2. Product detail and quote flow with total, tax treatment, prerequisites and terms.
3. Organization/project onboarding and role/member management.
4. Customer overview with resources, activity and next safe actions.
5. Product provisioning timeline including UNKNOWN/reconciliation and recovery.
6. Billing centre: quote, invoice, payment attempt, Control Number lifecycle, receipt and reconciliation exception.
7. Developer Hub: API catalogue, project, sandbox/live separation, credential reveal-once, request inspector and webhook simulator/replay.
8. Internal operations: approvals, provider health, manual review queues, audit and support.
9. Incident/status and customer notification preferences.
10. Responsive mobile navigation and high-density desktop operations table.

Every prototype includes success, pending, unknown, empty, loading, validation, permission-denied, provider-unavailable, partial failure, retry-safe and non-retry-safe states.

## 5. Usability test plan
Recruit representative prospective users: non-technical small-business owner, developer, finance operator, internal service operator and administrator. Do not fabricate participants or results. Task examples: find a product and understand total cost; create a project; create sandbox credential and revoke it; interpret a pending payment; find a control number and expiry; diagnose a failed provisioning operation; request support; change notification preferences. Capture completion, errors, time-on-task, comprehension, confidence and accessibility barriers. Obtain consent and avoid collecting unnecessary personal data.

## 6. Design approval checklist
- [ ] Benchmark references and rationale recorded.
- [ ] IA and task flows approved.
- [ ] Light/dark/system token contrast matrix calculated.
- [ ] All text, icon, border, focus and chart pairs checked.
- [ ] Fonts license-checked and language specimens passed.
- [ ] Responsive prototypes at mobile/tablet/desktop and 200% zoom.
- [ ] Keyboard-only and screen-reader review.
- [ ] Reduced motion and forced-colors review.
- [ ] Empty/loading/error/pending/unknown/recovery states.
- [ ] Usability sessions and issues recorded.
- [ ] Performance budget and measured results.
- [ ] Design tokens/components and handoff documented.

**Result:** Light-theme text palette has several passing combinations, while teal #14B8A6 fails as text on white. Full design approval remains BLOCKED on complete pair matrix, dark theme, font license/specimen/performance checks and usability evidence.
