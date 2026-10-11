# GSA/datagov-11ty context
> refreshed 2026-10-11 | upstream default: main @ 1af6f1731d3acc9ccb46f74c864b1b98d8759110

## Identity & policies
- upstream: GSA/datagov-11ty, default branch `main`, primary language HTML (11ty + USWDS), English-first (yes — README/CONTRIBUTING/docs all English)
- CLA/DCO: none (CONTRIBUTING has no CLA bot; CC0 public-domain dedication only; no contributor signup)
- AI-assisted PR policy: unstated (no AI-disclosure requirement in repo or org; `GSA/.github` 404 — no org default)
- signed commits required: no
- PR template: `.github/pull_request_template.md` (fill verbatim — pr-description skill)
- external tracker: github

## Conventions (verified from merged PRs)
- branch naming: `<issue#>-<kebab>` (e.g. `6117-user-guide-changes-for-access-level`), `patch/<kebab>`, `fix/...`, `dependabot/...` (from merged headRefNames)
- commit style: plain imperative subject; occasionally `NNNN: subject`
- test command: `npm run test` (EMPTY — no local test script); build: `npm run build`; no lint script wired
- CI: `build.yml` (reusable workflow from gsa/data.gov, push only), `content_scan.yml` on pull_request (pa11y-ci then Cypress via start-server-and-test), Snyk weekly
- how outside PRs merge: dependabot + occasional small content branches (e.g. #647 `marcos-nieto-usds` 2026-10-05, 2 files)

## Maintainer picture
- GSA Data.gov team (marcos-nieto-usds, jaredb96, jbrown-xentity, FuhuXia); low-volume repo (21 stars); recent merges 2026-10-05
- areas actively worked: user-guide/content updates, metrics pages, pie-chart fix — avoid overlapping in-flight work

## Issue-area health
- 36 open issues, mostly non-technical facility-testing items (#600–626 by BenSaxton) with no maintainer engagement; #423 is the automated weekly Link Checker Report (lychee QA), not maintainer-accepted work
- no maintainer-engaged actionable issue survives config.selection.prefer_documented_approved_issues -> self-found gaps only
- link rot: `pages/posts/*` historical links carry ~190 real 404s (out of scope for a small PR); current content has a handful of genuine dead links (see ledger/mined gaps)

## Fork PR inventory (dedupe)
- fork PR #1 `fix/typo-cleanup` (OPEN, 2026-09-03): `_data/climate-portals.json`, `_data/climate-tools.json`, `pages/topics/maritime.html`, `pages/user-guide.md` — do NOT duplicate these files

## Gap ledger (dedupe — READ FIRST, never re-pick)
- `2026-09-03` self-found typo pass (12 typos, 4 files) — outcome: pr-opened — lesson: plain US misspellings in `_data/climate-*.json` + `pages/`; safe, glance-reviewable
- `2026-10-11` self-found dead-link pass (`_includes/identifier.html`, `README.md`, `pages/old-user-guide.md`) — outcome: pr-opened — lesson: 3 verified live 404 -> 200 fixes in current content (re-curl-verified 2026-10-11); `catalog.data.gov/api/3/` inline-code base URL is ALSO dead but has no 1:1 verified replacement (successor is `https://api.gsa.gov/technology/datagov/v4/`, a different API shape) so it stays out of scope

## Mined gaps (discovered, not yet attempted)
- `2026-09-03` typo cleanup in `_data/climate-portals.json`, `_data/climate-tools.json`, `pages/user-guide.md`, `pages/topics/maritime.html` — status: attempted
- `2026-10-11` `pages/metrics/metrics_per-org.html` links `https://harvest.data.gov/organization/{{org.name}}`; the rendered org name (not slug) 404s while slug pages (e.g. `/organization/gsa`) are live — status: proposed (needs care: template artifact, verify before touching)
- `2026-10-11` `pages/old-user-guide.md` documents the CKAN API base `https://catalog.data.gov/api/3/` which 404s — status: proposed (no 1:1 replacement; successor API is `api.gsa.gov/technology/datagov/v4/`, not a trivial link swap)
- `2026-10-11` `pages/privacy-policy.md` `http://www.ftc.gov/ogc/coppa1.htm` 404 — status: dropped (ftc.gov bot-blocks; link_check false-positive class)
- `2026-10-11` `pages/posts/*` historical dead links (~190) — status: dropped (out of scope, huge diff, historical record)
