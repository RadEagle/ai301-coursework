# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

[Your GitHub username, exactly as it appears on your profile — no `@`, no profile URL. Your
comments upstream are identified by this name.]

RadEagle

---

## Posted upstream

**Claim comment**

[Link to the comment where you claimed the issue. Use the comment's own permalink, not the
issue page on its own. **Then paste the text of that comment underneath the link** — the
pasted text is what this field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61#issuecomment-5851281081

Going ahead and claiming this issue. The issue does not name the version affected nor does it have a release version so I will assume it is affecting the latest commit. It seems I need to edit `api/routes/health.py` so that textual SQL is wrapped in `sqlalchemy.text()`. Will try to reproduce the issue and write a report on it whenever I have the chance.

**Reproduction comment**

[Link to the comment where you posted your reproduction. It must record the environment
(OS, relevant versions, code state), steps a stranger could follow, and what you observed.
**Then paste the text of that comment underneath the link** — the pasted text is what this
field is graded on, so copy across what you actually posted.]

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61#issuecomment-5851955062

I was able to reproduce this issue in the latest commit (f89c06f) in Windows 11. I've outlined the reproduction steps below.

## Reproduction Steps
1. Fork the repo into your own copy
2. Clone the copy in SSH with `git clone`. 
    * If SSH takes too long, you can also download the repo as a zip file and unzip it into your local filesystem.
3. Open a terminal shell to your cloned repo
4. Follow the rest of the setup instructions as dictated by the README file
    ```bash
    # Configure environment (add your OPENROUTER_API_KEY to .env)
    cp .env.example .env
    
    # Start backing services — must be running before make setup
    docker compose up -d
    
    # Run first-time setup (installs deps, runs migrations, seeds DB, installs frontend)
    make setup
    
    # Start the application
    make run
    ```
5. In another terminal shell, call `GET /health` using a `curl` command. (Note that `localhost` is the same as `0.0.0.0`)
    * `curl http://localhost:8000/health`
6. See the issue reproduced in the artifact below.

## Artifact
In the `GET` request shell:
```bash
PS > curl http://localhost:8000/health
curl : {"detail":{"status":"unhealthy","dependencies":{"postgres":"unhealthy","redis":"unhealthy","vector_db":"healthy"
},"safety_events_last_hour":0,"timestamp":"2026-09-27T01:54:28.769153"}}
At line:1 char:1
+ curl http://localhost:8000/health
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-WebRequest], WebExc
   eption
    + FullyQualifiedErrorId : WebCmdletWebResponseException,Microsoft.PowerShell.Commands.InvokeWebRequestCommand
```

In the uvicorn/vite shell:
```bash
INFO:     Application startup complete.
2026-09-26 18:54:28 [error    ] postgres_health_check_failed   error="Textual SQL expression 'SELECT 1' should be explicitly declared as text('SELECT 1')" request_id=e0d1bb94-b64f-4d44-b0e8-9eefed0f527c
2026-09-26 18:54:29 [error    ] redis_health_check_failed      error="'Settings' object has no attribute 'redis_host'" request_id=e0d1bb94-b64f-4d44-b0e8-9eefed0f527c
2026-09-26 18:54:29 [debug    ] vector_db_health_check_passed  request_id=e0d1bb94-b64f-4d44-b0e8-9eefed0f527c
INFO:     127.0.0.1:53796 - "GET /health HTTP/1.1" 503 Service Unavailable
```

## Behavior
**Expected:** A `GET /health` request does not print an error regarding the SQL expression 'SELECT 1'.
**Actual:** A `GET /health` request returns 503 as the response code and prints an error that the SQL expression `'SELECT 1'` must be wrapped as `text('SELECT 1')`.

## Next Steps
I should be explicit in calling out that fixing this issue alone will not make the `GET /health` request return status code 200, as the other error (the redis error) is noted in [issue #62](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/62).

That being said, I plan to edit `api/routes/health.py` in which `'SELECT 1'` will be wrapped into `sqlalchemy.text('SELECT 1')` to comply with SQLAlchemy 2.x requirements. A fix for this file will be ready whenever I get to it.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

1. 9/26/2026 3:00PM PST - 13/20
2. 9/26/2026 3:28PM PST - 19/20
3. 9/26/2026 3:35PM PST - 20/20

**Package analysis**

[Pick one scored package (`pkg-01` through `pkg-20` — the four `calib-` packages are never
scored). Name it by id, say what your rubric decided and what the gold label said, and
explain why your rubric read it that way.]

pkg-07: My rubric failed this package in the first two runs (for different reasons) and was later accepted on the third run. The gold-label dictates that this package is accepted. The first rubric was a reconnaissance check to see if there were flaws I didn't consider, like how most of the accepted issues didn't list a version nor environment in the claim comment. The second rubric failed this package because the claim comment did not call out that the version mentioned (1.11.7) deviates from both the issue version (1.9.4 and 1.10.0) and the release version (2.3.2). Thankfully, the deviation callout was present in the repro report, so I added a nod to the deviation callout evidence guide to also look for any callouts in "Candidate repro report" and it passed.

**Check rationale**

[Quote one check from the `rubric.md` you uploaded to `tools/repro-check/`, exactly as it reads now.
Then say why it reads that way — what you revised to get there, or what you rejected in
favour of it.]

AI disclosure. "No AI disclosure is present in contribution policy OR AI-assisted coding is welcome in contribution policy OR claim AI disclosure is present"

I started off with two separate checks "AI disclosure is present" and "package discloses AI use" and modified the verdict so it passes as long as it didn't result in AI disclosure being present and the package didn't disclose AI use. These checks were set to "conditional required" to differentiate between "required" and "preferred". However, the rubric guidelines strictly require the weight to be either "required" or "preferred", so to make things simple, I condensed these checks to one check, with an OR statement added into the pass condition. At the time, it was "No AI disclosure is present in contribution policy OR claim AI disclosure is present", which correctly rejected pkg-20, but failed pkg-03. I noticed that pkg-03 has a AI contributing policy, but welcomes AI-assisted coding, so I modified the check to include "AI-assisted coding is welcome" and correctly evaluated the verdicts for both packages.

**Trade-offs**

[Every check gives something up. Any one of these is a complete answer: a package whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

At first, I made the "claim environment present" check required as I thought a good claim comment would mention the environment the user believes they can reproduce the issue in. However, when I ran the rubric against the gold-labels, almost all of the packages that were supposed to be accepted failed because of this check. I investigated those packages where the verdicts disagreed on (e.g., pkg-01,pkg,09 being ran as canaries) and found that a package can still be accepted even though no environment is mentioned in the claim comments. Thus, the simplest way to make those packages agree with the gold-label verdict is to make this check "preferred" so that the verdicts agree.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
