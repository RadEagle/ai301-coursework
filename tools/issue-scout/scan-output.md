The scan is done: all 5 graded candidates passed every required check. Two of them already have someone saying they'll work on it in the comments, and your rubric doesn't catch that (details below). I added these problems to `scan-notes.md`.

**How the candidates were picked:** your one query (chemistry OR quantum, "good first issue") returned 100 results with no duplicates. Your filters (no assignee, updated in the last 30 days) cut that to 12, and I graded the top 5 by fewest comments. Search order broke ties, because the strategy doesn't name a tie-break. All 5 came from that same query.

### Accepted, best fit first
Your fit profile doesn't separate these, since all are Python. I ranked them by how many preferred checks passed, then by how likely someone else is already working on it.

1. **[Qiskit/qiskit-ibm-runtime#2714](https://github.com/Qiskit/qiskit-ibm-runtime/issues/2714)**: add a public `calibration_id` to jobs.
   - Picked because: 1 comment, updated 2026-09-25.
   - Strengths: a maintainer labeled it on 2026-09-25 and explained the approach, the acceptance criteria are clear, there were commits today, and the last release was 2026-09-24.
   - Look first at #3386: an earlier pull request for this was closed without merging on 2026-10-06. Find out why before you start.
2. **[SerenaSolutions/zephirum#5](https://github.com/SerenaSolutions/zephirum/issues/5)**: write the formal spec for `qif`, docs only.
   - Picked because: 0 comments, updated 2026-10-14.
   - Strengths: very active repo, release on 2026-10-13, short issue.
   - Warning: the repo has 1 star, its commits are written by "Superagent (house)", and it was just relicensed under BSL "per founder order". It looks agent-run, with nobody else contributing. Your rubric has no check for this.
3. **[Quantinuum/pytket-qiskit#394](https://github.com/Quantinuum/pytket-qiskit/issues/394)**: convert Qiskit's uniformly controlled gates to and from pytket.
   - Picked because: 1 comment, updated 2026-09-25.
   - Strengths: release today, short issue.
   - Already claimed: on 2026-09-25 a commenter said they have a working implementation and asked to open a pull request. Also, the person who opened the issue wasn't sure the feature is worth adding.
4. **[unitaryfoundation/mitiq#1796](https://github.com/unitaryfoundation/mitiq/issues/1796)**: a tutorial reproducing the error-mitigation results from a research paper.
   - Picked because: 1 comment, updated 2026-09-24.
   - Strengths: release 2026-09-04. The repo allows AI-assisted code but requires you to disclose it.
   - Already claimed: on 2026-09-24 someone commented "I'd like to work on this". Maintainers replied within 7 days on only 1 of the 6 issues I sampled.
5. **[sineframe/keyless-mcp#6](https://github.com/sineframe/keyless-mcp/issues/6)**: a PubChem adapter for an MCP tool server.
   - Picked because: 0 comments, updated 2026-10-11.
   - Strengths: a very detailed checklist, and the issue asks people to claim it with a comment.
   - Downsides: 2 stars, no releases, and a 2,812-character issue, so it fails the "small" check.

### Rejected
None of the 5.

### Problems logged in `scan-notes.md`
- **Query doesn't match your profile:** your profile never mentions chemistry or quantum, and it doesn't search Go, Rust, Ruby or C++, the languages you said you want to learn.
- **Ranking rule is ambiguous:** "prefer fewer comments or more" can be read either way. I used fewest comments first.
- **Results may be cut off:** the query hit gh's 100-result maximum, so some matches may have been dropped.
- **"Unclaimed" misses claim comments:** the check only looks at the assignee field, which is why #3 and #4 passed despite the comments above.
- **Repos with no outside issues:** the replies-are-timely check has nothing to sample, so it grades as unclear.

If you take #1, post a claim comment on the issue right away, as `scope.md` says.

```json
[
  {"item": "https://github.com/Qiskit/qiskit-ibm-runtime/issues/2714", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15 (Fix FoldRzz pass to respect target #3489)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "fail", "evidence": "2 of 6 sampled issues got a maintainer reply within 7 days"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "0.50.0 published 2026-09-24 (21 days)"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "239 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Single feature: 'a method or attribute of the job object to fetch the calibration id'"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Feature request with acceptance criteria, no sub-item list"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "One closed unmerged PR (#3386), threshold is two or more"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 566 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add a way to get the calibration_id of a job'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "Only cross-referenced PR #3386 is closed"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI ban; repo ships AGENTS.md"}
  ], "verdict": "accept"},
  {"item": "https://github.com/SerenaSolutions/zephirum/issues/5", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.2.0 published 2026-10-13"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "1 star"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One deliverable: 'Draft the section in the style of docs/CHARTER.md'"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single spec-writing task, no sub-items"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 296 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Write the formal spec section for qif...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs, no comments"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md (765 bytes) says nothing about AI"}
  ], "verdict": "accept"},
  {"item": "https://github.com/Quantinuum/pytket-qiskit/issues/394", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15 (release 0 79 0 #558)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "fail", "evidence": "1 of 6 sampled issues got a maintainer reply within 7 days"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "0.79.0 published 2026-10-15"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "22 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One converter feature: UCGate to MultiplexorBox"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Feature request, no sub-item list"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 598 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add handling of uniformly controlled gates...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] (thread has a 2026-09-25 claim comment, which the rubric does not check)"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs; commenter offers a PR but none is open"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file found"}
  ], "verdict": "accept"},
  {"item": "https://github.com/unitaryfoundation/mitiq/issues/1796", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-09-20 (25 days)"},
    {"name": "Repo is very active", "grade": "fail", "evidence": "Last main commit 2026-09-20, 25 days ago"},
    {"name": "Issue replies are timely", "grade": "fail", "evidence": "1 of 6 sampled issues got a maintainer reply within 7 days"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.1.0 published 2026-09-04 (41 days)"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "445 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One tutorial reproducing paper figures 3-4, E.1"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single tutorial request"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "Only cross-reference is issue #1773, not a PR"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 228 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Tutorial : Use ZNE, CDR, vnCDR...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] (2026-09-24 'I'd like to work on this' comment, which the rubric does not check)"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'Contributors can use any tools... including AI tools' (disclosure required)"}
  ], "verdict": "accept"},
  {"item": "https://github.com/sineframe/keyless-mcp/issues/6", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-11 (Merge pull request #55)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-11, 4 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "fail", "evidence": "releases/latest returns 404: no releases"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "2 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One adapter with two named tools and an acceptance checklist"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Checklist is acceptance criteria for one adapter, not sub-issues"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 2812 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add a PubChem adapter...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI restriction"}
  ], "verdict": "accept"}
]
```

----------------

I re-ran the scan with your updated strategy. Of the top 5, 3 were accepted and 2 rejected. The best accepted candidates are the same two quiet repos from the first scan (zephirum and keyless-mcp), so your new queries didn't turn up anything stronger.

**How the candidates were picked:**
- **Results:** your 10 queries returned 262 unique issues; 29 were left after your drop filters.
- **Queries with nothing or capped:** sql, plpgsql, tsx and matlab returned no results. Python and C++ each hit gh's 100-result maximum, so those searches may be cut off.
- **Ranking:** I sorted by fewest comments. Your "easier to fix" and "more stars" filters need information that search results don't include, so I skipped them.
- **Ties:** that left 10 issues tied at 0 comments, so the top 5 came down to the order I read the results in, not to anything in your strategy.

### Accepted, best fit first
I ranked them by how many preferred checks passed.

1. **[SerenaSolutions/zephirum#5](https://github.com/SerenaSolutions/zephirum/issues/5)**: write the formal spec for quantum control flow, docs only.
   - Found by: the python query, 0 comments.
   - Strengths: commits today, release on 2026-10-13, short issue (296 characters).
   - Same warning as last scan: 1 star, and the commits come from "Superagent (house)". The repo looks agent-run, with nobody else contributing.
2. **[sineframe/keyless-mcp#6](https://github.com/sineframe/keyless-mcp/issues/6)**: a PubChem chemistry adapter.
   - Found by: the python query, 0 comments.
   - Strengths: last commit 4 days ago, a detailed acceptance checklist, and still nobody has commented to claim it.
   - Downsides: 2 stars, no releases, and a long issue.
3. **[evmckinney9/gulps#25](https://github.com/evmckinney9/gulps/issues/25)**: let the calibration functions take a measured trajectory.
   - Found by: the rust query, 0 comments.
   - Strengths: release on 2026-10-05.
   - Warning: it passes the rubric but is research-level. It means redesigning an API, reproducing results from a MICRO 2022 paper and adding caching. Your "not difficult" check only counts abandoned pull requests, so it can't catch this. The proposed code is also in Python, even though the repo is listed as Rust.

### Rejected
- **[akshaysoftware/bloch-legacy#202](https://github.com/akshaysoftware/bloch-legacy/issues/202)** (c++ query): the repo is archived. Its last commit was 2026-08-29, so it also fails "Repo is active".
- **[MGYamada/Qleisli#360](https://github.com/MGYamada/Qleisli/issues/360)** (rust query): fails "not an umbrella". It asks for one consistent set of rules across every target profile, which touches much of the codebase.

### Problems logged in `scan-notes.md`
- **Unusable filters:** the two skipped filters belong in the rubric, which already has "Issue is small", "Issue is not difficult" and "Repo is popular". For stars, you could also put `stars:>N` directly in the queries.
- **No tie-break:** add one that uses fields search does return, such as most recently updated.
- **Empty queries:** the sql, plpgsql, tsx and matlab queries return nothing because GitHub usually labels PostgreSQL and React repos as Python or TypeScript. Mathematics is in your profile but isn't searched.
- **Archived repos:** adding `archived:false` to the queries would drop them before grading.

The stronger repos from the last scan (qiskit-ibm-runtime#2714 and the others) appear at ranks 11–13 in this one. If you want them graded, either add a tie-break or raise N.

```json
[
  {"item": "https://github.com/SerenaSolutions/zephirum/issues/5", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.2.0 published 2026-10-13"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "1 star"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One deliverable: 'Draft the section in the style of docs/CHARTER.md'"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single spec-writing task, no sub-items"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 296 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Write the formal spec section for qif...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md (765 bytes) says nothing about AI"}
  ], "verdict": "accept"},
  {"item": "https://github.com/sineframe/keyless-mcp/issues/6", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-11 (Merge pull request #55)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-11, 4 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "fail", "evidence": "releases/latest returns 404: no releases"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "2 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One adapter with two named tools and an acceptance checklist"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Checklist is acceptance criteria for one adapter, not sub-issues"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 2812 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add a PubChem adapter...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI restriction"}
  ], "verdict": "accept"},
  {"item": "https://github.com/evmckinney9/gulps/issues/25", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-05 (chore: release 0.4.1)"},
    {"name": "Repo is very active", "grade": "fail", "evidence": "Last main commit 2026-10-05T13:56Z, just over 10 days ago"},
    {"name": "Issue replies are timely", "grade": "fail", "evidence": "1 of 7 sampled issues got a maintainer reply within 7 days"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.4.1 published 2026-10-05"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "6 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One feature with clear specs: proposed Candidates signature for strength_sweep/calibrate plus a power_candidates helper"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature request, no sub-issue list"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No PRs; only cross-reference is issue #2"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 2677 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '[Feature Request]: analysis over manual trajectory sequence'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": ".github/CONTRIBUTING.md has no AI restriction; repo ships AGENTS.md"}
  ], "verdict": "accept"},
  {"item": "https://github.com/akshaysoftware/bloch-legacy/issues/202", "checks": [
    {"name": "Repo is active", "grade": "fail", "evidence": "Last develop commit 2026-08-29 (docs: mark repository as legacy), 47 days ago"},
    {"name": "Repo is very active", "grade": "fail", "evidence": "Last commit 47 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No recent issues to sample"},
    {"name": "Repo has a recent release", "grade": "fail", "evidence": "v1.0.4 published 2026-02-21"},
    {"name": "Repo is not archived", "grade": "fail", "evidence": "archived=true"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "17 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One feature: defer statevector allocation until first operation"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature with acceptance criteria"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 520 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Lazy amplitude allocation'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md (1339 bytes) has no AI restriction"}
  ], "verdict": "reject"},
  {"item": "https://github.com/MGYamada/Qleisli/issues/360", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15 (Merge pull request #407)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "Sampled issues all opened today by the owner; no reply data"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.2.9 published 2026-10-03"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "0 stars"},
    {"name": "Issue is not an umbrella", "grade": "fail", "evidence": "'Maintain one explicit capability matrix for source forms and target profiles' and align semantics across all paths: cross-cutting, not one piece of work"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Framed as one review finding, not a tracker"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No PRs; only cross-reference is issue #382"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 1806 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'bug: make lowering-profile capability... consistent'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'Human-written and AI-assisted contributions follow the same review and verification requirements'"}
  ], "verdict": "reject"}
]
```

----------------

I re-ran the scan, and the result is identical to the last one. Your new thresholds ("2 files or less", "1000+ stars") didn't change the ranking.

Search found the same 262 issues, 29 survived your filters, and the top 5 came out in the same order. I re-checked those 5 issues and nothing on them has changed: no new comments, assignees or pull requests, and no change in archived status. Your rubric hasn't changed either, so I kept the grades from the last scan instead of re-grading.

**Why your edit had no effect:** the scout ranks using only what search results return. The file count is only in the issue body and the star count is on the repo, and search results include neither. Adding thresholds doesn't change that, so I still had to skip both filters. Ranking came down to fewest comments, and 10 issues tie at zero, so your filters never decided the top 5.

**Three changes that would move the results**, in order of impact:
1. **Add a tie-break** that uses fields search does return, e.g. "then most recently updated first". The 10-way tie at zero comments is what's picking your top 5 right now.
2. **Stars:** put `stars:>=1000` in each query instead of in the ranking filters. GitHub's issue search supports repo-level qualifiers like this, though I haven't confirmed `gh search issues` passes it through. It would remove repos with only a handful of stars, like zephirum (1), keyless-mcp (2) and Qleisli (0). Otherwise, drop the filter; your rubric already has "Repo is popular".
3. **File count:** move "2 or fewer files" into `rubric.md` as a preferred check, since only the issue body can show it.

I added these to `scan-notes.md`.

### Accepted, best fit first (same as last scan)
1. **[SerenaSolutions/zephirum#5](https://github.com/SerenaSolutions/zephirum/issues/5)**: docs-only spec work. It looks good on paper, but the repo has 1 star and looks agent-run.
2. **[sineframe/keyless-mcp#6](https://github.com/sineframe/keyless-mcp/issues/6)**: PubChem chemistry adapter. Clear checklist and still unclaimed, but the issue is long and the repo has no releases.
3. **[evmckinney9/gulps#25](https://github.com/evmckinney9/gulps/issues/25)**: passes the rubric, but the work is research-level.

### Rejected
- **[akshaysoftware/bloch-legacy#202](https://github.com/akshaysoftware/bloch-legacy/issues/202)**: the repo is archived.
- **[MGYamada/Qleisli#360](https://github.com/MGYamada/Qleisli/issues/360)**: fails "not an umbrella".

```json
[
  {"item": "https://github.com/SerenaSolutions/zephirum/issues/5", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.2.0 published 2026-10-13"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "1 star"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One deliverable: 'Draft the section in the style of docs/CHARTER.md'"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single spec-writing task, no sub-items"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 296 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Write the formal spec section for qif...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments (re-checked)"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md (765 bytes) says nothing about AI"}
  ], "verdict": "accept"},
  {"item": "https://github.com/sineframe/keyless-mcp/issues/6", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-11 (Merge pull request #55)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-11, 4 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No issues older than 7 days to sample"},
    {"name": "Repo has a recent release", "grade": "fail", "evidence": "releases/latest returns 404: no releases"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "2 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One adapter with two named tools and an acceptance checklist"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Checklist is acceptance criteria for one adapter, not sub-issues"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 2812 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add a PubChem adapter...'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments (re-checked)"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI restriction"}
  ], "verdict": "accept"},
  {"item": "https://github.com/evmckinney9/gulps/issues/25", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-05 (chore: release 0.4.1)"},
    {"name": "Repo is very active", "grade": "fail", "evidence": "Last main commit 2026-10-05T13:56Z, just over 10 days ago"},
    {"name": "Issue replies are timely", "grade": "fail", "evidence": "1 of 7 sampled issues got a maintainer reply within 7 days"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.4.1 published 2026-10-05"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "6 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One feature with clear specs: proposed Candidates signature plus power_candidates helper"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature request, no sub-issue list"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No PRs; only cross-reference is issue #2"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 2677 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '[Feature Request]: analysis over manual trajectory sequence'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [], no comments (re-checked)"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": ".github/CONTRIBUTING.md has no AI restriction; repo ships AGENTS.md"}
  ], "verdict": "accept"},
  {"item": "https://github.com/akshaysoftware/bloch-legacy/issues/202", "checks": [
    {"name": "Repo is active", "grade": "fail", "evidence": "Last develop commit 2026-08-29, 47 days ago"},
    {"name": "Repo is very active", "grade": "fail", "evidence": "Last commit 47 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "No recent issues to sample"},
    {"name": "Repo has a recent release", "grade": "fail", "evidence": "v1.0.4 published 2026-02-21"},
    {"name": "Repo is not archived", "grade": "fail", "evidence": "archived=true (re-checked)"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "17 stars"},
    {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "One feature: defer statevector allocation until first operation"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature with acceptance criteria"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "Issue is small", "grade": "pass", "evidence": "Body is 520 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Lazy amplitude allocation'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md (1339 bytes) has no AI restriction"}
  ], "verdict": "reject"},
  {"item": "https://github.com/MGYamada/Qleisli/issues/360", "checks": [
    {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-15 (Merge pull request #407)"},
    {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-15, 0 days ago"},
    {"name": "Issue replies are timely", "grade": "unclear", "evidence": "Sampled issues all opened today by the owner; no reply data"},
    {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.2.9 published 2026-10-03"},
    {"name": "Repo is not archived", "grade": "pass", "evidence": "archived=false"},
    {"name": "Repo is popular", "grade": "fail", "evidence": "0 stars"},
    {"name": "Issue is not an umbrella", "grade": "fail", "evidence": "'Maintain one explicit capability matrix for source forms and target profiles': cross-cutting, not one piece of work"},
    {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Framed as one review finding, not a tracker"},
    {"name": "Issue is not difficult", "grade": "pass", "evidence": "No PRs; only cross-reference is issue #382"},
    {"name": "Issue is small", "grade": "fail", "evidence": "Body is 1806 characters"},
    {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'bug: make lowering-profile capability... consistent'"},
    {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
    {"name": "No open pull requests", "grade": "pass", "evidence": "No linked PRs"},
    {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'Human-written and AI-assisted contributions follow the same review and verification requirements'"}
  ], "verdict": "reject"}
]
```

----------------

## Grading results (direct mode, measured against today, 2026-10-15)

### Accepted

**1. apache/mahout#1510: `create_empty_circuit()` without `num_qubits` behaves differently per backend** (source: direct)
- Fit: this is the best match for your profile. The work is in Python, which you already know, inside Qumat, a quantum-computing library, which matches your quantum physics interest. The repo's main language is Rust, which you want to learn.
- Required checks all pass. The last commit was today and the repo isn't archived. The issue is one bounded fix in `qumat/qumat.py` plus tests. It has no assignee, no linked or mentioned PRs, and a title that states a bug. CONTRIBUTING.md says nothing about AI use.
- Preferred checks:
  - Very active: pass (last commit today).
  - Timely replies: unclear. In the sample, maintainers answered only one issue (#1477, in about 2h). The hackathon batch, including this issue, has no maintainer replies yet.
  - Recent release: fail (latest is qumat-0.6.0 from 2026-05-31, 137 days ago).
  - Popular: pass (2,310 stars).
  - Small: fail (1,123 characters).
- ⚠️ **Someone may already be on this.** User `gautham0104-neitizen` commented on 2026-10-14 asking to be assigned, and the issue says "Comment here to claim it." The rubric's "Issue is unclaimed" check only looks at the assignee field, so it passes. Your `scope.md` says claim comments count, though. Before you take this, check whether a maintainer replies to that request. Consider adding claim comments to the check in `rubric.md`, and log this in `scan-notes.md`.

### Rejected

**2. maplibre/maplibre-gl-js#4234: `feature-state` with `fill-outline-color` breaks rendering** (source: direct)
- Failed "No open pull requests": PR #7420 is open and linked. In July 2026 a maintainer called it "what is aimed at solving this" and also said "Feel free to take a stab at it."
- Failed "Issue is not difficult": two linked PRs, #4241 and #4351, were closed without merging, and none has merged.
- Otherwise it's a healthy repo: 11.9k stars, a release 4 days ago, and replies within hours.

**3. onflow/cadence#1151: Request for additional math functions** (source: direct)
- Failed "Repo is active": the last commit to `master` was 2026-09-02, 43 days ago, which is past the 30-day limit.
- Failed "Issue is not an umbrella": it asks for 5 functions across "all applicable numeric types", and maintainers are still discussing new fixed-point types.
- Failed "No open pull requests": PR #3055 ("Introduce `Sqrt` on `NumberType`") is still open.

```json
[
  {
    "item": "https://github.com/apache/mahout/issues/1510",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Latest main commit 2026-10-15T18:08:29Z (#1531), 0 days ago"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Latest main commit today, within 10 days"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "Recent sample: only #1477 got a MEMBER reply (~2h); hackathon issues #1506-#1512 have no maintainer reply yet"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "Latest release mahout-qumat-0.6.0 on 2026-05-31, 137 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "archived: false"},
      {"name": "Repo is popular", "grade": "pass", "evidence": "2310 stars"},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Single bug: consistent create_empty_circuit() behavior across backends, 'Where: qumat/qumat.py and the three backends', add tests"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "No tracking/megaissue language; one hackathon task"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs in timeline; PR search for 1510/create_empty_circuit returns none relevant"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 1123 characters (>1000)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '[Bug] create_empty_circuit() without num_qubits behaves differently per backend'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] (note: claim-request comment by gautham0104-neitizen on 2026-10-14)"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No cross-referenced or open PRs found"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI policy statement (silence passes)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/maplibre/maplibre-gl-js/issues/4234",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Latest main commit 2026-10-15T20:00:40Z (#8780)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Five commits merged to main today"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "7 of 8 recent issues got a COLLABORATOR reply within ~1 day"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v6.14.0 on 2026-10-11, 4 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "archived: false"},
      {"name": "Repo is popular", "grade": "pass", "evidence": "11870 stars"},
      {"name": "Issue is not an umbrella", "grade": "pass", "evidence": "Single bug: fill-outline-color with feature-state throws in packColor"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Plain bug report, no tracking language"},
      {"name": "Issue is not difficult", "grade": "fail", "evidence": "Linked PRs #4241 and #4351 both closed unmerged; zero merged"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 616 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '`feature-state` with `fill-outline-color` breaks rendering'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: []"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #7420 cross-referenced and open; maintainer: 'I think the following PR is what is aimed at solving this'"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'MapLibre welcomes contributors who use AI coding tools' (disclosure required)"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/onflow/cadence/issues/1151",
    "checks": [
      {"name": "Repo is active", "grade": "fail", "evidence": "Latest master commit 2026-09-02T19:09:54Z, 43 days ago (>30)"},
      {"name": "Repo is very active", "grade": "fail", "evidence": "Latest master commit 43 days ago"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "Most recent sampled issues (#4475, #4470, #4468, #4417) have no reply; #4484 waited ~73 days"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.10.6 on 2026-08-18, 58 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "archived: false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "548 stars"},
      {"name": "Issue is not an umbrella", "grade": "fail", "evidence": "Asks for ln, log, pow, sqrt, exp 'for all applicable numeric types'; maintainers discussing new fixed-point types"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Framed as a feature request, not a tracking issue"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Linked PRs: #3055 open, #4473 merged; not 2+ closed with zero merged"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 1066 characters (>1000)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Request for additional math functions...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "assignees: [] (turbolent was assigned in 2021 but is no longer listed)"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #3055 'Introduce Sqrt on NumberType' is open"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md is silent on AI; AGENTS.md gives guidance for AI agents"}
    ],
    "verdict": "reject"
  }
]
```