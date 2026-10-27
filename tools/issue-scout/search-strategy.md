# Search strategy: where your scout looks, and why

<!--
THIS IS THE PART YOU WRITE. The scout in SKILL.md executes whatever
queries and filters you define here. It ships empty on purpose: the
strategy is your judgment about where YOUR first contribution lives,
and a scan without authored queries is just someone else's defaults.

A filled strategy must contain:

1. At least one query in the Queries section. Each query is a real
   `gh search issues` invocation, and each should trace to a sentence
   of your fit profile in scope.md: if you cannot say which sentence
   produced a query, the query is probably not yours. Search breadth
   is the point at this stage: prefer generous limits and let the
   ranking filters do the narrowing.

2. At least one ranking filter in the Ranking filters section. A
   filter is a condition or an ordering over fields the search
   results already carry (last activity date, assignee presence,
   label set, comment count, repo). It must be checkable from the
   result fields alone: if deciding it would need opening the issue
   page, it belongs in your rubric, not here. Ranking is the free
   stage; keep it free. Make at least one filter an ordering, or
   state your tie-break: with drop conditions alone, the scout takes
   the top of whatever order the searches happened to return, and
   the graded candidates stop being traceable to you.

3. The top-N line, kept or deliberately changed.
-->

## Queries

<!-- Real gh search invocations, one per line, each with a comment
naming the fit-profile sentence it came from. Example SHAPE (write
your own; these values belong to nobody):

gh search issues --label "good first issue" --language python --state open --limit 100 --json title,repository,labels,assignees,commentsCount,updatedAt,url
-->

<!-- Languages: "I want to engage in issues in Python, TypeScript, React, PostgreSQL, and MATLAB. I want to get better at Go, Rust, Ruby, and C++."
Topics: "The project area I want to work on should revolve around chemistry, quantum physics, mathematics, japanese kanji, and signal processing."
GitHub allows at most 5 AND/OR/NOT per query, so the keywords are split into two groups. Edit the language list or a keyword group in one place.
"-linked:pr" drops issues that already have a linked pull request; it must stay its own argument after "--", because inside the "language:$lang" string it breaks the language filter. -->

for lang in python typescript sql plpgsql tsx matlab go rust ruby c++; do gh search issues --label "good first issue" --state open --limit 100 --json title,repository,labels,assignees,commentsCount,updatedAt,url -- chemistry OR molecule OR quantum OR kanji "language:$lang" "-linked:pr"; done

for lang in python typescript sql plpgsql tsx matlab go rust ruby c++; do gh search issues --label "good first issue" --state open --limit 100 --json title,repository,labels,assignees,commentsCount,updatedAt,url -- math OR "signal processing" OR FFT "language:$lang" "-linked:pr"; done

## Ranking filters

<!-- Conditions and orderings over the free result fields, applied in
the order written. State each so a stranger could apply it and get
your ordering. Example SHAPES (write your own):

- drop any result with an assignee
- drop any result not updated in the last 60 days
- prefer fewer comments over more
-->

- drop any result with an assignee
- drop any result not updated in the last 30 days
- strongly prefer issues where code changes are needed over documentation changes (docs = a `documentation`/`docs` label, or a title starting with "docs")
- prefer issues from repos with a moderate amount of stars (100-1000 stars, from the one star-count lookup per repo)
- prefer fewer comments over more
- tie-break: prefer the most recently updated
- keep at most one issue per repo (its highest-ranked one)

## How many to grade

Grade the top **5** ranked results per scan.

<!-- Five is the default because grading is the only stage that costs
money: about $0.20 per candidate, so a scan is about $1, and you can
iterate the strategy several times for less than one full regression
run. You need one good issue, not ten. Raising this number is
allowed, but it is a decision you state here in a sentence, with the
cost you are accepting; it is not a number you bump because a scan
disappointed you once. -->
