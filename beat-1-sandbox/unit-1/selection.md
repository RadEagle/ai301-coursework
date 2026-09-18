# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

[The individual Path Review issue page. A link to the repository or the issue list
does not satisfy this field.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]
All three are in the scoped repo and repo-level evidence is unchanged (last `main` commit `2026-09-16`; `archived: false`; 1 star; no releases; `docs/CONTRIBUTING.md` silent on AI; still **zero pull requests repo-wide**).

**All three accept** — 14 accepted total. Preferred checks remain tied across every candidate (small ✓, very active ✓, timely ✓, popular ✗, release ✗), so ranking stays fit-driven.

Worth flagging a tension on the two new frontend issues. **#40** (3 files, frontend + backend, 5–8h, `tier-2`) and **#39** (5 files, 5–8h, `tier-3`, needs a new `progress_pct` column on `Review`) both clear *Issue is not an umbrella* by the rubric's stated condition — each is one feature with an explicit file list and specs, not codebase-wide — but they're roughly triple the work of the top of the list and neither carries a `good first issue` label. The rubric accepts them; the ranking is where that shows. If you'd rather the rubric itself screen out multi-day cross-stack work, the place to fix it is the umbrella check's pass condition (or a new required effort check), not this run.

**Combined ranking, all 14 accepted:**

