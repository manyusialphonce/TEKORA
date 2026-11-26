# TEKORA — Global Design System, Color, Typography & UX Specification

**Status: PROPOSED / PARTIAL.** This is a design direction and measurable specification, not a claim that contrast calculations, prototypes, usability tests or accessibility audits are complete.

## 1. Experience principles
Clarity before decoration; progressive disclosure; trust through evidence; calm operational interfaces; fast paths for experts and guided paths for newcomers; consistent cross-category behavior; responsive-first design; accessibility by default. Every page must explain where the user is, what can be done, cost/limits, what happens next and who is responsible.

## 2. Benchmarking plan
Study Stripe for payments, billing, test/live separation and API debugging; Vercel for project/deployment workflows and design-system discipline; Cloudflare for account/zone hierarchy and network/security controls; DigitalOcean for approachable infrastructure selection; Supabase for project-first developer onboarding; Twilio for channel/provider delivery events; Linear for fast navigation, keyboard efficiency and calm information density. For each inspected flow record source URL/date, user problem, observed pattern, adopt/adapt/reject decision, accessibility impact and TEKORA rationale. Do not claim inspection without evidence and do not copy proprietary assets, brand or text.

## 3. Information architecture
**Public marketplace:** home, catalogue, category/product detail, eligibility/prerequisites/limits, verified plans/pricing, provider/integrations, docs/API, status, trust/security/privacy/support, sign-in/onboarding.

**Customer portal:** overview, organization/members/roles, projects/environments, catalogue/orders, resources/configuration, deployments/activity, usage/cost/budgets, billing/invoices/payments/subscriptions/Control Numbers, integrations/credentials/webhooks, support/incidents/health, notifications/audit/settings.

**Developer hub:** API catalogue/version, quickstarts/docs/SDK/CLI, projects/environments, sandbox credentials/simulator, API explorer/request history/errors, webhook endpoint/delivery/replay/signature, usage/quotas/rates/billing, live access request, changelog/deprecation/status.

**Internal operations:** work queues/approvals, scoped customer/resource lookup, orders/provisioning, provider health, finance/control-number exceptions/reconciliation, delivery/projects/contracts, support/incidents, security/access reviews/audit, catalog/SKU/price governance, capacity/cost/reliability. Navigation is role/context-aware; frontend hiding is never authorization.

## 4. Visual direction and color system
**Direction:** premium technical editorial; crisp, precise, calm, human and confident. Light-first neutral surfaces with restrained cobalt and teal anchors. Avoid generic dark admin templates, excessive gradients, neon, glassmorphism and unnecessary card stacking.

### Provisional global tokens
| Token | Value | Role |
|---|---|---|
| Brand primary | #315EFB | Primary action, links, selected navigation |
| Primary hover | #244AD6 | Hover/active |
| Brand deep | #1736A8 | High-emphasis brand surface |
| Teal accent | #14B8A6 | Secondary accent |
| Ink | #101828 | Primary text |
| Secondary text | #475467 | Secondary text |
| Muted text | #667085 | Supporting text; pair-test |
| Canvas | #F7F8FC | App background |
| Surface | #FFFFFF | Panels/menus |
| Subtle surface | #F2F4F7 | Grouping |
| Border | #E4E7EC | Dividers/outlines |
| Focus candidate | #84ADFF | Focus ring; pair-test |
| Success | #067647 | Success |
| Warning | #B54708 | Warning |
| Danger | #B42318 | Error/destructive |
| Info | #175CD3 | Informational |

These values are proposals, not certified color pairs. Compute contrast for every foreground/background combination, state, border, focus and chart use. Do not ship untested combinations.

### Service category accents (small accent only)
01 Domains #2563EB; 02 Hosting #0EA5E9; 03 Cloud #3478F6; 04 Containers #6366F1; 05 Networking #0D9488; 06 Database #14B8A6; 07 Storage/DR #64748B; 08 Email #0891B2; 09 Communications #0284C7; 10 Payments #0F9F83; 11 Developer/API #7158E8; 12 DevOps #4F46E5; 13 Cybersecurity #D97706; 14 Observability #475569; 15 AI/ML #8957D5; 16 Media #D9468F; 17 Data #0D9488; 18 Business Apps #3B69C9; 19 IT Services #0F766E; 20 IoT #CA8A04; 21 Digital Trust #7C3AED; 22 Licensing #64748B. Use category accents only for small markers/icons/chart series. Status colors remain globally semantic. Never convey status/category by color alone.

### Themes
Support Light, Dark and System. Define semantic token sets per theme; do not mechanically invert. Test charts, code, syntax highlighting, maps, provider widgets, focus, borders and status. Respect forced-colors and reduced-motion settings.

