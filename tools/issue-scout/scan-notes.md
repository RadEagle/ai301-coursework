## 10/15/2026: 
* Added "Chemistry or Quantum" into the fit profile
* Split query into multiple queries, one per language

Strategy edit: added thresholds to the two preference filters ("2 files or less, if called out" and "1000+ stars"). The ranking didn't change: same 262 results, 29 kept, and the same top 5 in the same order. None of the 5 issues changed, so the grades from the second scan stand.
- Both filters still need information search results don't include (issue body, repo stars), so the scout can't apply them at ranking. Adding thresholds doesn't fix that. To have them act:
  - stars: put `stars:>=1000` inside each query (GitHub issue search accepts repo qualifiers like this; check that `gh search issues` passes it through), or drop the filter, since the rubric already grades "Repo is popular".
  - file count: move it to the rubric as a preferred check ("issue names 2 or fewer files"). Only the issue body can show it.     
- The tie-break is still missing. Fix that first: 10 results tied at 0 comments decide the whole top 5.