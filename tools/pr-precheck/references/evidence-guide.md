# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->

## Plan fidelity (harness category: silent-drift)

<!-- Where the plan states its scope, boundary, and deviation notes,
and where the diff shows what actually changed. What it means for a
diff to match the plan, for an honest deviation to re-tie a mismatch,
and what silent drift looks like in each direction (more than the
plan, or less with no note). The description's fidelity claims read
against the diff live here too: a description claiming more or less
than the diff delivers is silent drift, not a comms problem. -->

| Signal | On github.com | In the eval |
| Diff | Read the diffs made in the branch | In candidate PR, find "Diff" |
| Plan context | In `plan.md` | In plan context, read the whole thing |
| Deviation | In `plan.md`, read any Deviation comments. | In plan context, find any callouts under "Deviations" |

## Test evidence (harness category: not-tested)

<!-- Where the PR shows its proof: the test-evidence section's
before/after against the plan's test plan and the reproduction's own
steps, and the outcome of the repo's own checks or suite. What
decisive looks like (an observable behavior named, the expected-after
stated, the checks' outcome visible) next to "tests pass". -->

| Signal | On github.com | In the eval |
| Test evidence | In `test_evidence.md` | In candidate PR, find "Test evidence" |
| Before output | In `test_evidence.md`, find the output before fix | In Test evidence, find the output before fix. |
| After output | In `test_evidence.md`, find the output after fix | In Test evidence, find the output after fix. |

## Diff quality (harness category: unreviewable)

<!-- Where the change itself lives: the unified diff and the commit
list. What a reviewable change looks like (the fix visible, nothing
unrelated riding along) and the debris tells: debug leftovers, dead
code, commented-out blocks, formatting churn, drive-by edits. -->

| Signal | On github.com | In the eval |
| Debug line | In the diffs made by this branch, find any comments added that mention a debug line. | In diff, find any comments mentioning a debug line. |
| Diff comments | In the diffs made by this branch, find any comments added. | In diff, find any comments |
| Commits | In the branch, read the names of the commits made by this branch. | In candidate PR, find "Commits" |
| Issue | In the linked github issue. | In the "Issue" section, read the whole thing. |

## Standards and comms (harness category: standards-wall)

<!-- Where the repo states its asks (the repo-facts block's PR
template sections, contributing instructions, and stated policy,
including AI-use disclosure) and where the PR honors them: the
stated sections filled with real content, the disclosure present,
explicit maintainer direction in the thread engaged. What compliant
looks like next to boilerplate or a visibly ignored ask. (Whether
the description's claims match the diff is plan fidelity, above.) -->

| Signal | On github.com | In the eval |
| PR template | In the repo, under `.github/PULL_REQUEST_TEMPLATE.md` | The "pull requests" line under Repo facts |
| Candidate PR | In `pr_draft.md` | In Candidate PR, read the whole thing |
| AI contributing | CONTRIBUTING.md in the repo root or .github/, and any contributor docs it links out to; the policy often hides one click away from the repo | The "contribution policy" line under Repo facts |
| AI acknowledgement | In `pr_draft.md`, in the description, find any callouts about AI use. | In the candidate PR, under description, see a line calling out the AI policy |
