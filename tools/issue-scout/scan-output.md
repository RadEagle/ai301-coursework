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

----

I graded all three issues against your rubric and **rejected all three**. Each one already has an open pull request that claims to fix it, so someone else is already working on it.

### Rejected

**1. apache/mahout#1510**: `create_empty_circuit()` without `num_qubits` behaves differently per backend (Python, quantum). Source: direct.
- **Sank it:** No open pull requests. PR #1561 by Howardisme is open, was updated today, and says "Closes #1510".
- **Required checks that passed:** Repo is active (last commit 2026-10-17), not archived, not a tracking issue, not difficult, not a usage question, no assignee, AI code allowed (CONTRIBUTING.md says nothing about AI), and scope-feasible (it names `qumat/qumat.py` and the three backends).
- **Preferred checks:**
  - Pass: very active, 2,311 stars.
  - Timely replies: pass, but only on a thin sample. The two issues old enough to judge got maintainer replies within 1 and 4 days; the other four are under 7 days old.
  - Fail: latest release was 2026-05-31, which is 144 days ago. The issue body is 1,123 characters, over your 1,000 limit.
- **Fit:** This is the best fit of the three: Python and quantum computing, which matches your profile. It lost only on the claim.

**2. maplibre/maplibre-gl-js#4234**: `feature-state` with `fill-outline-color` breaks rendering (TypeScript). Source: direct.
- **Sank it, two required failures:**
  - Not difficult: fail. PRs #4241 and #4351 are both closed and neither was merged, which is two abandoned attempts.
  - No open pull requests: fail. PR #7420 is still open, and a maintainer said on 2026-07-05 that it is the fix in progress.
- **Required checks that passed:** Active (commits today), not archived, not tracking, not a question, no assignee, scope-feasible, and AI code allowed. MapLibre welcomes AI-assisted work but requires you to disclose it and be able to explain the code.
- **Preferred checks:**
  - Pass: 11,920 stars, release v6.15.0 on 2026-10-18, issue body is 616 characters.
  - Fail: timely replies. Only 2 of the 6 latest issues have a maintainer reply.

**3. onflow/cadence#1151**: request for `ln`, `log`, `pow`, `sqrt`, `exp` (Go, math). Source: direct.
- **Sank it, two required failures:**
  - Repo is active: fail. The last commit to `master` was 2026-09-02, which is 50 days ago and over your 30-day limit.
  - No open pull requests: fail. PR #3055 ("Introduce `Sqrt` on `NumberType`") is open.
- **Required checks that passed:**
  - Not difficult: PR #4473 (`pow`) was merged, so it doesn't have two failed attempts.
  - No assignee: turbolent was unassigned back in 2021.
  - AI code allowed: CONTRIBUTING.md says nothing about AI, and the repo has an AGENTS.md.
  - Scope-feasible and not a tracking issue: graded pass, but I'm not confident (see below).
- **Preferred checks:**
  - Pass: none.
  - Fail: 547 stars, release 65 days old, slow replies (the one reply in the last 6 issues took about 2.5 months), body is 1,066 characters.

### Rubric friction worth logging in `scan-notes.md`
- **"Issue is unclaimed" only looks at assignees.** Both #4234 (zaknixon, 2026-06-30) and #1510 (gautham0104, 2026-10-14) have "I'd like to work on this" comments that the check doesn't see. Your scope.md says claims count again, so the check could include claim comments.
- **Tracking-issue checks on #1151.** It asks for five functions across all numeric types, and PR #4473 says "Work towards #1151", so in practice it works like an umbrella issue. Because the issue never calls itself a tracking issue, both checks passed. The verdict didn't depend on this.
- **Timely replies sample.** Reading the newest issues counts ones that are only hours old as "no response". The sample could skip issues younger than 7 days.

```json
[
  {
    "item": "https://github.com/apache/mahout/issues/1510",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-17 (#1533), 5 days ago"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-17, within 10 days"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Issues older than 7 days (#1512, #1511) got member replies in 1 and 4 days; 4 newer issues are under 7 days old"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "Latest release mahout-qumat-0.6.0 on 2026-05-31, 144 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "pass", "evidence": "2311 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug report about create_empty_circuit() backend inconsistency"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No closed linked PRs; only #1561 (open)"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 1123 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '[Bug] create_empty_circuit() without num_qubits behaves differently per backend'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees (comment request by gautham0104 on 2026-10-14 unanswered)"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #1561 by Howardisme is OPEN and says 'Closes #1510'"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md contains no AI policy"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One behavior to fix; 'Where: qumat/qumat.py and the three backends'"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/maplibre/maplibre-gl-js/issues/4234",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-22 (#8491), today"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "Only 2 of the 6 latest issues (#8854, #8840) have a member reply"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v6.15.0 released 2026-10-18"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "pass", "evidence": "11920 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single rendering bug report with repro steps"},
      {"name": "Issue is not difficult", "grade": "fail", "evidence": "Linked PRs #4241 and #4351 both closed unmerged; zero merged"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 616 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '`feature-state` with `fill-outline-color` breaks rendering'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #7420 'Fix fill-outline-color fallback for feature-state expressions' is OPEN"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'MapLibre welcomes contributors who use AI coding tools' (disclosure required)"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One bug: fill-outline-color with feature-state throws in packColor"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/onflow/cadence/issues/1151",
    "checks": [
      {"name": "Repo is active", "grade": "fail", "evidence": "Last master commit 2026-09-02, 50 days ago"},
      {"name": "Repo is very active", "grade": "fail", "evidence": "Last master commit 2026-09-02"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "1 of the 6 latest issues has a member reply, after ~2.5 months (#4484)"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "v1.10.6 released 2026-08-18, 65 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "547 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Framed as a feature request, not labeled or described as tracking (though PR #4473 says 'Work towards #1151')"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Linked PR #4473 merged 2026-05-19; no closed-unmerged PRs"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 1066 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Request for additional math functions...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees (turbolent unassigned 2021-09-29)"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #3055 'Introduce Sqrt on NumberType' is OPEN"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI policy; repo ships AGENTS.md"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Names concrete functions to add (ln, log, pow, sqrt, exp)"}
    ],
    "verdict": "reject"
  }
]
```

----

I graded all three issues against your rubric. Two are accepted and one is rejected, but the MFC issue looks like it's already been fixed on `master`, so read the note on it before you claim it.

### Accepted, in fit order

