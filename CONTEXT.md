# GSA/datagov-11ty context
> refreshed 2026-09-03 | upstream default: main @ dad14c4

## Identity & policies
- upstream: GSA/datagov-11ty, default branch `main`, primary language HTML (11ty + USWDS), English-first (yes — README/CONTRIBUTING/docs all English)
- CLA/DCO: none (CONTRIBUTING has no CLA bot; CC0 public-domain dedication only)
- AI-assisted PR policy: unstated (no AI-disclosure requirement found)
- signed commits required: no
- PR template: `.github/pull_request_template.md` (fill verbatim — pr-description skill)
- external tracker: github

## Conventions (verified from merged PRs)
- branch naming: `fix/...`, `patch/...`, `dependabot/...`, `snyk-...` (from merged headRefNames)
- test command: `npm run test` (content Cypress, accessibility pa11y-ci, inclusivity woke); build: `npm run build`
- CI: `build.yml` (reusable workflow from gsa/data.gov), `content_scan.yml` on PR

## Maintainer picture
- GSA Data.gov team; low-volume repo (20 stars, 28 open issues); outside PRs merged via dependabot + occasional fix branches

## Issue-area health
- content/data files (`_data/*.json`) and `pages/` docs contain plain-text typos — low-risk, meaning-preserving cleanup targets
- no contested/redesign signals relevant to typo cleanup

## Gap ledger (dedupe — READ FIRST, never re-pick)
- `2026-09-03` self-found typo pass (12 typos, 4 files) — outcome: pr-opened — lesson: plain US misspellings in `_data/climate-*.json` + `pages/`; safe, glance-reviewable

## Mined gaps (discovered, not yet attempted)
- `2026-09-03` typo cleanup in `_data/climate-portals.json`, `_data/climate-tools.json`, `pages/user-guide.md`, `pages/topics/maritime.html` — status: attempted
