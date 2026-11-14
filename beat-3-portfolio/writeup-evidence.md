# Evidence pack: technical writeup on planning the F6 / Shift+F6 feature

Subject: writing the implementation plan for avogadroapp #910 (merged as PR #931).
This is raw material only, not the writeup itself. Excerpts are quoted from the source named in each heading.
All times are Pacific (PDT through 10/31, PST from 11/1), converted from GitHub's and the transcripts' UTC timestamps.

Links
- Issue: https://github.com/OpenChemistry/avogadroapp/issues/910
- PR: https://github.com/OpenChemistry/avogadroapp/pull/931
- Plan as written: `beat-2-contribution/contribution-story.md` → "Solution Approach" (lines 217–324); final copy in the avogadroapp clone at `plan.md`
- Plan-check rubric and change log: `tools/plan-check/rubric.md`, `tools/plan-check/check-notes.md`
- Plan-check transcripts: `~/.claude/projects/-mnt-c-Users-Jonathan-OneDrive-Documents-Coding-Portfolio-CodePath-Open-Chemistry-openchemistry-avogadroapp/` (sessions `14cb6b2a`, `66df2ccd`, `a76de65d`)
- Ship-gate log: `~/.claude/ship-gate/gate-log.md`; ship manifest: `ship-manifest.md` in the avogadroapp clone

---

## 1. Overview

**What the issue asked for** (maintainer ghutchis, opened 10/16 at 5:51 PM):
> - Add two `QShortcut`s in `MainWindow`, next to the Ctrl+Tab molecule shortcuts at `avogadro/mainwindow.cpp:635`.
> - Each moves focus to the next or previous *visible* dock, or the active 3D view, in a fixed order. Skip hidden docks, and give focus to the dock's first focusable child.
> - Make sure F6 isn't already used by a plugin. Search avogadrolibs for `"F6"` and `Qt::Key_F6`.

**The core of your plan** (contribution-story.md, Proposed Solution):
- `F6` → `focusNextPane`, `Shift + F6` → `focusPreviousPane`. The shortcuts sit next to Ctrl+Tab, the functions sit next to `nextMolecule`/`previousMolecule`, and both are declared in `mainwindow.h`.
- Step 1 filter, final wording: panes that are **visible**, **not floating**, **on screen** (not a background tab), and **contain a focusable widget**, sorted top-left-right-bottom, with the 3D view first.
- Backward wrap borrowed from `previousMolecule`: `(index - 1 + n) % n`.
- "I will change nothing else in this repo."
- AI line: "The new code will be LLM generated according to the plan I wrote above, but I will review it line-by-line before opening a pull request."

**How the plan was checked: your plan-check skill**
- It grades the plan and the draft plan comment against the live #910 thread and your repro.
- It uses your rubric: 11 required checks, such as "Steps are unambiguous", "Plan complies with thread" and "Handles unanswered questions".
- Verdict rule: "Accept this package if all required checks pass... Any unclear checks count as a fail."
- **Scale:** 10 graded runs between 10/30 and 11/4, plus one regrade. The first accept came on run 6, and the final accept at 3:35 PM on 11/4.

**Groundwork done before the plan** (issue thread):
- 10/26 10:40 AM: you asked about AI policy. The maintainer replied at 11:53 AM: "Adding shortcuts with an LLM is fine."
- 10/27 3:19 PM: Claude oriented you in `avogadro/` and found no tests in `tests/` that touch shortcuts or focus (session `66df2ccd`).
- 10/30 9:19 AM: you confirmed the feature is missing on v2.1.0 (77e13db) in WSL, found no use of `F6` / `Qt::Key_F6` in avogadrolibs, and asked whether the Z-Matrix Editor is in scope.

**Final footprint** (gh pr view): 2 files, +184 / −0 (`mainwindow.cpp` +173, `mainwindow.h` +11), 2 commits on 11/5 at 2:30 PM.

---

## 2. What happened

### Timeline

