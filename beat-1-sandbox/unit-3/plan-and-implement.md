# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

[Your GitHub username, exactly as it appears on your profile - no @, no
profile URL. Your comment upstream is identified by this name, and it is
the only thing that ties it to you. Several students may plan the same
house issue, so this is what keeps their comments off your score and
yours off theirs.]

RadEagle

**Plan comment**

[Link to the comment where you posted your plan on the issue. Use the comment's own
permalink. **Then paste the text of that comment underneath the link** — the pasted text is
what this field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61#issuecomment-5961543762

Reproduced in the latest commit (f89c06f). The error requires the SQL text to be wrapped in `text()`. The plan is a one-line fix to `api/routes/health.py` described by the error. Once I am able to fix this issue, a pull request will be ready for review.

Note that the fix won't make `/health` return response code 200 until [issue #62](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/62) is also fixed.

---

## Your branch

**Branch**

[The name of the branch you built the change on, exactly as it appears in your fork. The
naming shape is a type prefix, then the issue number, then a short description. **The issue
number in the branch name must be the number of the issue you claimed** — a name carrying
any other number does not satisfy this field.]

fix/61-wrap-sql-in-sqlalchemy-text

**Evidence**

[Your Unit 2 reproduction steps re-run against the built change: the before, then the
after. Paste both, including the commands you ran and their output.]

#### Before fix

Command: `curl http://localhost:8000/health`

Output:
In PowerShell:
```
PS> curl http://localhost:8000/health
curl : {"detail":{"status":"unhealthy","dependencies":{"postgres":"unhealthy","redis":"unhealthy","vector_db":"healthy"
},"safety_events_last_hour":0,"timestamp":"2026-09-27T01:54:28.769153"}}
At line:1 char:1
+ curl http://localhost:8000/health
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-WebRequest], WebExc
   eption
```


In the uvicorn shell:
```
INFO:     Application startup complete.
WARNING:  Invalid HTTP request received.
WARNING:  Invalid HTTP request received.
2026-10-02 14:35:28 [error    ] postgres_health_check_failed   error="Textual SQL expression 'SELECT 1' should be explicitly declared as text('SELECT 1')" request_id=97b2bd72-2600-46b2-9f26-a29fd74f1396
2026-10-02 14:35:30 [error    ] redis_health_check_failed      error="'Settings' object has no attribute 'redis_host'" request_id=97b2bd72-2600-46b2-9f26-a29fd74f1396
2026-10-02 14:35:30 [debug    ] vector_db_health_check_passed  request_id=97b2bd72-2600-46b2-9f26-a29fd74f1396
INFO:     127.0.0.1:37496 - "GET /health HTTP/1.1" 503 Service Unavailable
```

#### After fix

Command: `curl http://localhost:8000/health`

Output:
In PowerShell:
```
PS> curl http://localhost:8000/health
curl : {"detail":{"status":"unhealthy","dependencies":{"postgres":"healthy","redis":"unhealthy","vector_db":"healthy"},
"safety_events_last_hour":0,"timestamp":"2026-10-02T21:36:12.078467"}}
At line:1 char:1
+ curl http://localhost:8000/health
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-WebRequest], WebExc
   eption
    + FullyQualifiedErrorId : WebCmdletWebResponseException,Microsoft.PowerShell.Commands.InvokeWebRequestCommand
```

In the uvicorn shell:
```
INFO:     Application startup complete.
2026-10-02 14:36:12,080 INFO sqlalchemy.engine.Engine BEGIN (implicit)
2026-10-02 14:36:12,080 INFO sqlalchemy.engine.Engine SELECT 1
2026-10-02 14:36:12,080 INFO sqlalchemy.engine.Engine [generated in 0.00010s] ()
2026-10-02 14:36:12 [debug    ] postgres_health_check_passed   request_id=96288047-0314-41db-a594-871433f32972
2026-10-02 14:36:13 [error    ] redis_health_check_failed      error="'Settings' object has no attribute 'redis_host'" request_id=96288047-0314-41db-a594-871433f32972
2026-10-02 14:36:13 [debug    ] vector_db_health_check_passed  request_id=96288047-0314-41db-a594-871433f32972
2026-10-02 14:36:13,299 INFO sqlalchemy.engine.Engine ROLLBACK
INFO:     127.0.0.1:48930 - "GET /health HTTP/1.1" 503 Service Unavailable
```

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

1. 10/02/2026 12:03PM PST - 19/20

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

pkg-14: My rubric decided that was a fail, but the gold label said it was an accept. Looking at the candidate plan, there are steps listed in the test plan presented as a paragraph, and not every detail is clear (behavioral parity, for one). This aligns with the check that failed the rubric, which was "Steps are unambiguous", because the behavioral parity isn't described in a way that is clear to the grader.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/plan-check/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

Plan complies with thread - The plan does not ignore the thread highlights made by the maintainer and follows through on what it says. Automatic pass if there are no thread highlights.

This check came straight from the group activity where our verdict for calib-03 disagreed with the gold-label as the plan ignored guidelines from the thread, only to disagree with the verdict for calib-01 as there are no thread highlights. To ensure the verdicts agree for both packages, I added a statement that the required check automatically passes if there are no thread highlights because if it were to be a preferred check, then there is a chance calib-03 would be wrongly accepted.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

Originally, I ran the evaluation using only the calibration packages as canaries with the check "Files in-scope are bounded", only to have the accepted calib-01 package fail because the files were not mentioned in either the issue nor the repro-evidence. So I had to change the check to "Changes in-scope are bounded" and change the evidence gathered from issue files, repro files, and in-scope files to expected and actual behaviors as well as proposed changes so that the AI agent has an easier time identifying which of the proposed changes is necessary to change the behavior from the current one to the expected one. By replacing one check with another, I got the next set of canaries (half-rubric, half-scope-creep) to pass and met the benchmark when running the full set.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