**1. melink14/rikaikun#198**: Doesn't include hiragana after kanji when hovering tofugu ruby spans. Source: direct.
- **Fit:** This is the best fit. It's TypeScript and Japanese kanji, both straight from your profile.
- **Difficulty: ambitious.** The kanji sits inside a `<ruby>` element and the hiragana that follows it is in a sibling element, so the word lookup has to cross element boundaries. The owner said "it might be tricky," and the issue is labeled `medium difficulty`. Ask the maintainer which approach they want before you start.
- **Preferred checks:**
  - Pass: very active, release v3.2.42 on 2026-09-30, issue body is 909 characters.
  - Fail: 487 stars, slow maintainer replies.
- **What to verify before claiming:**
  - Every recent commit is a Dependabot dependency bump; they still count as merges to `main`, which is what the rubric checks.
  - The issue was filed in 2020 and the thread has been silent since. Check that it still happens on the current version.
  - The newest issue (#3110, 2026-10-15) has no reply yet, so expect slow reviews.

**2. MFlowCode/MFC#1509**: `check_chemistry()` runs twice, and the fallback constants are stale. Source: direct.
- **Fit:** Python (the toolchain), in a project close to chemistry and physics. The main solver is Fortran, but this issue only touches Python.
- **Difficulty: straightforward.** The issue names the exact file and lines.
- **Preferred checks:**
  - Pass: very active (last commit 2026-10-19), release v5.7.0 on 2026-09-12.
  - Fail: 434 stars, slow replies (only 2 of the 8 latest issues have a maintainer reply), issue body is 3,150 characters.
- ⚠️ **Tension: the work looks already done.**
  - Part (b), the duplicate `check_chemistry()` calls, was fixed by PR #1627, merged 2026-07-05.
  - Part (a), the stale fallback constants, looks resolved too. PR #2042 (2026-10-13) moved the validator to constants from `params/definitions.py`, and the hardcoded fallbacks no longer appear in `case_validator.py`.
  - The rubric accepts it because no check asks whether the fix has already landed.
  - The only contribution left is probably a comment asking the maintainer to close it.

### Rejected

**3. OpenChemistry/avogadrolibs#1714**: Allow user to set size of ghost atom (C++, chemistry). Source: direct.
- **Sank it, two required failures:**
  - **No open pull requests.** PR #1911 ("Fixes#1714", by peach280) is still open. Its last comment, from June 2025, asks the maintainer whether it was nearly ready.
  - **AI code must be allowed.** CONTRIBUTING.md says AI levels 0 and 1 (autocomplete, small snippets) "are probably fine and further levels are not." It also says code must be "implemented by a human." That rules out the AI-assisted workflow this course uses.
- **Preferred checks:**
  - Pass: very active, fast replies (most get a same-day maintainer reply), issue body is 653 characters.
  - Fail: last release (2.0.0) was 2026-04-01, which is 204 days ago; 692 stars.
- This is a shame for fit: it's chemistry and C++, which you want to get better at, and the maintainer had already pointed to exactly where the change goes.

### Rubric friction for `scan-notes.md`
- **No "work already done" check.** MFC#1509 passed every required check even though master appears to contain both fixes. A required check could ask whether a merged PR or a commit to the default branch already covers what the issue asks for.
- **Unclaimed only looks at assignees, again.** avogadrolibs#1714 has a 2024 "I will start right now" comment. The open PR sank it anyway, but the same gap showed up last round.
- **The AI check has no partial-ban case.** Avogadro allows some AI help but not AI-written code. The rubric only distinguishes "forbids" from "doesn't forbid", so this was a judgment call. The rubric could say directly that a policy limiting AI to autocomplete or snippets counts as a fail.

```json
[
  {
    "item": "https://github.com/melink14/rikaikun/issues/198",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-22 (merged PR #3112)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-22, within 10 days (all recent commits are dependabot PRs)"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "Most sampled issues (#3110, #2358, #2337, #2336) have no member reply"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v3.2.42 released 2026-09-30, 22 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "487 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug about hiragana after ruby kanji not being included"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs in timeline"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 909 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Doesn't include hiragana after kanji when hovering tofugu ruby spans'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no claim comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No linked or cross-referenced PRs"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md contains no AI policy"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One behavior: word lookup should continue past ruby element into following hiragana"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/MFlowCode/MFC/issues/1509",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master commit 2026-10-19 (#2040)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master commit 2026-10-19, 3 days ago"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "Only 2 of the 8 latest issues (#2086, #2084) have a member reply"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v5.7.0 released 2026-09-12, 40 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "434 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Two small validator-hygiene fixes in one file, not a tracker"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Only linked PR #1627 is merged; no closed-unmerged PRs"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 3150 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'case_validator: check_chemistry() runs twice + stale fallback constants...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Only linked PR #1627 is merged"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No AI ban; repo ships AGENTS.md with agent instructions"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Names exact lines in toolchain/mfc/case_validator.py and the fix for each part"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/OpenChemistry/avogadrolibs/issues/1714",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master commit 2026-10-22 (merged PR #3223)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master commit 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "5 of the 8 latest issues got a member reply, most within a day"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "2.0.0 released 2026-04-01, 204 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "692 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature request: customizable ghost atom radius"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No closed linked PRs; only #1911 (open)"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 653 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Allow user to set size of ghost atom'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #1911 'Fixes#1714 => Functionality for setting size of ghost atom' is OPEN"},
      {"name": "AI code must be allowed", "grade": "fail", "evidence": "CONTRIBUTING.md: 'levels 0 and 1 are probably fine and further levels are not'; code must be 'implemented by a human'"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Maintainer names the change: per-element radius vectors in avogadro/core/elements.cpp"}
    ],
    "verdict": "reject"
  }
]
```

----------------------------------

I ran the scan and graded the top 5. **The rubric accepts all five, but none is a strong pick.** Four of the five come from one 3-star repo whose owner opened all of its issues within a minute of each other yesterday. The ranking shows the same gaps as last time.

**Funnel**
- **Search:** 10 queries returned 260 unique results: Python 100, C++ 100, TypeScript 34, Rust 19, Go 6, Ruby 1. SQL, PL/pgSQL, TSX and MATLAB returned nothing.
- **Drop filters:** removing issues with an assignee left 224, and removing issues not updated in the last 30 days left 31.
- **Filters I couldn't apply:** "straightforward first" needs the issue body and "1000+ stars" needs repo data. Search results carry neither, so I skipped both, as the 10/15 note in `scan-notes.md` predicted.
- **Ordering:** fewest comments first. Fifteen results tie at 0 comments and the strategy has no tie-break, so I broke ties by most recent update. Every top-5 candidate came from the Python query with 0 comments; the tie-break decided the order.

### Accepted, in fit order

**1. MysterionRise/pubchem-finder#32**: Tested setup for LM Studio (local models). Top 5 at rank 1 (0 comments, updated 2026-10-22).
- **Fit:** Chemistry, which matches your profile. The task is a docs section ("No Python needed"), not code.
- **Difficulty: straightforward.** Add one `### LM Studio` section to `docs/clients.md`. You do need to install LM Studio and run a local model that can call tools.
- **Preferred checks:**
  - Pass: very active, release v2.0.1 today.
  - Fail: 6 stars, body is 2,020 characters.
  - Unclear: reply timeliness. Every recent issue was opened by the owner and has no comments, so there's nothing to measure.
- **Notes:**
  - It's a sub-issue of #23. A sibling task (PR #37, a VS Code setup) is open, but nothing targets #32.
  - The owner builds the project with Claude, so AI-assisted work is clearly welcome here.

**2. QMeshPy/distributed-quantum#51**: Request persistent browser storage and warn about eviction. Top 5 at rank 2.
- **Fit:** Weak. "Quantum" only appears in the repo name; the work is IndexedDB and browser storage code, in a 3-star repo.
- **Difficulty: moderate.** You have to find where the vault code lives in `frontend/`.
- **Preferred checks:**
  - Pass: very active, body is 897 characters.
  - Fail: no releases, 3 stars.
  - Unclear: reply timeliness, for the same reason as #32.
- It says "None; can be picked up independently", so it's the only QMeshPy pick you could start today.

**3. QMeshPy/distributed-quantum#68**: Compose-based CI integration test for the Kubo client (Python). Top 5 at rank 5.
- **Difficulty: moderate.** It touches CI, the compose setup and the Python client.
- **Preferred checks:** pass very active and small (591 characters); fail release and 3 stars.
- **Tension:** it depends on #61, which is still open, so the client it tests doesn't exist yet.

**4. QMeshPy/distributed-quantum#75**: Add the content node to the architecture diagrams. Top 5 at rank 3.
- **Difficulty: ambitious.** It's blocked on the #71 spike; the issue itself says "once the node decision is made."
- **Preferred checks:** pass very active and small (563 characters); fail release and 3 stars.

**5. QMeshPy/distributed-quantum#56**: Post eight design questions to the IPFS community forum and record the answers. Top 5 at rank 4.
- **Difficulty: ambitious.** You'd be speaking for a project you've never contributed to in front of the Helia and IPFS maintainers. It's community work, not code.
- **Preferred checks:** pass very active and small (923 characters); fail release and 3 stars.

### Rejected
None.

### Friction worth logging in `scan-notes.md`
- **The star filter is still dead, and that's why this top 5 is weak.** Putting `stars:>=1000` inside each query would have removed all five candidates. The well-known repos that survived the drop filters (qiskit-ibm-runtime, mitiq, cuda-quantum, Qiskit) landed at ranks 18–28 because they have 1–11 comments.
- **There's no tie-break.** Fifteen results tie at 0 comments, so the tie-break picks the whole top 5. Mine was most recent update, which favors repos that just batch-opened their issues.
- **One repo can fill the top 5.** A "max 1–2 per repo" rule would have made room for other projects.
- **The keyword match is too loose.** The words match repo names, so storage and IPFS issues came in under "quantum".
- **The rubric has no "blocked by an open dependency" check.** #68 and #75 passed even though their prerequisites (#61, #71) are still open.
- **The reply-timeliness check can't measure a fresh repo.** When every recent issue was opened by the owner and has no comments, there's no reply to time.

Want me to append these to `scan-notes.md`?

```json
[
  {
    "item": "https://github.com/MysterionRise/pubchem-finder/issues/32",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master merge 2026-10-22 (PR #36)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues are owner-filed on 2026-10-22 with 0 comments; no responses to measure"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v2.0.1 released 2026-10-22"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "6 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single task (one docs section); it is a sub-item 'Part of #23', not the tracker"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is small", "grade": "fail", "evidence": "Issue body is 2020 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Tested setup for LM Studio (local models)'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No PR references #32 (open PR #37 is the VS Code sibling task)"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": ".github/CONTRIBUTING.md has no AI ban; repo commits are authored by claude"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Done when a PR adds a ### LM Studio section to docs/clients.md'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/51",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs (only cross-ref is tracker #43)"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 897 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'feat(vault): request persistent storage and warn about eviction'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #51"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Call navigator.storage.persist() and show a storage banner; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/68",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single CI test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 591 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(content-node): compose-based integration test for the Kubo client'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #68"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One CI job: add content via Python client, read back via gateway, compare CIDs (depends on open #61)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/75",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single docs update; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 563 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'docs(helia): add the content node to the architecture and target diagrams'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #75"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Update architecture diagram and Sections 12/14 (blocked on open spike #71)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/56",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single outreach task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is small", "grade": "pass", "evidence": "Issue body is 923 characters"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'docs(helia): post the open design questions to the IPFS community and record answers'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #56"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Eight threads are open and linked' and answers summarized in the doc"}
    ],
    "verdict": "accept"
  }
]
```

--------

--------

I ran the scan again and graded the new top 5. **The rubric accepts four, all from QMeshPy/distributed-quantum, and rejects one.** Your new "code over docs" filter worked and moved the docs-only issues to the bottom. But the same 3-star repo still fills most of the top 5, because the star filter still can't run at the ranking stage.

**Funnel**
- **Search:** same 10 queries and the same 260 unique results as last time.
- **Drop filters:** removing issues with an assignee left 224, and removing issues not updated in the last 30 days left 31.
- **Ordering:**
  - **Code over docs:** applied. An issue counts as docs if it has a `documentation` or `docs` label or its title starts with `docs`. That moved 7 issues to the bottom, including pubchem-finder#32 and QMeshPy #75 and #56.
  - **Fewest comments first:** applied.
  - **Straightforward first and 100–1000 stars:** skipped. Search results include neither the issue body nor repo stars.
  - **Tie-break:** there's still none in the strategy, so I used most recent update.
- **Result:** all five have 0 comments and are classed as code. The Python query surfaced the four QMeshPy issues and the Rust query surfaced Qleisli.
- **Rubric:** your rubric no longer has "Issue is small", so it isn't graded below.

### Accepted, in fit order
None of these four touches quantum code. The work is browser storage and pinning in a repo that only has "quantum" in its name. All four have the same preferred grades: very active passes, release and popularity fail (no releases, 3 stars), and reply timeliness is unclear because every issue is owner-filed with no comments.

The repo does merge pull requests from outside contributors (for example, PR #82 from SaishKorgaonkar today), which is a good sign for a newcomer.

1. **QMeshPy/distributed-quantum#53**: unit tests for `local-index` and `sync-queue` (TypeScript). Rank 3.
   - **Difficulty: straightforward.** It names both files (`features/ipfs/lib/local-index.ts`, `features/vault-pinning/lib/sync-queue.ts`), the test runner (`bun test`) and the cases to cover.
   - It can be picked up independently. This is the best pick of the four.
2. **QMeshPy/distributed-quantum#51**: request persistent browser storage and warn about eviction (TypeScript). Rank 1.
   - **Difficulty: moderate.** You have to find where the vault's first publish happens.
   - It can be picked up independently.
3. **QMeshPy/distributed-quantum#47**: remove the legacy `nft.storage` alias (TypeScript). Rank 4.
   - **Difficulty: ambitious.** It names the files, but also leaves an open design question: should old audit records be mapped to `pinata` when read, or migrated? Raise that with the maintainer before you start.
4. **QMeshPy/distributed-quantum#68**: compose-based CI integration test for the Kubo client (Python). Rank 2.
   - **Difficulty: moderate.**
   - **Tension:** it's blocked on #61, which is still open, so the client it tests doesn't exist yet.

### Rejected
5. **MGYamada/Qleisli#223**: migrate the Lean-kernel CI from proof-oriented to test-oriented harnesses (Rust). Rank 5.
   - **Sank it, two required failures:**
     - **Not a tracking issue:** fail. It's a "medium-term CI/harness milestone" with three planned CI lanes, and it has spawned follow-up issues (#255, #268, #269).
     - **scope-feasible:** fail. There's no single piece of work in it.
   - It also has 0 stars.

### Friction for `scan-notes.md`
- **The new docs filter works.** It's checkable from labels and titles, which is the free kind of filter the strategy needs.
- **The star filter still can't run, now as 100–1000.** To make it work, put `stars:100..1000` inside each query. That alone would have removed QMeshPy and Qleisli.
- **There's still no tie-break and no per-repo cap.** One repo that batch-filed its issues yesterday takes four of the five slots.
- **"Straightforward first" can't be applied at ranking either.** It needs the issue body, so it belongs in the rubric as the difficulty note, which you already have.

```json
[
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/53",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs (only cross-ref is tracker #43)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(vault): unit tests for local-index and sync-queue'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Only open PR is #41 (ENS helpers), unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Tests for local-index.ts and sync-queue.ts; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/51",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'feat(vault): request persistent storage and warn about eviction'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Only open PR is #41 (ENS helpers), unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Call navigator.storage.persist() and show a storage banner; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/47",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single cleanup; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'chore(vault-pinning): remove the legacy nft-storage alias'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Only open PR is #41 (ENS helpers), unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Remove alias from types.ts, delete services/nft-storage.ts, fix use-pin.ts default"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/68",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single CI test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(content-node): compose-based integration test for the Kubo client'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, no comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Only open PR is #41 (ENS helpers), unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One CI job comparing CIDs via client and gateway (depends on open #61)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/MGYamada/Qleisli/issues/223",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #428)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed with 0 comments"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.3.0-alpha released 2026-10-11"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is popular", "grade": "fail", "evidence": "0 stars"},
      {"name": "Issue is not a tracking issue", "grade": "fail", "evidence": "'medium-term CI/harness milestone' with three lanes; spawned follow-ups #255, #268, #269"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Linked PRs #252, #256, #389, #422 merged; #221 closed (one closed unmerged)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'progressively migrate lean-kernel CI...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PRs in repo"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'Human-written and AI-assisted contributions follow the same review and verification requirements'"},
      {"name": "scope-feasible", "grade": "fail", "evidence": "Staged migration of the whole CI harness; no single piece of work"}
    ],
    "verdict": "reject"
  }
]
```

-------------------

I stopped this scan before grading anything. The strategy's only query doesn't work, so there was no valid set of results to rank.

**What went wrong with the query**
- **As written, it fails.** `gh search issues` has no `--stars` flag, so the command exits with `unknown flag: --stars` and returns nothing.
- **Moving it into the query doesn't work either.** GitHub's issue search doesn't support `stars:` as a filter. It treats the text as search words instead, so the search matches issues that mention stars and returns junk: 8 results, such as a "github star counter" bug, a Java legacy repo and a Chinese daily-news repo. After the drop filters, one result was left: SecureBananaLabs/bug-bounty#743, a docs issue with 1,450 comments. It wasn't worth grading.
- **Without stars, the query is fine.** The same query without the stars part returns 100 results.

**How to fix it.** I'd do the first of these:
1. **Remove the stars part from the query** and leave popularity to the rubric's "Repo is moderately popular" check. Search can't filter issues by star count, and ranking can't see stars either.
2. **Look up each repo's star count during ranking.** That works, but it costs one API call per repo, and your skill keeps ranking to the fields search already returned. It would be a deliberate change to the skill.

**Other things I noticed in the edited files**
- **Rubric typo.** "Repo is moderately popular" says "at least 1000 and at most 1000 stars", so only a repo with exactly 1,000 stars passes. You probably meant 100–1000.
- **Claim-comment filter.** The new "drop any result with a claim comment" filter needs the issue's comments, which search results don't include. It belongs in the rubric's "Issue is unclaimed" check instead, which would fix the gap the earlier grading runs kept hitting.
- **"Straightforward first" still can't be applied at ranking.** It needs the issue body.
- **Missing comment above the query.** The strategy asks for a comment tracing each query to a sentence in your fit profile, and the new query doesn't have one.
- **"Signal processing" isn't searched.** You added it to the fit profile in `scope.md`, but the query still only searches `chemistry OR quantum OR kanji`.
- **Fewer results overall.** Merging ten queries into one caps the scan at 100 results total, down from about 260 last time. If breadth matters, go back to one query per language or raise `--limit`.

If you want, I can rerun the scan with the stars part removed and grade the top 5 once you've decided on the fix.

-----------------------

I ran the scan and graded the top 5. **The rubric accepts all five, but none is a strong pick.** Four are the QMeshPy issues from the last two scans, and the fifth is a link-list entry outside your fit profile. QMeshPy hasn't changed since the last grading: the four issues still have no assignees and no comments. Its new PR #83 closes #54, which isn't one of these.

**Funnel**
- **Search:** your one query, with the stars part removed, returned 100 results. That's the limit, so it may have cut off more.
- **Drop filters:** removing issues with an assignee left 75, and removing issues not updated in the last 30 days left 21.
- **Ordering:**
  - **Code over docs:** applied, using labels and titles.
  - **Fewest comments first:** applied.
  - **100–1000 stars:** skipped, because search results don't include star counts.
  - **Tie-break:** there's still none, so I used most recent update.
- **Result:** all five have 0 comments and are classed as code.

### Accepted, in fit order
None of these fits your profile well. The four QMeshPy issues are browser storage and pinning work, not quantum code. Their preferred grades:
- Pass: very active (last merge 2026-10-22).
- Fail: no releases, and 3 stars against the new 100–1000 range.
- Unclear: reply timeliness, because every recent issue is owner-filed with no comments.

1. **QMeshPy/distributed-quantum#53**: unit tests for `local-index` and `sync-queue` (TypeScript). Rank 3.
   - **Difficulty: straightforward.** It names both files and the test runner, and can be picked up independently.
2. **QMeshPy/distributed-quantum#51**: request persistent browser storage and warn about eviction (TypeScript). Rank 1.
   - **Difficulty: moderate.** You have to find where the vault's first publish happens.
3. **QMeshPy/distributed-quantum#47**: remove the legacy `nft.storage` alias (TypeScript). Rank 4.
   - **Difficulty: ambitious.** Someone has to decide whether old audit records are mapped to `pinata` when read or migrated. Raise that with the maintainer first.
4. **QMeshPy/distributed-quantum#68**: CI integration test for the Kubo client (Python). Rank 2.
   - **Difficulty: moderate.**
   - **Tension:** it's blocked on #61, which is still open.
5. **StudentSuite/awesome-skills-plugins-for-students#305**: no anatomy or physiology study skill (a JSON entry in a curated list). Rank 5.
   - **Fit:** none. It isn't one of your areas, and the work is finding a link, not writing code. The ranking counted it as code only because its label is `content`, not `documentation`.
   - **Difficulty: straightforward**, but the hard part is the research. Merged PR #331 says its author searched for a fitting skill for #305 and "did not find a public, documented skill that genuinely fits." There may be nothing to add.
   - **Preferred checks:**
     - Pass: very active, release v1.1.0 exactly 60 days ago.
     - Fail: 26 stars.
     - Unclear: reply timeliness.

### Rejected
None.

### Friction for `scan-notes.md`
- **The same 3-star repo takes four of the five slots for the third scan in a row.** Two fixes would help:
  - A per-repo cap ("at most one result per repo") can be checked from search results and would push other projects into the top 5.
  - A tie-break is still missing; all the leaders are tied at 0 comments.
- **The 100–1000 stars filter still can't run at ranking.** Your rubric's "Repo is moderately popular" check already covers it, so you could delete it from the strategy.
- **The single query costs breadth.** It returns at most 100 results, which left 21 survivors this time against 31 from the per-language queries.
- **The query still doesn't search "signal processing"** and has no comment tracing it to your fit profile.
- **The docs filter misses non-code work under other labels.** #305 is curation, not code, but its `content` label slipped past. Adding `content` to the docs label list would catch it.

```json
[
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/53",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs (only cross-ref is tracker #43)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(vault): unit tests for local-index and sync-queue'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 (closes #54) and #41 (ENS) are unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Tests for local-index.ts and sync-queue.ts; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/51",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'feat(vault): request persistent storage and warn about eviction'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 (closes #54) and #41 (ENS) are unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Call navigator.storage.persist() and show a storage banner; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/47",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single cleanup; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'chore(vault-pinning): remove the legacy nft-storage alias'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 (closes #54) and #41 (ENS) are unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Remove alias from types.ts, delete services/nft-storage.ts, fix use-pin.ts default"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/68",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single CI test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(content-node): compose-based integration test for the Kubo client'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 (closes #54) and #41 (ENS) are unrelated"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One CI job comparing CIDs via client and gateway (depends on open #61)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/StudentSuite/awesome-skills-plugins-for-students/issues/305",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-21 (PR #331)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-21"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All 8 sampled issues owner-filed 2026-10-17 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v1.1.0 released 2026-08-23, 60 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "26 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single gap: add one anatomy/physiology skill entry"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Only cross-ref is merged PR #331, which mentions #305 without attempting it"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'STEM Subjects has no human anatomy / physiology study skill'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #305"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI ban; the repo curates AI agent skills"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Find one real, documented skill and add it' with a data/last-verified.json entry"}
    ],
    "verdict": "accept"
  }
]
```

-----------------

I ran the scan and graded the top 5. **The rubric accepts all five, but none is a good pick for you.** The new keywords are too broad: "voice" and "math" matched voice-recording apps, a recruiting bot and a Java kernel. The language filter also let Java and Kotlin repos through, so the query isn't restricting languages the way the per-language queries used to.

**Funnel**
- **Search:** the single query returned 100 results, which is the limit.
- **Drop filters:** removing issues with an assignee left 82, and removing issues not updated in the last 30 days left 51.
- **Ordering:**
  - **Code over docs:** applied, using labels and titles.
  - **Fewest comments first:** applied.
  - **100–1000 stars:** skipped, because search results don't include star counts.
  - **Tie-break:** there's still none, so I used most recent update. 32 results tie at 0 comments.
- **Result:** all five candidates have 0 comments and were classed as code.

### Accepted, in fit order
All five fail the same preferred checks: no repo has more than 4 stars, and only tandemcode has a release.

1. **Djbrl/tandemcode-harness#2**: Wolof voice input (TypeScript). Rank 5.
   - **Fit:** the closest of the five. It's speech recognition, which is near signal processing.
   - **Difficulty: ambitious.** You'd first research open speech models that handle Wolof and post the findings, then build a "speech server" setting that sends recordings to an `/audio/transcriptions` endpoint.
   - **Preferred checks:** pass very active, release v0.1.0 on 2026-10-18; fail 0 stars; reply timeliness unclear.
   - **Notes:** it's a hackathon entry. The project welcomes AI-assisted work if you review every line, test in the browser and disclose the tool in your PR.
2. **LazarusStack/openfury#3**: new `bpo-voice` use case for an AI phone-screening recruiter (Python). Rank 4.
   - **Fit:** weak. It's Python, but none of your areas.
   - **Difficulty: moderate.** You'd need to find how the existing `job-screening` and `support` use cases are built.
   - **Preferred checks:** pass very active; fail 0 stars and no release; reply timeliness unclear.
   - The repo was created three days ago.
3. **Amber-Swent/amber#112**: relatives' voice recording playback (Kotlin). Rank 1.
   - **Fit:** none. Kotlin isn't in your profile.
   - **Difficulty: moderate.** The issue is a two-line user story and doesn't say where the change goes.
   - **Preferred checks:** pass very active; fail 2 stars and no release; reply timeliness unclear.
   - ⚠️ **It looks like a university team project**: the commits mention "review comments of the coaches". Outside PRs are probably not wanted. The rubric has no check for this.
4. **kstackhq/kstack#245**: explore adding voice control to the UI. Rank 3.
   - **Fit:** negative. Kubernetes is on your avoid list.
   - **Difficulty: ambitious.** It's an open-ended exploration.
   - **Preferred checks:** pass very active; fail 2 stars and no release; reply timeliness unclear.
   - **Notes:**
     - The issue says "No code is expected." The deliverable is a note in `docs/notes/`. Your docs filter missed it because it has no docs label.
     - The AI policy allows assisted work with an `Assisted-by:` trailer.
5. **JackFurton/who-would-build-a-kernel-in-java#74**: overflow-checked `Math.addExact` and related methods. Rank 2.
   - **Fit:** negative. Java is on your avoid list.
   - **Difficulty: straightforward.** It names the file (`kernel/src/java/lang/Math.java`), the exact methods and when it's done.
   - **Preferred checks:** pass very active and timely replies (4 of 6 issues answered in about a day); fail 4 stars and no release.
   - **Notes:** this is actually the best-scoped issue of the five. You'd claim it by commenting `@duke-bot claim`.

### Rejected
None.

### Friction for `scan-notes.md`
- **The language filter isn't working in the single query.** A Java repo and a Kotlin repo came through even though neither language is listed. The earlier one-query-per-language form (`--language python`, etc.) did filter properly. Going back to it also fixes the 100-result cap.
- **"voice" and "signal" are too generic.** They matched voice notes, the Signal messenger and Unix signals. Phrases like `"signal processing"`, `DSP`, `FFT` or `audio` match your profile more precisely.
- **"math" matches mental-math games and `java.lang.Math`.** Pairing it with a domain word (`"linear algebra"`, `numerical`) would cut the noise.
- **The rubric has no "does this repo accept outside contributors" check.** That would have caught Amber, a class project. CONTRIBUTING.md is a cheap place to look: Amber has none.
- **The docs filter misses issues that say "no code" in the body.** kstack#245 is one. This can only be judged from the issue body, so it belongs in the rubric.

```json
[
  {
    "item": "https://github.com/Djbrl/tandemcode-harness/issues/2",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-20 (PR #9)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-20"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-19 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.1.0 released 2026-10-18"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "0 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature: Wolof speech input"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Wolof voice input'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #2"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'You are welcome to work the same way' with AI agents, with disclosure"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Add a 'speech server' setting posting to an /audio/transcriptions endpoint"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/LazarusStack/openfury/issues/3",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-19"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-19"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-19, almost all with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "0 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single new use case extending job-screening"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'New use case: bpo-voice (customer service voice process)'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #3"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md contains no AI policy"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One use case with listed coverage: shifts, cab facility, typing speed, prior process"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/Amber-Swent/amber/issues/112",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-21 (PR #201)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-21"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues team-filed with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "2 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single user story: audio playback of a chosen clip"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Only cross-ref is merged PR #148 (docs), no closed-unmerged PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: \"Relatives' Voice Recording Feature\""},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #112"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md; AGENTS.md present; no ban"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Implement the audio playback from the backend to play chosen audio clip'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/kstackhq/kstack/issues/245",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (#379)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "Sampled issues owner- or bot-filed with no member replies to measure"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "2 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single exploration with one deliverable note"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Explore adding voice control to the UI'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #245"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md AI Policy: AI encouraged with 'Assisted-by' tag; bans only fully LLM-authored work"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'The deliverable is a short note in docs/notes/'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/JackFurton/who-would-build-a-kernel-in-java/issues/74",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master commit 2026-10-22 (#221)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master commit 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "4 of 6 sampled issues got member replies within ~1 day"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "4 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "One set of overflow-checked Math methods"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs (cross-ref #160 is an issue)"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Math: addExact, subtractExact, multiplyExact, negateExact, toIntExact'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #74"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md contains no AI policy"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Names Math.java, the exact methods, and 'Done when' conformance tests"}
    ],
    "verdict": "accept"
  }
]
```

-------------

I ran the scan and graded the top 5. **Three are accepted and two rejected, and the two rejected ones are the only good projects in the set.** gombit and erpc are real, active projects, but each already has an open PR on the issue. The three accepted issues come from repos with 1–3 stars.

**Funnel**
- **Search:** 20 searches (2 keyword groups × 10 languages) returned 811 unique results with no errors. Seven searches reached the 100-result limit.
- **Drop filters:** removing issues with an assignee left 694, and removing issues not updated in the last 30 days left 223.
- **Ordering:**
  - **Code over docs:** applied, using labels and titles.
  - **Fewest comments first:** applied.
  - **100–1000 stars:** skipped, because search results don't include star counts.
  - **Tie-break:** there's still none, so I used most recent update. More than 150 results tie at 0 comments, so the tie-break picked the whole top 5.
- **Result:** all five candidates have 0 comments and were classed as code.

### Accepted, in fit order
None is a good fit. QMeshPy hasn't changed since the last grading: the issues still have no assignees and no comments, and #61 is still open. All three repos fail release and popularity (no releases, 1–3 stars), and reply timeliness is unclear because every issue was opened by the owner and has no comments.

1. **QMeshPy/distributed-quantum#51**: request persistent browser storage and warn about eviction (TypeScript). Rank 4, chemistry/quantum/kanji query.
   - **Difficulty: moderate.**
2. **QMeshPy/distributed-quantum#68**: Kubo client CI integration test (Python). Rank 5, chemistry/quantum/kanji query.
   - **Difficulty: moderate.**
   - **Tension:** it's still blocked on #61, which is open.
3. **QuinCyMP/QuinCyMP-GDD#3**: add a gacha game genre reference file. Rank 1, math/signal/FFT query.
   - **Fit:** none. It matched "math" through "pity math", and the work is writing a 150–250-line Markdown file for a game-design AI skill.
   - The ranking counted it as code only because it's labeled `enhancement`.
   - **Difficulty: straightforward.** It names the file, which file to copy the structure from, and when it's done.

### Rejected
4. **erpc/erpc#869**: a large JSON-RPC `id` is silently converted to the wrong number (Go). Rank 3, math/signal/FFT query.
   - **Sank it:** No open pull requests. PRs #870 and #1326 are both open; #1326 says it will "reject lossy ids."
   - This is the strongest repo of the round: 794 stars, release 0.4.0 on 2026-10-11, maintainers reply within days, and agent-written PRs are explicitly welcome if you disclose them.
5. **gombit-dev/gombit#611**: the OpenAPI document doesn't declare the 429 response or its `Retry-After` header (Go). Rank 2, math/signal/FFT query.
   - **Sank it:** No open pull requests. PR #614 ("document resend rate limit response") is open.
   - It's a well-scoped bug in a 17-star repo with a release three days ago.

### What the scan is telling you
The searches are working now. The remaining problem is the ranking: "fewest comments first" with no other signal sorts brand-new issues in tiny repos to the top, every time. Two changes would fix it:
- **Let ranking look up star counts.** That's one API call per repo, about 150 for this scan, and it would make your 100–1000 filter work; erpc would be near the top. It's a deliberate change to the skill, since ranking currently uses only what search returns.
- **Add a per-repo cap of at most one issue per repo.** It can be checked from search results today, and it would stop QMeshPy from filling slots three scans running.

```json
[
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/51",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'feat(vault): request persistent storage and warn about eviction'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 and #41 do not reference #51"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Call navigator.storage.persist() and show a storage banner; 'can be picked up independently'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QMeshPy/distributed-quantum/issues/68",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #82)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "3 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single CI test task; sub-item 'Part of #43'"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'test(content-node): compose-based integration test for the Kubo client'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "Open PRs #83 and #41 do not reference #68"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy file; silence passes"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One CI job comparing CIDs via client and gateway (depends on open #61)"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/QuinCyMP/QuinCyMP-GDD/issues/3",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main commit 2026-10-22"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main commit 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues owner-filed 2026-10-21 with 0 comments"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "No releases"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "1 star"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single file: references/gacha.md"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add a gacha / mobile live-service genre reference'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #3"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No CONTRIBUTING.md or AI policy; repo is itself an AI agent skill"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Done means: the file exists, SKILL.md lists it in the References table'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/erpc/erpc/issues/869",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (#1325)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "Recent issues #1289, #1276 got member replies within 1-3 days"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "0.4.0 released 2026-10-11"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "794 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug: float64-to-int64 cast on JSON-RPC id"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Linked PR #1092 merged; no two closed-unmerged PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'bug: Silent float64 to int64 truncation...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PRs #870 and #1326 ('reject lossy ids') are OPEN"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md: 'Agent-written PRs are welcome' with disclosure"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Fix the cast at common/json_rpc.go:1303 and :210"}
    ],
    "verdict": "reject"
  },
  {
    "item": "https://github.com/gombit-dev/gombit/issues/611",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (#605)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues filed by one member with 0 comments"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v0.8.0 released 2026-10-19"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "fail", "evidence": "17 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug: undeclared 429 and Retry-After on one operation"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No closed-unmerged linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: '[bug] Email verification resend: ...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "fail", "evidence": "PR #614 'fix(auth): document resend rate limit response' is OPEN"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md documents Claude Code and Cursor skills for contributors; no ban"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Declare 429 and Retry-After on auth-resend-email-verification (auth/verification.go:330-339)"}
    ],
    "verdict": "reject"
  }
]
```

--------------------

This scan worked much better. **The rubric accepts four of the five, and every one comes from a real project with 100–900 stars.** The top pick is a strong fit for you. Two of the accepted issues have catches you should know about before claiming (noted under each).

**What the three fixes did**
- **`-linked:pr` in the searches:** the 20 searches returned 787 unique results, about 25 fewer than last scan, because issues with linked PRs are now excluded. Neither rejection this time was for an open PR.
- **Star lookup:** after the drop filters (690, then 206), I looked up stars for the 109 remaining repos. Only 9 code issues were in the 100–1000 range, and they now rank first.
- **One issue per repo:** QMeshPy dropped to rank 13 and appears once.

### Accepted, in fit order

**1. OpenChemistry/avogadroapp#910**: add F6 / Shift+F6 to move keyboard focus between docks and the 3D view (C++, 271 stars). Rank 1, chemistry/quantum/kanji query.
- **Fit:** strong. It's chemistry software in C++, which you want to get better at.
- **Difficulty: straightforward.** The issue names the spot (`avogadro/mainwindow.cpp:635`, next to the Ctrl+Tab shortcuts) and the exact behavior.
- **Preferred checks:** pass very active, popular, timely replies (the maintainer usually answers the same day); fail release (2.0.0 was 204 days ago).
- ⚠️ **AI policy:** this repo's CONTRIBUTING.md says nothing about AI, so the check passes. But its sister repo avogadrolibs, run by the same maintainer (ghutchis), only allows autocomplete-level AI use. Ask him before you lean on AI for this one.

**2. stan-dev/math#3362**: add an ITP one-dimensional solver (C++, 842 stars). Rank 5, math/signal/FFT query.
- **Fit:** strong. It's mathematics in C++.
- **Difficulty: ambitious.** It's a new solver in Stan Math's autodiff code; a maintainer pointed to `solve_powell.hpp` and `solve_newton.hpp` as models.
- **Preferred checks:** pass very active, release v5.4.0 on 2026-09-16, popular; fail timely replies (no maintainer replies in the 6 recent issues sampled).
- **Notes:**
  - Stan's AI policy welcomes AI-assisted work if you disclose it and can defend every line; it rejects fully automated submissions.
  - Someone asked to be assigned on 2026-10-21 and hasn't had an answer. The rubric only checks assignees, so it passes, but check the thread before claiming.

**3. DouglasNeuroInformatics/OpenDataCapture#1640**: the Breakout Task paddle can move past the canvas walls (TypeScript, 119 stars). Rank 2, math/signal/FFT query.
- **Fit:** language only. It's TypeScript, but none of your topics.
- **Difficulty: straightforward.** It gives the exact lines (`DNP_BREAKOUT_TASK/index.ts:203-207` and `:94-99`), how to reproduce it, and the expected values. Labeled `Difficulty: Low`.
- **Preferred checks:** pass active, release v2.5.2 on 2026-09-25, popular; fail very active (last merge 15 days ago); reply timeliness unclear (recent issues are team-filed with no comments).

**4. aqlaboratory/openfold-3#323**: allow setting the residue identifier for SMILES input (Python, 901 stars). Rank 3, chemistry/quantum/kanji query.
- **Fit:** strong on paper: chemistry in Python.
- **Preferred checks:** pass very active, popular, timely replies; fail release (v0.5.0 was 62 days ago, 2 days past your limit).
- ⚠️ **It looks already done.** PR #386 ("Allow custom residue names for SMILES ligands") was merged on 2026-08-28; the issue was just never closed. The rubric has no "work already landed" check, so it passes. The only thing left is probably a comment asking for it to be closed.

### Rejected

**5. OpenChemistry/avogadrolibs#3188**: Auto Optimize should use Alt for larger steps and not signal a change for ignored keys (C++, 692 stars). Rank 4.
- **Sank it:** AI code must be allowed. The policy says "levels 0 and 1 are probably fine and further levels are not."
- It's also been claimed: JJC3321 asked today and the maintainer said yes. The rubric missed that because it only looks at assignees.

### Two rubric gaps showed up again
- **"Issue is unclaimed" ignores claim comments.** It missed avogadrolibs#3188 and the stan request.
- **There's no "work already landed" check.** It passed openfold-3#323 and, earlier, MFC#1509.

Both are worth adding to `rubric.md`.

**My recommendation: claim avogadroapp#910.** Comment on the issue first, and ask about AI use in the same comment.

```json
[
  {
    "item": "https://github.com/OpenChemistry/avogadroapp/issues/910",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master merge 2026-10-22 (PR #917)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "5 of 5 sampled non-owner issues got member replies within 0-2 days"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "2.0.0 released 2026-04-01, 204 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "271 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single feature: F6/Shift+F6 pane focus shortcuts"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add F6 / Shift+F6 to move keyboard focus...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #910"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "avogadroapp CONTRIBUTING.md (17 lines) has no AI policy"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "'Add two QShortcuts in MainWindow, next to ... avogadro/mainwindow.cpp:635'"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/stan-dev/math/issues/3362",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last develop merge 2026-10-22 (PR #3432)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last develop merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "fail", "evidence": "None of 6 sampled recent issues has a member reply"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v5.4.0 released 2026-09-16"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "842 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single new function: solve_itp"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Add ITP one dimensional solver'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees (assignment request on 2026-10-21 unanswered)"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #3362"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "Stan AI Contribution Policy: 'We welcome AI-assisted contributions' with disclosure; bans only fully automated submissions"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One solver modeled on solve_powell.hpp / solve_newton.hpp, named solve_itp"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/DouglasNeuroInformatics/OpenDataCapture/issues/1640",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-07 (PR #1654), 15 days ago"},
      {"name": "Repo is very active", "grade": "fail", "evidence": "Last main merge 2026-10-07, more than 10 days ago"},
      {"name": "Issue replies are timely", "grade": "unclear", "evidence": "All sampled issues team-filed with 0 comments"},
      {"name": "Repo has a recent release", "grade": "pass", "evidence": "v2.5.2 released 2026-09-25"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "119 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single bug: paddle clamp in Breakout Task"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Breakout Task paddle can move past the canvas walls'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees, 0 comments"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #1640"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "CONTRIBUTING.md has no AI policy; AGENTS.md present"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Fix clamps at DNP_BREAKOUT_TASK/index.ts:203-207 and :94-99"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/aqlaboratory/openfold-3/issues/323",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last main merge 2026-10-22 (PR #465)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last main merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "3 of 6 sampled issues got member replies within 0-1 days; the rest have no reply yet"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "v0.5.0 released 2026-08-21, 62 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "901 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Single option: residue identifier for SMILES ligands"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "Linked PR #386 merged; no closed-unmerged PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Allow residue/component identifier specification for SMILES input.'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #323"},
      {"name": "AI code must be allowed", "grade": "pass", "evidence": "No AI ban found; repo ships a .claude directory"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "One optional field in the ligand block of the input format"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/OpenChemistry/avogadrolibs/issues/3188",
    "checks": [
      {"name": "Repo is active", "grade": "pass", "evidence": "Last master merge 2026-10-22 (PR #3223)"},
      {"name": "Repo is very active", "grade": "pass", "evidence": "Last master merge 2026-10-22"},
      {"name": "Issue replies are timely", "grade": "pass", "evidence": "4 of 4 sampled non-owner issues got member replies within a day"},
      {"name": "Repo has a recent release", "grade": "fail", "evidence": "2.0.0 released 2026-04-01, 204 days ago"},
      {"name": "Repo is not archived", "grade": "pass", "evidence": "isArchived=false"},
      {"name": "Repo is moderately popular", "grade": "pass", "evidence": "692 stars"},
      {"name": "Issue is not a tracking issue", "grade": "pass", "evidence": "Two small fixes in one function, AutoOpt::keyPressEvent"},
      {"name": "Issue is not difficult", "grade": "pass", "evidence": "No linked PRs"},
      {"name": "Issue is not a usage question", "grade": "pass", "evidence": "Title is a statement: 'Auto Optimize: Alt for larger steps...'"},
      {"name": "Issue is unclaimed", "grade": "pass", "evidence": "No assignees (JJC3321 claimed in a comment on 2026-10-22, maintainer agreed)"},
      {"name": "No open pull requests", "grade": "pass", "evidence": "No open PR references #3188"},
      {"name": "AI code must be allowed", "grade": "fail", "evidence": "CONTRIBUTING.md: 'levels 0 and 1 are probably fine and further levels are not'"},
      {"name": "scope-feasible", "grade": "pass", "evidence": "Names autoopt.cpp:818-853 and the two changes"}
    ],
    "verdict": "reject"
  }
]
```