| Date and time | Event | Source |
|---|---|---|
| 10/16 5:51 PM | Issue opened with a "What to change" list | issue #910 |
| 10/26 10:40 AM | Claim comment and AI-policy question; maintainer answers at 11:53 AM | issue thread |
| 10/27 3:19 PM | Claude orients you in `avogadro/`; no tests for shortcuts or focus | session `66df2ccd` |
| 10/30 9:19 AM | Repro confirmed, F6 free, Z-Matrix question posted | issue thread |
| 10/30 3:08 PM | Plan-check run 1: reject | session `14cb6b2a` |
| 11/4 10:20–10:50 AM | Plan-check runs 2–7: 4 rejects, then 2 accepts | session `14cb6b2a` |
| 11/4 11:04–11:07 AM | Hidden-tab and empty-pane bugs; plan revised, graded (run 8) and fixed in one turn | session `66df2ccd` |
| 11/4 11:40 AM | You answer your own Z-Matrix question (it lives in a plugin, so out of scope); maintainer replies at 11:47 AM: "I think it's a good start." | issue thread |
| 11/4 3:26–3:35 PM | Reordered-pane test; plan-check runs 9, 9b, 10 (reject, reject, accept); rubric changed at 3:34 PM | session `a76de65d` |
| 11/5 9:04 AM | Plan changed to put the top dock first, to match Tab (`plan.md` last modified) | session `a76de65d` |
| 11/5 11:36 AM | `ship-manifest.md` last modified | avogadroapp clone |
| 11/5 2:30 PM | Two commits: `9785c3d` (shortcuts) and `4ff3030` (top/left/right/bottom order) | `git log` |
| 11/6 3:07–3:59 PM | Ship-gate runs; "deviation noted [pass]" | gate-log.md |
| 11/6 4:04 PM | PR opened; the plan is pasted into the PR description | PR #931 |
| 11/10 8:05 PM | Approved: "Sure, seems like a reasonable way to do it." | PR review |
| 11/11 10:12 AM | Merged | PR #931 |

### Every plan-check run

| # | Session | Time | Verdict | What decided it |
|---|---|---|---|---|
| 1 | `14cb6b2a` | 10/30 3:08 PM | **reject** | 3 fails + 1 unclear: Z-Matrix "(if in-scope)" left open, no test plan, no AI line in the plan comment; "Expected outcome" unclear |
| 2 | `14cb6b2a` | 11/4 10:20 AM | **reject** | 8/11 pass. Test 2 (Shift+F6) says "Hit `F6`"; test 4 expects floating docks skipped, which the plan never says; no AI line in the comment |
| 3 | `14cb6b2a` | 11/4 10:28 AM | **reject** | 10/11. Test 3 expects a "collapsed" pane skipped, but step 1 only filters on visibility |
| 4 | `14cb6b2a` | 11/4 10:30 AM | **reject** | 10/11. Same collapsed-pane contradiction |
| 5 | `14cb6b2a` | 11/4 10:32 AM | **reject** | 10/11. Same, plus the new test text says `Ctrl+Tab` (the *next molecule* shortcut) where you meant `Tab` |
| 6 | `14cb6b2a` | 11/4 10:44 AM | **accept** | 11/11, but only because **tests 3 and 4 were deleted** |
| 7 | `14cb6b2a` | 11/4 10:50 AM | **accept** | 11/11. "Not floating" added back to step 1 |
| 8 | `66df2ccd` | 11/4 11:07 AM | **accept** | 11/11. Plan updated for background tabs and empty panes after the build bug |
| 9 | `a76de65d` | 11/4 3:26 PM | **reject** | 9/11. Test 4 (reordered panes) contradicts step 1's fixed order; also failed "Plan complies with thread" on the issue's "in a fixed order" |
| 9b | `a76de65d` | 11/4 3:28 PM | **reject** (regrade) | After you pushed back, "Plan complies with thread" became a pass; "Steps are unambiguous" still failed |
| 10 | `a76de65d` | 11/4 3:35 PM | **accept** | 11/11. Step 1 now sorts "by dock area, then top-to-bottom, then left-to-right" |