| #   | Issue                                                      | Why it ranks here                                                                                                                          |
| --- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | **#61** SQLAlchemy `text()` in health probe                | FastAPI + Postgres, exact `ArgumentError` quoted, one-call fix.                                                                            |
| 2   | **#60** Faithfulness `text: None` crash                    | Tightest scope overall — one `.get()` defect, copy-paste repro, named covering test.                                                       |
| 3   | **#62** Health check `settings.redis_host`                 | Redis + FastAPI + config; slightly wider since the swallowing `except Exception` is arguably in scope.                                     |
| 4   | **#69** Output parser JSON array fallback                  | Self-contained Python fix plus an `xfail` removal; JSON-shape work transfers from your TS.                                                 |
| 5   | **#68** Keyword search `ZeroDivisionError`                 | Same shape as #69, but the edge case starts in `rank-bm25`.                                                                                |
| 6   | **#57** Tech detector counts vendored files                | Real logic, but two named failing tests make "done" unambiguous.                                                                           |
| 7   | **#36** Missing test for `POST /reviews` with no documents | *New.* One file, one test, 2–3h, `good first issue` — FastAPI route testing, and your vitest habits carry over to pytest.                  |
| 8   | **#37** API doc missing `POST /profiles` body              | Zero runtime risk, squarely FastAPI, but you author content across three files with nothing to test against.                               |
| 9   | **#12** Snapshot tests for prompt templates                | Testing work you'd enjoy, but 3–5h and you design the version-bump convention.                                                             |
| 10  | **#18** Repo analyzer never gets a file list               | New file-list fetching in `GitHubTool` *and* analyzer wiring — two components.                                                             |
| 11  | **#15** Agent session state not cleared                    | Cache/session lifecycle across three files; easy to half-fix.                                                                              |
| 12  | **#59** Faithfulness word-overlap scoring                  | One function, but the matching strategy is left to you; no `good first issue` label.                                                       |
| 13  | **#40** "Copy link" share button                           | *New.* React/TS/Tailwind is your stack, but 5–8h building a new public-link surface with tokens and 30-day expiry across frontend and API. |
| 14  | **#39** Real-time review progress indicator                | *New.* Largest: 5 files, a new DB column and migration, service wiring, polling hook, and UI — `tier-3`, 5–8h.                             |

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One probe in one file, api/routes/health.py: wrap the literal \"SELECT 1\" in sqlalchemy.text()."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report with a reproduction and the exact ArgumentError; no sub-item list."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 612 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Health check DB probe passes a raw SQL string, which fails under SQLAlchemy 2.x' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#61' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/60",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One defect in one call: chunk.get('text', '') in FaithfulnessChecker.check(), with a named covering test."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Body is a single bug report with repro; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 640 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Faithfulness checker crashes when a context chunk has `text: None`' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#60' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/62",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One probe in api/routes/health.py should read settings.redis_url instead of nonexistent redis_host/redis_port."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report with reproduction and observed log output; no sub-item list."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state; the sole 'referenced' timeline event is a commit reference, not a PR."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 672 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Health check references `settings.redis_host`, which does not exist on Settings' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "A PR search for '#62' returns total_count 0 and the repo has no pull requests at all."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Names two files (rag/generator/output_parser.py, its unit test) and one fallback path; estimated effort 2-4 hours."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single AttributeError bug report; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 541 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Output parser crashes on a top-level JSON array fallback' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#69' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/68",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Names two files (rag/retriever/keyword_search.py, its unit test) and one empty-corpus guard; estimated effort 2-4 hours."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single ZeroDivisionError bug report; the manifest id H-01 refers to an xfail marker to remove, not a tracked sub-list."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state; the sole 'referenced' timeline event is a commit reference, not a PR."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 572 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Keyword search raises `ZeroDivisionError` when the index is empty' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "A PR search for '#68' returns total_count 0 and the repo has no pull requests at all."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/57",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One exclusion rule in agent/tools/tech_detector.py, pinned by two named failing tests."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report with an executable repro; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 762 characters, the longest of the fourteen but still under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Tech detector counts vendored and build-output files, skewing language detection' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#57' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/36",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One test case in one named file, tests/unit/test_review_routes.py; estimated effort 2-3 hours."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single missing-test description; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 376 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title '`POST /reviews` endpoint has no test for when the profile has no ingested documents' is a statement of a gap."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#36' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/37",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Bounded deliverable: request-body schemas for exactly two endpoints in docs/API.md; estimated effort 2-3 hours."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "One documentation gap described in prose; no sub-item checklist or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 445 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'API reference doc is missing the `POST /profiles` request body schema' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#37' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/12",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One deliverable in one named file, tests/unit/test_prompt_templates.py, with a stated 3-5 hour estimate."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Body is a single enhancement request; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 379 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Add snapshot tests for prompt templates to catch accidental changes' is an imperative statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#12' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/18",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Two named files and one missing key ('file_structure') to populate; estimated effort 2-4 hours."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single defect description; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 515 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Repo analyzer never receives a file list, so `has_tests` and `has_ci` are always `False`' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' and 'renamed' events; a PR search for '#18' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/15",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One behavior change stated concretely ('Empty that cache and delete the profile's saved session state when run starts'), across three named files."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single defect description with a prescribed fix; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 478 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Agent session state is not cleared between reviews for the same user' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#15' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/59",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Scoped to one function, _is_supported() in faithfulness_checker.py, with a named failing test."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report with reproduction command; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 525 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Faithfulness checker scores claims unsupported when the context uses different words' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' and 'renamed' events; a PR search for '#59' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/40",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One feature with explicit specs (no login, 30-day expiry) and three named files; larger at 5-8 hours but not codebase-wide."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single enhancement request; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 373 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Add a \"Copy link\" button to share a public review summary' is an imperative statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#40' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/39",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-16, 2 days before today (2026-09-18), well inside 30 days."},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-09-16 is 2 days old, inside the 10-day bar."},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Both maintainer first responses in the repo (#52, #43) came 6 days after opening, under 7 days."},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "GitHub releases and tags endpoints both return empty: the repo has never published a release."},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "Repo API reports archived: false, disabled: false."},
      {"name": "Repo is popular", "grade": "fail", "evidence": "stargazers_count: 1, far below the 1000-star bar."},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One outcome ('Show a real progress bar') with a named root cause and five named files; largest of the set at 5-8 hours but not codebase-wide."},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report; no sub-item list or tracking language."},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Repo contains zero pull requests of any state, so no closed unmerged attempts on this issue."},
      {"name": "Issue is small", "grade": "pass", "evidence": "Title plus body is 529 characters, under the 1000-character bar."},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title 'Review progress indicator doesn't update in real time during long-running reviews' is a defect statement."},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] on the issue API response."},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Timeline has only 'labeled' events; a PR search for '#39' returns total_count 0."},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no AI, LLM, or generated-code policy statement; silence passes."}
    ],
    "verdict": "accept"
  }
]
```

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
paste the output here, including the closing JSON block
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]
1. 9/18/2026 11:49AM PST - 12/20
2. 9/18/2026 1:08PM PST - 18/20

**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

In issue 20, my rubric accepts it while the gold label rejects it. My rubric accepted it because the repo is active (as in last updated the day before capture) and the issue is entirely unclaimed. CodePath course states the selected issue may be a feature request, which perfectly describes this very issue. The gold-label rejected it because it didn't have any spec, but the spec entails that there should be an easier way to easily add custom logos (like the company logo) into the canvas.

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

For the check, "repo is very active", it is similar to "repo is active", but ensures that during the CodePath class, my PR can be merged to the default branch without me having to worry about deadlines due to the maintainer taking too long to respond. There, I am given about 4-5 weeks for unit 5, but it seems like I need to make measurable progress every week. I only gave it 10 days rather than 7 days to exercise leniency among the maintainers as they also have to do a lot of work too.

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

In the check "the issue is not an umbrella", I first saw this check fail when I ran the first full run and popped up in issue 1. So I put that issue as a canary and tweaked this check so that it passes. Only when I mentioned "has clear specs" did issue 1 pass. However, that same statement caused issue 4 to fail because it did not have clear specs (as in which files) on what to update.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
3. The anticipated difficulty in claiming it.]

1. As I want to elevate my SQL skills and not have to rely on manually migrating SQL everytime, in addition to needing Python compatibility, I chose issue #61, SQLAlchemy issue to be my first issue. It seems that a health check is a relatively simple scope to work around with and I have experience building backend applications with Python, FastAPI, and PostgreSQL.

2. The verdict identified that the specs are specified, that it is short, unclaimed, and that there are no open pull requests; largely the issue-specific checks were identified correctly. Any checks that are repo-specific are trivial since the assignment limits the scope to one repo, such as repo popularity, active maintainer, etc.

3. I anticipate since it is a SQLAlchemy issue, which usually means the developer must know backend and SQL, and many people are still in school while I have professional exprience, I should have little difficulty in claiming this issue.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
