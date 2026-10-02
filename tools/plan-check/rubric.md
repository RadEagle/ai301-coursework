# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Files in-scope named | Files in-scope | Files in-scope is present | required |
| Out-of-scope called out | Files out-of-scope, Features out-of-scope | Files out-of-scope or features out-of-scope are present | required |
| Expected outcome | Expected outcome | Expected outcome is present | required |
| Changes in-scope are bounded | Issue behavior, expected behavior, actual behavior, proposed changes | 
All of the proposed changes listed contribute to fixing the actual or issue behavior to the expected behavior | required |
| Diagnosis aligns with evidence | Diagnosis, repro evidence | The diagnosis does not contradict with the repro evidence. For example, if the repro evidence rules out a null check issue, but blames the null check, it is not a pass. | required |
| Steps are unambiguous | Plan steps | The steps are confident and can be followed without asking any questions | required |
| Test plan is specific | Test plan, Expected outcome | The test plan should describe the outcome, not something generic like "nothing should be broken" | required |
| Comments follow AI policy | AI Contributing, Plan comment | Either no AI policy on commenting is present or plan comment explicity mentions it is written in their own words or is human-made | required |
| Issue is fixable | Unsolvable comment | No unsolvable comment is present | required |
| Plan complies with thread | Thread highlights, candidate plan | The plan does not ignore the thread highlights made by the maintainer and follows through on what it says. Automatic pass if there are no thread highlights. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Accept this package if all required checks pass.

Preferred checks do not change the verdict.

Any unclear checks count as a fail.