Pattern: every reject after run 1 came from the plan contradicting its own tests, never from the diagnosis or the scope.

### Revision 1: from a first draft to a buildable plan (runs 1–5, 10/30 to 11/4 10:32 AM)

Run 1's verdict:
> **Verdict: reject (hold).** Four required checks fail or are unclear. All of them can be fixed in the drafts.
> | Test plan is specific | fail | There's no test plan. "I will not add tests unless directed" gives no manual check either...

Your Toolkit note: "reject due to unanswered questions, lack of a test plan, and lack of an AI line."
- Fix: Z-Matrix Editor moved out of scope; test plan and AI line added.

Run 1 also listed gaps in the tool itself:
> The evidence guide puts the plan comment in `comment.md`, but your file is `plan-comment.md`... The procedure never says to check `scope.md` rules... The rubric doesn't say how to treat a plan that depends on an unanswered question on the thread.

These became the 11/4 entries in `check-notes.md`: the new check "Handles unanswered questions", "Plan Steps" renamed "Test Steps", and `scope.md` read first. You logged one more problem with the tool: "Misordered steps. This tool is checked in step 6, but needs test plan, which is filled in step 8."

Runs 2–5 rejected tests that contradicted the plan:
- Shift+F6 steps that said to press F6.
- A "collapsed" pane the plan never filtered out.
- `Ctrl+Tab` written where you meant `Tab`.

Run 3 also corrected one of the tool's own earlier grades:
> **Correction to my earlier runs:** I graded "Comments follow AI policy" as a fail twice... The AI Usage section in avogadrolibs' CONTRIBUTING.md (levels 0–1) is about code, not comments, so that branch passes.

### Where "not floating" came from (runs 6–7, 11/4 10:44–10:50 AM)

Run 6 accepted only after tests 3 and 4 were deleted. The tool flagged this itself:
> No check reads the implementation steps on their own. The floating and collapsed-pane questions only came up because tests exposed them, and dropping the tests made them disappear from the grade.

At 10:45–10:47 AM, you said panes can't float, and Claude disagreed:
> You: "I tested the app and the panes can't be in floating docks in the first place"
> Claude: "...the code says they can... Qt's default makes every `QDockWidget` floatable... You're testing under WSL. WSLg's window handling is known to break dock dragging and floating."
> Claude, on Tab: "Tab can't move focus into a floating dock in Qt... My recommendation: Skip floating docks, the same way Tab does."

Run 7 accepted with "visible **and not floating**" in step 1. Your Implementation Notes, 11/4: "This isn't possible in at least WSL, but it might be possible in Windows or Mac, so I had Claude add in that check just in case."

### Revision 2: the first build cycled to panes you couldn't use (run 8, 11/4 11:04–11:07 AM)

Your prompt:
> "the fix mostly works, however, it cycled focus to panes with no focusable elements, like layers and display type settings... before applying the fix, tell me where to update plan.md first, run the plan-check, and then actually apply the fix"

What you wrote under Deviations:
> Layers, while tabbed behind Files. Qt does not hide a background dock tab; it moves it off screen, so `isVisible()` stays true. The fix checks that the dock's `visibleRegion()` is not empty instead.
> Display Type Settings, before a display type is selected ... The fix skips any pane without a visible, enabled widget that accepts Tab focus.

In one turn, Claude edited `plan.md`, accepted it with plan-check, and wrote the code. The merged code:
```cpp
// A tabified dock that isn't the current tab is moved off screen rather
// than hidden, so isVisible() is still true: check what is actually shown
if (dock->visibleRegion().isEmpty())
  continue;
```

### Revision 3: fixed order → on-screen order (runs 9, 9b, 10, 11/4 3:26–3:35 PM)

What you wrote under Deviations:
> Previously, the solution involved cycling focus on a fixed pane order, regardless if the panes have been reordered ... I updated the plan so that it now respects the on-screen order.

Run 9 read the maintainer's words as a fixed list:
> Why "Plan complies with thread" fails: ... The issue body, written by ghutchis, asks for the panes "in a fixed order." Test 4 expects on-screen order instead.