## 5. Typography system
Do not choose fonts by popularity alone. Test distinctiveness, readability, Swahili and Latin Extended glyphs, punctuation, numerals, TZS formatting, code symbols, responsive metrics, accessibility, performance and license.

**Candidates for specimen evaluation (not final selection):**
- Headings/display: Manrope variable.
- Body/UI: Source Sans 3.
- Code/technical data: IBM Plex Mono.
- Editorial display alternative: Geist Serif, sparingly.
- Developer UI alternative: Geist Sans + Geist Mono.
Select only after side-by-side specimen tests, licensing review and payload measurement. Record foundry/license, source, static vs variable, weights, subsets, fallbacks, file format, preload and font-display policy.

**Initial type scale:** display 48–64px; H1 36–44; H2 28–32; H3 22–24; H4 18–20; body 16px with 1.55–1.65 line-height; large body 18px/1.6; UI 14px; supplementary metadata 12–13px only where non-critical; code 13–14px. Use fluid scaling and preserve zoom to 200%.

**Specimen strings:** “Huduma za TEKORA”; “Mabadiliko ya usajili”; “Namba ya malipo”; “Shughuli zilizokamilika”; “TZS 1,250,000.50”; “M-Pesa / Airtel Money”; “DNSSEC, IPv6, OAuth 2.0, webhook_id”; “Müller, José, Łukasz”; “@#$%&/()[]{}<>”. Verify glyphs, fallback, clipping and alignment.

## 6. Layout and component rules
4px spacing base; common scale 4/8/12/16/20/24/32/40/48/64/80. Reading width ~65–75ch; narrower forms/detail pages; dashboards use responsive grids with minimum widths. Common controls use restrained 8–12px radii; elevation sparingly; borders/surface contrast over heavy shadows.

Shared components: buttons, links, inputs, select/combobox, date/time, tabs, breadcrumbs, side nav, command search, tables/filters/pagination, status badges, alerts/banners, dialogs/drawers, tooltip/popover, charts, code editor/copy, timeline/stepper, empty/loading/error states. Each defines relevant default, hover, focus-visible, active, disabled, loading, invalid, success and destructive states.

Tables require sorting/filtering, useful column controls, pagination, mobile alternative, clear bulk-action confirmation and all empty/error/loading states. Forms require visible labels, helper text, validation summary, inline errors, value preservation on recoverable failure and duplicate-submit protection.

## 7. Interaction and workflow
Destructive/financial actions explain scope, impact and reversibility; require confirmation or step-up where appropriate. Optimistic UI only when rollback/reconciliation is safe. Long provisioning shows state, progress, last update, retryability and support path. Never show success before authoritative confirmation. Label estimate vs actual, pending vs completed, simulated vs live, provider-observed vs TEKORA-observed. Errors state what happened, whether retry is safe and provide a correlation ID without secrets. Empty states give the next safe action. Preserve form/context on refresh/back and recover interrupted workflows.

## 8. Accessibility and responsive acceptance
Target WCAG 2.2 AA. Minimum contrast: normal text 4.5:1; large text 3:1; relevant UI component boundaries/states and graphical objects 3:1. Do not use color alone. Keyboard-only operation, logical focus, visible focus, semantic landmarks/headings, accessible names, screen-reader async announcements, text resize to 200%, responsive reflow, reduced motion, no flashing, captions/transcripts where relevant and accessible chart summaries/data tables. Use 44×44 CSS px as a TEKORA touch-target usability target where practical. Test narrow mobile, tablet, desktop and zoom. Automated scanners do not prove conformance; combine automation, manual review and assistive technology.

## 9. Performance
Prefer licensed, self-hosted, subsetted WOFF2 fonts; avoid unnecessary families/weights; preload only critical font files; use appropriate font-display. Measure LCP, CLS, INP, route transitions, dashboard tables/charts and mobile network behavior. Lazy-load advanced editors/charts; paginate/filter large inventories server-side; avoid motion that slows task completion.

## 10. Design governance gates
Before approval: benchmark evidence; IA and role journeys; computed contrast matrix; font specimen/language/license/performance test; light/dark/system prototypes; mobile/tablet/desktop flows; keyboard/screen-reader review; component state documentation; usability tests with representative users; handoff with responsive/interaction/error/loading/empty/analytics/acceptance behavior. Before module release: visual regression, responsive matrix, keyboard, contrast, screen-reader spot check, performance budget and token compliance.

## 11. Open decisions
Final palette after contrast calculation and prototype review; final font system after specimen/license/performance validation; density options for developer/ops tables; default theme and preference storage; breakpoints/container tokens; localization ownership; formal accessibility audit scope. Current status remains PROPOSED/PARTIAL.
