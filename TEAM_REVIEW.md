# MR91 Journal — 8-role product review

This is a structured engineering review performed against the project source, not a claim that eight human contractors independently tested the app.

## 1. Senior Android engineer
- Kept the app native Java and offline-first; no new runtime dependency was introduced.
- Raised the database schema to v3 for daily reviews.
- Added a v1 legacy-date migration guard and v2→v3 daily-review migration.
- Kept minSdk 23 and the existing Android Gradle toolchain.

## 2. Product designer
- Reworked the UI palette toward MR91 deep black/navy, electric blue and restrained green/red status colors.
- Added surface contrast, subtle borders, softer corners, stronger type hierarchy and larger touch targets.
- Reserved the strongest blue action for creating a trade; secondary toolkit actions use quieter surfaces.
- Exact pixel matching to the MR91 website is not certified because the live site could not be inspected in this environment.

## 3. UX / behavioral design
- Put the primary action near the top of the dashboard.
- Grouped supporting trader tools together instead of mixing them into trade entry.
- Added a daily pre-trade checklist with visible 0/5 progress and per-day local persistence.
- Added a daily review prompt focused on strengths, repeated mistakes and the next improvement.

## 4. Creative product role
- Added three offline tools without subscriptions or external APIs: risk calculator, daily discipline checklist and daily review.
- Added optional reward-to-risk ratio output when a take-profit value is entered.
- Included daily reviews in full ZIP backups and full JSON exports.

## 5. Professional trader review
- Risk amount is calculated as balance × risk percentage.
- The app clearly labels its volume result as a simplified linear estimate, not a broker lot-size conversion.
- The tool does not infer pip value, contract size, leverage, spread, swap or account-currency conversion.
- Win rate now uses only closed trades with an entered result, rather than treating unscored closed trades as losses.
- Trade result entry is labeled gross-before-fees because fees are subtracted in net P/L calculations.

## 6. Adversarial / red-team review
Findings addressed in source:
- Reject NaN/infinite and invalid numeric inputs.
- Restrict attachment paths to the private `files/trades` tree; reject traversal and absolute paths.
- Limit imported raster images to 25 MB and decode with bounds-first sampling.
- Limit ZIP compressed size to 350 MB, expanded size to 300 MB and entry count to 10,000.
- Reject duplicate ZIP paths and path traversal.
- Validate SQLite integrity, required tables/columns and attachment paths before restore.
- Reject unsupported SQLite triggers, views and extra tables in imported backups.
- Stage database and image replacement with rollback attempts.
- Escape JSON control characters and neutralize common CSV formula-injection prefixes in text fields.

## 7. QA / bug-fixing role
- Fixed the legacy migration's unconditional `created_at` assumption by checking the column before copying dates.
- Added guards around malformed numeric inputs and invalid image paths.
- Added source-level delimiter checks, XML parsing, workflow YAML parsing and SQLite migration simulations.
- Real Android runtime tests and malicious-archive tests remain pending; static checks are not presented as runtime proof.

## 8. Release manager
- Bumped app version to `1.1.0-beta` / versionCode 4 and database schema to v3.
- Updated release notes, QA matrix, build status and GitHub Actions workflow.
- Rebuilt the GitHub-ready source ZIP and checked archive integrity.
- APK build, device installation, upgrade and restore tests must pass in GitHub Actions / on a physical device before calling this release-ready.