Your pushback (3:28 PM):
> "The thread explicitly mentions in a fixed order for the next or previous visible dock or 3D view, not in an arbitrary list mentioned in the issue above."

The tool's regrade (run 9b):
> You're right... "Fixed" most naturally means predictable... I'm changing **Plan complies with thread** to **pass**. ... A step like "if maintainer direction can be read more than one way, grade by the reading the plan states and note the ambiguity" would have prevented this.

At 3:34 PM, you added that rule to `rubric.md` ("If maintainer direction is ambiguous, note the ambiguity"). Run 10 then graded:
> | Plan complies with thread | pass | The issue's "in a fixed order" is ambiguous. Your plan states its reading (on-screen order), and the comment repeats it...

### Revision 4: left-first → top-first, to match Tab (11/4 3:40 PM to 11/5)

Run 10 warned:
> **The code doesn't match the plan yet.** `visiblePanes()` in `mainwindow.cpp` still builds the panes in the hardcoded order with no sort.

The sort was first built Left → Top → Right → Bottom (11/4 3:40 PM). Your Implementation Notes, 11/5:
> I tested the focus cycle with Tab just in case, and it cycled top, left, right, and bottom. So I had Claude fix that implementation so that the F6 focus cycling matches closely with tab cycling.

You changed the plan at 9:04 AM on 11/5 ("updated the pan so it matches the tab behavior of top first, then left"). That became `dockAreaRank()` plus a `geometry()`-based sort.

### Where the AI pushed back (Implementation Notes Toolkit, Learnings)
> Kept implementing what it suggested even when I told it not to. (e.g., cycling focus on hidden panes, floating docks, left dock over top dock first)
> if Claude gives me a choice between deleting tests vs. updating the plan, I should have prioritized updating the plan to cover said checks.

### From plan to merged PR
**What the ship manifest required.** Must pass:
- The build (`cmake --build ../../build`, from `build_linux.yml`).
- clang-format on changed lines (from `clang-format-check.yml`).

Excluded on 11/5, each with a reason:
> **ctest:** "My build follows CLAUDE.local.md, which leaves ENABLE_TESTING OFF, so no tests are built here... no existing test covers QShortcut behavior."
> **macOS, Windows, Windows ARM, Linux ARM64 and Flatpak builds:** "Each needs that OS or a cross toolchain I can't run in WSL... CI runs these builds on the PR."
> **clang-tidy and Codacy:** "Both workflows are `workflow_dispatch` only, so they never run on a pull request."

**Ship-gate compared the diff with the plan** (gate-log.md, 11/6 3:42 PM):
> deviation noted [pass]: Diff touches only mainwindow.cpp/.h as the plan states; visibleRegion filter, focusable filter and dock-order changes are listed under plan Deviations.

**What the PR showed**
- The full plan went into the PR description under "### Plan".
- You flagged the issue's ambiguity in "Notes for Reviewers":
  > In the issue, it mentions that the focus should cycle **in a fixed order**. I'm unsure whether it means the list above or the panes that are on-screen. I decided to go with a traditional approach where the focus cycle closely resembles the tab behavior...
- The maintainer approved that choice (11/10 8:05 PM): "Sure, seems like a reasonable way to do it."
- The test plan became the "After" results table (7 rows, all ✅).

---

## 3. Limitations + What's next

