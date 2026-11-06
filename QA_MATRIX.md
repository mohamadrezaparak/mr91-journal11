# MR91 Journal — 8-role review & QA matrix

This is a review checklist representing the eight requested perspectives; it is not a claim that eight independent human agents executed tests.

| Review role | Main responsibility | Checks represented in this build |
|---|---|---|
| Senior Android engineer | Architecture, persistence, maintainability | Java native app, SQLite helper, schema v1→v2 migration, private app storage |
| UI designer | Visual hierarchy and brand consistency | Dark/blue visual baseline, compact dashboard, consistent cards and controls; exact website match remains pending source assets |
| UX psychologist | Reduce friction and improve review behavior | Quick trade entry, searchable history, decision/emotion/review fields, one-tap navigation |
| Creative product thinker | Useful differentiators without subscriptions | Screenshot journaling, strategy breakdown, custom date filtering, offline exports and restore |
| Professional trader | Trading data and metric semantics | Side, entry/exit, SL/TP, size, fees, result, setup, timeframe, emotion, status; metric caveats documented |
| Adversarial tester | Abuse cases and data safety | ZIP traversal rejection, entry-count and expanded-size caps, SQLite integrity check before restore |
| QA / bug fixer | Regression and edge cases | Upgrade path, empty fields, edit behavior, delete confirmation, offline architecture; device tests still required |
| Release manager | Reproducible handoff | Source project, build instructions, build status, QA checklist, version notes |

## Known release blockers
- Build has not been compiled in this environment (Android SDK/Gradle toolchain is not available here).
- No emulator or physical-device run has been performed.
- Exact MR91 website visual matching requires screenshots or assets from the website.
- Release signing, Play/Bazaar metadata, and production privacy review are not completed.
