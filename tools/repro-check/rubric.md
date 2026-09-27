# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Reproduction steps present | Reproduction steps | Reproduction steps is present | required |
| Expected result matches | Expected output and Issue expected output | Expected output matches Issue expected output | preferred |
| Actual result matches | Actual output and Issue actual output | Actual output matches issue actual output | preferred |
| Honest cannot reproduce | Can't reproduce callout | Can't reproduce callout is present | preferred |
| Version deviation called out | Issue version, claim version, repro version, release version, deviation callout | Issue and claim version are the same, OR release and claim version are the same, OR issue and repro version are the same, OR release and repro version are the same, OR deviation callout is present | required |
| Arguments and expressions match | Reproduction steps, issue steps | In code blocks, the arguments in the reproduction steps clearly match the arguments in the issue steps | required |
| No guaranteed timeline | Guaranteed timeline | No guaranteed timeline is present | required |
| Claim version present | Claim version | Claim version is present | preferred |
| Claim environment present | Claim environment | Claim environment is present | preferred |
| Repro version present | Repro version | Repro version is present | required |
| Repro environment present | Repro environment | Repro environment is present | required |
| No private repos | Private repo callout | No private repo callout is present | required |
| AI disclosure | Contribution policy and claim AI disclosure | No AI disclosure is present in contribution policy OR AI-assisted coding is welcome in contribution policy OR claim AI disclosure is present | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Accept the package if and only if every required check passes. 
One of the following checks must pass so that the package is accepted
* Actual result matches
* Honest cannot reproduce

Preferred checks never change the verdict. They only decide the ranking of accepted packages. Any unclear checks will count as a fail.