# Unit 4 — Test and Submit

Path: `beat-1-sandbox/unit-4/pull-request.md`

Record of the pull request you opened against the Path Review repo, and of the evaluation
runs that produced `eval-run.txt`. This file is graded at the path above; a copy kept
anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your pull request

**Pull request**

[Link to the pull request you opened. It must be the pull request's own page on the Path
Review repo, not your fork's branch page.]

https://github.com/codepath/pathreview-ai301-fa26-s1/pull/156

**Branch**

[The name of the branch the pull request comes from, exactly as it appears in your fork.
The naming shape is a type prefix, then the issue number, then a short description. **The
issue number in the branch name must be the number of the issue the pull request fixes** —
a name carrying any other number does not satisfy this field.]

fix/61-wrap-sql-in-sqlalchemy-text

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

1. 10/11/2026 3:09PM PST - 20/20

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

pkg-01: My verdict agrees with the gold verdict to reject this package because I added a check that says "PR template followed" where the candidate PR structure must follow the pull request template contained in the repo. This package fails because the template requires a checklist (e.g., closes #xxxx) but doesn't mention that item.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/pr-precheck/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

No TODOs - Diff comments do not contain TODOs
Often times, when we're swamped with work, we often add TODOs to our code to remind ourselves what to do. For that same reason, we may end up forgetting to remove the TODO comments before committing the code and making a pull request. I made this check required because we wouldn't want to see a stray TODO line in the main branch of the repo.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

Nothing changed, and here is how I know. When I ran the rubric on the calibration packages the first time, I scored full points. Then I ran the rubric on the eval packages, and got all checks correct. There is no reason to change any checks of the rubric when I got a full 20/20.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/pr-precheck/`.
