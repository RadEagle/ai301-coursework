# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

<!-- Where the plan states its cause, and where the repro evidence
pins down the behavior that cause must explain. What it means for a
diagnosis to follow from the evidence rather than contradict or
ignore it. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Diagnosis | In "Candidate plan", look for the issue in the "Diagnosis" or "Cause" line. | In the working directory's `plan.md`, look for the issue in the "Diagnosis" or "Cause" line. |
| Issue behavior | In "Issue", look for the current behavior. | In the linked issue's body, look for the current behavior. |
| Expected behavior | In "Repro evidence", look for the behavior listed in the "Expected" line. | In the reproduction steps commented in the linked issue, look for the behavior listed in the "Expected" line. |
| Actual behavior | In "Repro evidence", look for the behavior listed in the "Actual" line. | In the reproduction steps commented in the linked issue, look for the behavior listed in the "Actual" line. |

## Scope

<!-- Where the plan bounds itself: the in-scope statement, the
not-in-scope line, the files or areas named. What one bounded change
looks like next to a drive-by rewrite. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Files in-scope | In "Candidate plan", look for any files that will be changed | In the working directory's `plan.md`, look for any files that will be changed |
| Files out-of-scope | In "Candidate plan", look for any files that will not be changed | In the working directory's `plan.md`, look for any files that will not be changed |
| Features out-of-scope | In "Candidate plan", look for any features that will not be changed | In the working directory's `plan.md`, look for any features that will not be changed |

## Executability

<!-- Where the plan says what will actually be done: files or areas,
approach, order of work. What it means for a stranger to be able to
start executing without asking the author anything. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Plan steps | In "Candidate plan", look for a list of instructions on how a stranger can test the fix | In the working directory's `plan.md`, look for a list of instructions on how a stranger can test the fix |
| Issue files | In "Issue", look for any files called out | In the linked issue's body, look for any files called out |
| Repro evidence files | In "Repro evidence", look for any files called out | In the reproduction steps commented in the linked issue, look for any files called out |

## Test plan

<!-- Where the plan says how success will be observed, and how that
maps onto the repro evidence's steps and artifacts. What a decisive
test plan names that a vague one does not. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Test plan | In "Candidate plan", look for a test plan in the "Test" line | In the working directory's `plan.md`, look for a test plan in the "Test" line |
| Expected outcome | In "Candidate plan", look for an outcome described in the "Test" line | In the working directory's `plan.md`, look for an outcome described in the "Test" line |

## Honesty

<!-- Where claims meet uncertainty: risks, unknowns, and deviations.
How to tell stated unknowns from false confidence, and where an
honest mid-build deviation gets recorded. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Deviations | In "Candidate plan", look for a comment where the user scopes down from their original plan, for finds other files they felt necessary to fix. | In the working directory's `plan.md`, look for a comment where the user scopes down from their original plan, for finds other files they felt necessary to fix. |

## Comms

<!-- Where the words meet the thread and the repo: the plan comment
read against the issue's maintainer signals (thread highlights, or
the live thread) and against the repo-facts block's stated templates,
contributing asks, and contribution policy (including AI-use
disclosure requirements). What thread-aware looks like next to
boilerplate. -->

| Signal | In the eval bundle | On github.com |
|---|---|---|
| Contribution policy | the "contribution policy" line under Repo facts                                | CONTRIBUTING.md in the repo root or .github/, and any contributor docs it links out to; the policy often hides one click away from the repo | 
| Claim AI disclosure | In "Candidate claim comment," find a sentence that explicitly calls out AI use | In the user provided file, under "Claim comment," find a sentence that explicitly calls out AI use                                          | 
| Thread highlights | In "Thread Highlights", see comments posted by a collaborator or maintainer | In the linked issue, see comments posted by either the repo owner or the contributor or the maintainer |
| Plan comment | In "Plan comment" | In the working directory's `comment.md` |

