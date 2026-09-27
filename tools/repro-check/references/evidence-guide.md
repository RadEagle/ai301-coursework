# Evidence guide: where proof lives in a reproduction package

Every rubric check needs an evidence source. This guide maps the our criterion families to concrete places you can look: on github.com when you are sizing up a live comment by hand, and in the snapshot bundle when you are in eval mode. It closes with one repo-level surface the four families do not cover: the contribution policy. If a signal is not listed here, name your own source in the rubric; just make it somewhere a grader can actually look.

## Environment


| Signal               | On github.com                                                                                                                                                                                                                                                                              | In the eval bundle                                                                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Claim environment    | In the user provided file, under "Claim comment," find environments such as "Linux", "Ubuntu", "Mac", or "Windows".                                                                                                                                                                        | In "Candidate claim comment," find environments such as "Linux", "Ubuntu", "Mac", or "Windows".                                                                          |
| Repro environment    | In the user provided file, under "Repro report," find environments such as "Linux", "Mac", or "Windows".                                                                                                                                                                                   | In "Candidate repro report," find environments such as "Linux", "Mac", or "Windows".                                                                                     |
| Issue environment    | In the provided github link, in the issue body, find environments such as "Linux," "Mac," or "Windows" in the environment line.                                                                                                                                                            | In "Issue," find environments such as "Linux," "Mac," or "Windows" in the environment line.                                                                              |
| Claim version        | In the user provided file, under "Claim comment," find the release version in the environment line.                                                                                                                                                                                        | In "Candidate claim comment," find the release version in the environment line.                                                                                          |
| Repro version        | In the user provided file, under "Repro report," find the release version in the environment line.                                                                                                                                                                                         | In "Candidate repro report," find the release version in the environment line.                                                                                           |
| Issue version        | In the provided github link, in the issue body, find the release version in the environment line.                                                                                                                                                                                          | In "Issue," find the release version in the environment line.                                                                                                            |
| Release version      | In the main repo of the provided github link, in the right sidebar, find the release version under "Releases".                                                                                                                                                                             | In "Repo facts," find the release version in the "latest release" line.                                                                                                  |
| Deviation callout    | In the user provided file, under either "Claim comment" or "Repro report," look in the main body to see if there are any callouts that the version differs from the issue version. It is also a callout if the user explicitly notes that no release version nor issue version is present. | In either "Candidate claim comment" or "Candidate repro report", look in the main body to see if there are any callouts that the version differs from the issue version. |
| Private repo callout | In the user provided file, under "Repro report," find any mentions that a private report is used.                                                                                                                                                                                          | In "Candidate repro report," find any mentions that a private report is used.                                                                                            |




## Steps


| Signal                  | On github.com                                                                                                                                            | In the eval bundle                                                                                                                   |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Reproduction steps      | In the user provided file, under "Repro report," the steps could be within plain text, under the "steps" line, or inside a code block.                   | In "Candidate repro report," the steps could be within plain text, under the "steps" line, or inside a code block.                   |
| Issue steps             | In the provided github link, in the issue body, the steps that can either be in plain text, under the "steps" line, or inside a code block.              | In "Issue," read the general text. The steps can either be in plain text, under the "steps" line, or inside a code block.            |
| Can't reproduce callout | In the user provided file, under "Repro report," find a sentence where the user calls out that they can't reproduce the behavior described in the issue. | In "Candidate repro report," find a sentence where the user calls out that they can't reproduce the behavior described in the issue. |




## Behavior shown


| Signal                | On github.com                                                                | In the eval bundle                                       |
| --------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------- |
| Expected output       | In the user provided file, under "Repro report," look at the "Expected" line | In "Candidate repro report," look at the "Expected" line |
| Actual output         | In the user provided file, under "Repro report," look at the "Actual" line   | In "Candidate repro report," look at the "Actual" line   |
| Issue expected output | In the provided github link, in the issue body, see "Expected" result        | In "Issue," see "Expected" result                        |
| Issue actual output   | In the provided github link, in the issue body, see "Actual" result          | In "Issue," see "Actual" result                          |




## Honesty


| Signal              | On github.com                                                                                                                           | In the eval bundle                                                                                                  |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Guaranteed timeline | In the user provided file, under "Claim comment," look for specific time ranges, like "tomorrow", "2 days", "1 week", "next week", etc. | In "Candidate Claim Comment," look for specific time ranges, like "tomorrow", "2 days", "1 week", "next week", etc. |




## Comms


| Signal              | On github.com                                                                                                                               | In the eval bundle                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Contribution policy | CONTRIBUTING.md in the repo root or .github/, and any contributor docs it links out to; the policy often hides one click away from the repo | the "contribution policy" line under Repo facts                                |
| Claim AI disclosure | In the user provided file, under "Claim comment," find a sentence that explicitly calls out AI use                                          | In "Candidate claim comment," find a sentence that explicitly calls out AI use |