### Limitations of the plan and feature
1. **Hardcoded pane list.** Both functions pass `{ m_toolDock, m_sceneDock, m_viewDock, m_moleculeDock, m_layerDock }`, so docks that live in plugins, like the Z-Matrix Editor, are skipped. The maintainer expects more of them: "We may move more windows into dock widgets like the Z-Matrix editor, but that's something for another day."
2. **The floating-dock rule was never tested.** It rests on Claude's account of Qt (runs 6–7) because docks couldn't float in WSL.
3. **Testing was manual and on one platform.** Testing Strategy: "there are no tests associated with the accessibility shortcuts in this repository." The manifest leaves out ctest and every build outside WSL. CI produced builds for other platforms, but nothing records them being tested by hand.
4. **The plan missed things that only running the app revealed.** Background tabs, empty panes, reordering, and dock-area order all turned up after coding began. Revisions 2–4 came from the build, not from planning.
5. **"Fixed order" is still your reading of the issue.** You settled it in the rubric and in a reviewer note, not with a question on the thread.
6. **The plan comment plan-check accepted was never posted.** `plan-comment.md` (last modified 11/4 3:31 PM) says focus "will be cycled according to the on-screen order", but it isn't on #910. Your 11/4 comment said the plan would go in the PR instead. So the maintainer first saw the order choice in the PR, after the build.
7. **Waiting on questions.** The Z-Matrix question sat from 10/30 to 11/4, and you answered it yourself. Learnings: "I should have run it through Claude to see if said question was answerable locally first."

### Limitations of plan-check and the planning process
8. **Plan-check could be passed by deleting tests.** Run 6 accepted only after tests 3 and 4 were removed, and the tool said so: "dropping the tests made them disappear from the grade."
9. **No check reads the implementation steps.** Runs 2–10 all repeated this gap. Plan problems surfaced only when a test happened to contradict the plan.
10. **Plan-check grades text, not behavior.** Its checks (e.g., "Files in-scope named ... is present") could not have caught the `isVisible()` / background-tab bug, and that bug appeared only after run 7 had accepted the plan.
11. **Grades changed without new evidence.** The AI-policy check flipped from fail to pass when the tool corrected itself in run 3. "Plan complies with thread" flipped after your argument in run 9b.
12. **Run 8 was self-graded.** The same Claude turn edited the plan and accepted it.
13. **The final plan was never re-checked.** The Top-first change (11/5 9:04 AM) came after the last plan-check run. Ship-gate was the only later check, and it confirms deviations are listed, not that the plan holds up.
14. **A known rubric gap stayed open.** The rubric's AI check reads the plan comment, but the evidence guide still looks for AI disclosure in the claim comment or `plan.md`. The tool flagged this in runs 2–10.
15. **Tool upkeep.** The procedure asks for a test plan before the course step that produces one. Updating `rubric.md`, `evidence-guide.md`, `procedure.md` and `SKILL.md` was "twice the amount of work involved" (Learnings).

### What's next
These are suggestions drawn from the evidence above. Keep only the ones you intend to do.
- **Feature:** a follow-up issue for plugin docks like the Z-Matrix Editor (limitation 1); testing floating docks on native Windows or macOS (limitation 2).
- **Add a rubric check that reads the implementation steps** against the tests (limitation 9).
- **Treat a removed test as a deviation**: the plan must say why the case no longer applies (limitation 8).
- **Re-run plan-check after every plan edit.** Ship-gate already fingerprints the plan (`plan c596717bd9e6` in gate-log.md), so it could flag a plan changed since the last accept (limitation 13).
- **Grade in a separate session from the one that edits the plan** (limitation 12).
- **Post the plan comment, or ask on the thread, when the maintainer's direction is ambiguous, before building** (limitations 5–6).
- **Fix the rubric:** align the AI check with the evidence guide, and repair the "Changes in-scope are bounded" row, whose pass condition still has a line break that breaks the table (limitation 14).

---

## Things to check before you cite them
- **Approval date:** 11/10 at 8:05 PM local, which matches your contribution story.
- **The "Files" pane:** `m_moleculeDock` ("Molecules List" in your plan) is titled **"Files"** in the app (`mainwindow.cpp:761`, found during runs 6–7). The plan and PR use two names for one pane.
- **Not counted as plan-check runs:** a 10/02 run on the unit 3 practice issue (transcript gone; `beat-1-sandbox/unit-3/eval-run.txt` holds that eval), and the 11/5–11/6 accepts in session `a76de65d`, which were pr-precheck.
- **Source files in the clone:** `plan.md`, `plan-comment.md`, `pr_draft.md`, `pr_title.md`, `test_evidence.md`, `ship-manifest.md`. `plan.md` is the final plan (last modified 11/5 9:04 AM).
