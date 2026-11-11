# Contribution: Add F6 / Shift+F6 to move keyboard focus between docks and the 3D view

Path: `beat-2-contribution/contribution-story.md`

This file is Assignment 5, and it is graded at the path above; a copy kept anywhere else in
the repository is not read. **Keep every section header below under its exact name** — the
format criteria grade exactly that. Your course repo link is the whole submission: no tool
files and no evidence uploads are part of Assignment 5.

**Contribution Number:** [1]
**Student:** Jonathan Chau
**GitHub Username:** RadEagle
**Issue:** https://github.com/OpenChemistry/avogadroapp/issues/910
**Pull Request:** https://github.com/OpenChemistry/avogadroapp/pull/931

One repository, built across units 5 to 8, telling the whole story of your real
contribution. Fill it as you work, not at the end — the sections below ask for evidence that
is far easier to write down as it happens than to reconstruct in the last weekend.

Contribution Number stays `[1]` unless you make more than one contribution this term; it
just numbers them.

---

## Toolkit

Every story section below, from Why I Chose This Issue through Pull
Request, ends with a Toolkit block: which tool did that phase's work
and how you used it, what it produced, what difficulties or
shortcomings it presented, and what you changed or would change
because of them. Together the blocks are the thread the rubric's
Toolkit points read, and they are the raw material for your unit-9
portfolio, so keep them current as you work rather than
reconstructing them later.

A Toolkit block looks like this (copy it into each story section and
fill it there):

```text
**Toolkit**

- Tool: [which tool did this phase's work, and how you used it]
- What it produced: [described in a sentence or a short excerpt]
- Difficulties: [what fought you or fell short, or "none met"]
- What changed: [the patch, revision, or workaround, what you would
  update, or "nothing"]
```

This section also keeps one short dated entry per week of tool work,
starting below: what you built or changed that week, what broke, and
what you changed because of it. The blocks tell the story where it
happened; these entries are the toolkit's own timeline.

All four entries are graded. Keep every heading below, and fill each
one in the week it belongs to.

**Unit 5: Scouting for Issues**

This unit, I built an AI agent skill that scouts issues for me using GitHub search filters. Unfortunately, due to the poor formatting of the fit profile, Claude complained and had to assume a few filters, such as narrowing the language down to Python and prioritizing the search over the fit profile (e.g., I forgot to put "Chemistry" and "Quantum" into the fit profile so claude had to infer from the query from the search strategy). So, I made sure the fit profile is updated and split the queries into multiple queries, one per language.

**Toolkit**

- Tool: issue-scout (rubric kept consistent for simplicity. search strategy involved encompassing multiple languages and interests, with one interest added should the issues that pull up are unsatisfactory.)
- What it produced: The scan told me this issue is a good fit as I want to improve in C++ while also working around a chemistry software. Its verdict is "accept" and labeled its difficulty as "straightforward" because it names the file to fix directly.
- Difficulties: kept grading issues that are either rejected, ambitious, poor fit, and from repos with less than a hundred stars.
- What changed: Ended up letting Claude make loops on search queries to simplify search, and adjusted the ranking filter to what actually works, like a moderate amount of stars, actual code issues over documentation, and prefer at most one issue per repo.

**Unit 6: Voice Guard and Memory File**

For the voice guard, nothing broke. I know this because I tested my draft claim comment on the voice guard and it told me it is ready to post.

For the repo-memory file, nothing broke there as well. I ran the scoped orientation command regarding the issue and provided me with useful information I can put into the template. There are no instructions revolving around commits, branches, and AI policy.

**Toolkit**

- Tool: voice-guard
- What it produced: Draft claim comment passes voice guard checks
- Difficulties: none met
- What changed: nothing

**Toolkit**

- Tool: orientation Command for memory file
- What it produced: Successful results, nothing is wrong
- Difficulties: none met
- What changed: nothing

**Unit 7: Ship-gate and Gate manifest**

The ship-gate produced positive results for both the build and the clang-format check. It also ran my draft against my rubric and passed it. However, because it couldn't locate the pull request template (named `.github/PULL_REQUEST_TEMPLATE` rather than `.github/PULL_REQUEST_TEMPLATE.md`), it labelled the template as noise and suggested that I delete it. It also cannot check if the commits are signed under my name, even though I already modified the author from my username to my full name under Claude's guidance. So as a result, I followed Claude to ensure the pull request template is present and checked to make sure the commits are signed under my full name.

**Toolkit**

- Tool: ship-gate
- What it produced: Passes on both checks (build and clang-format). Also marked my PR draft as accept against my rubric, ran it against my voice guide, and offered suggestions, like clarifying AI policy.
- Difficulties: Doesn't read `.github/PULL_REQUEST_TEMPLATE`, so it thought no pull request template existed. Also suggested deleting the pull request template itself (the Developer Certificate of Origin). Cannot check if the commits are signed off with my full name although Claude Code did. Complained about the title being there as well as the Shift+F6 test not being present.
- What changed: Removed title and moved it into `pr_title.md`, added `Shift+F6` tests. Pasted checks section. Kept the DCO since Claude Code mentions it is worth keeping.

**Unit 8: PR monitor**

Since I just opened my PR, the PR monitor drafted a suggestion that I wait before nudging the maintainer to review my PR. I set the time to 3 days because most issues not by the maintainer nor the bot are replied within a day. Since it is a wait note, I chose not to post it and put it in my log at the moment. The log is located at `pr-monitor-result.md`

**Toolkit**

- Tool: PR monitor
- What it produced: A wait note in the form of a polite nudge.
- Difficulties: none met
- What changed: nothing

---

## Why I Chose This Issue

I chose this issue because it comes from a repository that revolves around the field of chemistry while also being a straightforward issue to resolve. I ran this issue through my issue-scout skill and it came back as "accept" with a difficulty of "straightforward". Even though the actual issue isn't related to Chemistry, having this be my first open-source issue will help build rapport amongst the maintainers of this repo. The scout didn't do half bad, to be fair. It helped assess the scope of the issues it ranked, even though it had no control over the top 5 issues selected for the agent. Many times, it kept scoring four issues from the same repository with 3 stars.

As for searching for the issue itself, it was a migraine to go through. I initially had ten search queries, one per language. That meant if I wanted to add in another field of interest, like Japanese, then I have to go through all 10 queries and update them with 1 word each. Still, none of the issues were of the right scope, and some of them were even rejected by the issue scout, largely because the ranking filters didn't work as expected. I updated the rankings, but still no issues that satisfy what I wanted to do. I eventually gave up and handed my search queries to Claude to make searching simpler, as it added a python loop to iterate through each language in two queries intead of 10. Thankfully, I found an issue where my issue-scout accepted it and ranked it as straightforward, rather than ambitious, even though it is an enhancement.


Link to claim comment: https://github.com/OpenChemistry/avogadroapp/issues/910#issuecomment-6423134887


**Toolkit**

- Tool: issue-scout (rubric kept consistent for simplicity. search strategy involved encompassing multiple languages and interests, with one interest added should the issues that pull up are unsatisfactory.)
- What it produced: The scan told me this issue is a good fit as I want to improve in C++ while also working around a chemistry software. Its verdict is "accept" and labeled its difficulty as "straightforward" because it names the file to fix directly.
- Difficulties: kept grading issues that are either rejected, ambitious, poor fit, and from repos with less than a hundred stars.
- What changed: Ended up letting Claude make loops on search queries to simplify search, and adjusted the ranking filter to what actually works, like a moderate amount of stars, actual code issues over documentation, and prefer at most one issue per repo.

---

## Understanding the Issue

**Problem Description**

The `avogadroapp` is missing accessibility features that allow keyboard users to quickly cycle focus between visible panes and the 3D view.

**Expected Behavior**

A shortcut exists that cycles through visible docks and 3D view.

**Current Behavior**

No shortcut exists that achieves expected behavior.

**Affected Components**

Two files inside the `avogadro` folder are affected:

* `mainwindow.cpp`
* `mainwindow.h`

**Toolkit**

- Tool: repro-check
- What it produced: No issues, ready to post
- Difficulties: None
- What changed: None

---

## Reproduction Process

**Environment Setup**

I'm using the latest version (2.1.0, 77e13db) on Windows (WSL). I followed the setup instructions according to its [development guide](https://avogadro.cc/develop/build.html#develop-build) using a Cursor terminal and had its AI help me install the missing libraries and submodules as I haven't contributed in C++ before. The only challenge with setting this up is that the build took hours to finish, though after that any subsequent updates to the core libraries takes about 10 minutes to build. During the build I spent my time working on other tasks and catching up on my free time while waiting for the build to finish.

### Setup Instructions
1. Fork the upstream `avogadroapp` repo into your own repo
2. Clone the repo according to the instructions outlined [here](https://avogadro.cc/develop/build.html#manual-clone)
    ```bash
    git clone https://github.com/OpenChemistry/openchemistry.git
    cd openchemistry
    git clone https://github.com/OpenChemistry/avogadrolibs.git
    git clone https://github.com/[YOUR_GITHUB_USERNAME]/avogadroapp.git
    git -C avogadroapp checkout 2.1.0
    git -C avogadrolibs checkout 2.1.0
    ```
3. Follow the setup instructions outlined [here](https://avogadro.cc/develop/build.html#building-avogadro)
    * Perform these commands in the directory named `openchemistry`
    ```bash
    git submodule update --init thirdparty/jkqtplotter
    git submodule update --init fragments molecules crystals avogadro-i18n
    ```

    * Perform these commands in the parent directory of `openchemistry`
    ```
    sudo apt update
    sudo apt install qt6-base-dev qt6-svg-dev libgl1-mesa-dev
    sudo apt install libxml2-dev
    sudo apt install libglu1-mesa-dev
    cmake -DQT_VERSION=6 -DBUILD_MOLEQUEUE=OFF -S ./openchemistry -B ./build
    cmake --build ./build
    ./build/prefix/bin/avogadro2
    ```

**Steps to Reproduce**

1. With the app opened, click on the black display box.
2. Try to cycle focus through visible docks using any key (e.g., F6 and Shift+F6)
    * Because this feature is not implemented yet, there is no way to achieve the desired behavior.

**Reproduction Evidence**

- **Commit showing reproduction:** https://github.com/RadEagle/avogadroapp/commit/77e13db9f6263cf86768169298812cb8c3674d1f
- **Screenshots/logs:** N/A, this is a feature request
- **My findings:** During reproduction, I ensured the shortcut to cycle focus through visible panes doesn't exist and the F6 key didn't do anything as well. While playing around the app, I discovered there is an extra pane worth mentioning, the Z-Matrix Editor, that is hidden by default. I'm asking the maintainer about whether to include this pane in scope and where to find it.

**Toolkit**

- Tool: repro-check
- What it produced: Claim draft and repro-report both accepted
- Difficulties: Having to thank the maintainer, trimming/re-adding reproduction steps, and GitHub markdown issues
- What changed: Modified opening line to thank maintainer, settled for using upstream repo to reproduce, and settled for using numbers for sub-items over letters.

---

## Solution Approach

**Analysis**

The root cause is that there is no function that allows keyboard users to cycle through the visible panes in the first place.

**Proposed Solution**

The fix approach involves creating two `QShortcut`s in `avogadro/mainwindow.cpp`, `F6` to cycle forward focus across the 3D view and visible panes, and `Shift + F6` to cycle backwards. Each `QShortcut` links to a C++ function, which means I need to also create two functions in `avogadro/mainwindow.cpp` as well as declare them in `avogadro/mainwindow.h`.

These new shortcuts will be linked to their respective new functions named below:

* `F6` -> `focusNextPane`
* `Shift + F6` -> `focusPreviousPane`

Here is how the new function `focusNextPane` will be implemented:

1. Construct a list of panes that are **visible**, **not floating**, **on screen** (not a background tab, e.g. Layers behind Files), and **contain a focusable widget** (e.g. Display Type Settings is empty until a display type is selected). Collect the qualifying docks, and then sort by top-left-right-bottom dock area order. The 3D view stays first. The following list references the panes and where to get them. Other than the 3D view being first, the panes may not necessarily be in order depending on in-screen settings.
    1. 3D view: `m_multiViewWidget->activeWidget()`
    2. Tool Settings: `m_toolDock`
    3. Display Types: `m_sceneDock`
    4. Display Type Settings: `m_viewDock`
    5. Molecules List: `m_moleculeDock`
    6. Layers: `m_layerDock`
2. If there is only 1 visible pane, return
3. Find which pane in the visible list contains `QApplication::focusWidget()`
4. If there is no pane that has the focus widget, default focus to the 3D view
5. Otherwise, do the following
    1. Get the index of the selected pane
    2. `setFocus()` on the next pane's first focusable child

The function `focusPreviousPane` will be implemented similarly, except we will cycle through the visible panes similar to what `previousMolecule` did. That is, after getting the index, decrement by one, increment by the number of visible panes, then take the remainder after dividing by said number of visible panes.

I will change nothing else in this repo.

**Implementation Plan**

1. Add two `QShortcuts` for `F6` and `Shift + F6` to live next to the `Ctrl + Tab` shortcuts at `avogadro/mainwindow.cpp:635`
2. Create two functions, `focusNextPane` and `focusPreviousPane`, according to the Proposed Solution above. They should live near where `nextMolecule` and `previousMolecule` are implemented.
3. Declare these two functions at `avogadro/mainwindow.h`, next to where `nextMolecule` and `previousMolecule` are declared.

Note: There are no tests associated with the `QShortcut`s directly, so I will not add tests unless directed as it solves an accessibility issue.


**Deviations**

Cycling focus to the Z-Matrix Editor will be out of scope for now because the code lives in a `qtplugin`, not `mainwindow.cpp` where it defines the scope of the issue.

During testing, the first build of `focusNextPane` cycled focus to panes the user could not see or use:

* Layers, while tabbed behind Files. Qt does not hide a background dock tab; it moves it off screen, so `isVisible()` stays true. The fix checks that the dock's `visibleRegion()` is not empty instead.
* Display Type Settings, before a display type is selected. The dock has no focusable widget, so focus landed on the dock itself with no visible indicator. The fix skips any pane without a visible, enabled widget that accepts Tab focus.

Both are filters in step 1 of the Proposed Solution; the files touched and the shortcuts stay the same.

Previously, the solution involved cycling focus on a fixed pane order, regardless if the panes have been reordered, leading to accessibility issues. I updated the plan so that it now respects the on-screen order.

After applying the in-screen order fix, the focus cycles left-top-right-bottom, whereas tab focus goes top-left-right-bottom. The F6 focus cycle should closely mimic that tab behavior.

**Test Plan**

1. Cycle normally with `F6`
    1. Verify that you have the default setup, so that the left pane has tools, display types, display type settings, and molecules list in that order.
    2. Click on the title bar on top of the window.
    3. Hit `F6`
    4. Hit the left and right arrow keys
    5. See that the molecule rotates
    6. Hit `F6` again
    7. See that the focus switches from the 3D view to the tools pane, and then display types, etc.
    8. Repeat the same steps with the layers pane visible.
2. Cycle backwards normally with `Shift + F6`
    1. Verify that you have the default setup, so that the left pane has tools, display types, display type settings, and molecules list in that order.
    2. Click on the title bar on top of the window.
    3. Hit `Shift + F6`
    4. Hit the left and right arrow keys
    5. See that the molecule rotates
    6. Hit `Shift + F6` again
    7. See that the focus switches from the 3D view to the molecules list, and then display type settings, etc.
    8. Repeat the same steps with the layers pane visible.
3. Skip hidden and empty panes
    1. Start with Layers tabbed behind Files, Files selected, and no display type selected.
    2. Hit `F6` repeatedly from the 3D view.
    3. See that focus visits the 3D view, Tool (only if the active tool shows settings), Display Types, and Files only, then wraps to the 3D view. It never lands on Layers or Display Type Settings.
    4. Select the Layers tab and hit `F6` again; see that focus now visits Layers instead of Files.
    5. Click a display type (e.g. Ball and Stick) so its settings appear, and hit `F6` again; see that focus now also visits Display Type Settings.
    6. Repeat with `Shift + F6` and see the same panes visited in reverse order.
4. Focus still cycles from top to bottom on reordered panes.
    1. Reorder the left pane by dragging the Tools Pane to the bottom
    2. Hit `F6` from the 3D view.
    3. The focus should land in Display Types. Tools pane should be the last pane before wrapping back to the 3D view.
    4. Repeat the same but for `Shift + F6`
    5. From the 3D view, the focus should hit the bottom pane, which is the Tools pane.
5. Panes on different docks
    1. Drag the panes so that at least one pane shows up in the top, left, right, and bottom docks.
    2. From the 3D view, hit `F6`
    3. Verify that the focus hits the top dock first, then left, right, bottom, and back to the 3D view.
    4. Hit `Shift + F6`
    5. Now, the focus hits the bottom dock first, then right, left, top, and back to the 3D view.

**AI Use**
The new code will be LLM generated according to the plan I wrote above, but I will review it line-by-line before opening a pull request.

**Toolkit**

- Tool: plan-check
- What it produced: reject due to unanswered questions, lack of a test plan, and lack of an AI line. Lots of rubric gaps that unit 3 did not account for, including evidence guide comment file name, ambiguity of "Plan Steps", lack of a repro comment (since CodePath told me not to post the repro comment into the issue thread), procedure missing `scope.md`, and dealing with unanswered questions.
- Difficulties: Misordered steps. This tool is checked in step 6, but needs test plan, which is filled in step 8. Complains about whether floating docks should be included whilst cycling focus.
- What changed: Moved the Z-Matrix Editor to out of scope, added a test plan, an AI line. Updated `references/evidence-guide.md, procedure.md, and rubric.md` and added `check-note.md` to document changes. Found out that floating docks aren't feasible for the visible panes in question, so added a condition that the panes must not be floating under Proposed Solution Step 1.

---

## Testing Strategy

Since the issue I picked is a feature request for accessibility, there is no way to tell in the terminal if the feature is fixed or not. I will provide video evidence of the behavior before and after to show that the fix works as expected.

In addition, there are no tests associated with the accessibility shortcuts in this repository, so I will be skipping them.

**Toolkit**

- Tool: plan-check
- What it produced: Reject, complained about testing steps being unambiguous, especially regarding step 3 and hidden docks.
- Difficulties: Confusion about keep steps related to floating docks and hidden panes. Initial implementation even led to focus landing on a pane where there are no focusable items (e.g., Display Type Settings when no display type is selected)
- What changed: Modified the plan so that visible docks picked up must be in the main window (not on a floating dock) and have a focusable item.

---

## Implementation Notes

**11/4/26**

Began implementing the fix using Claude Code. Fix is mostly there, but ran into an issue where the focus cycled to panes that were either not visible nor have no focusable items, so I updated the plan and told Claude to improve the implementation based on the updated plan. Now that the updated code is there, I should be able to test the fix.

There's also another issue with cycling focus to panes in their own floating window, but I didn't want that since the normal tab behavior wouldn't cycle through floating docks. This isn't possible in at least WSL, but it might be possible in Windows or Mac, so I had Claude add in that check just in case.

**11/5/26**

I forgot the case when it comes to reordering panes and when I used F6, it cycled from the 3D view to tools, regardless if it's at the top or not. So I updated the plan again so it can factor in pane placement. Claude let me know that panes can be in other docks, not just the left, and ordered it so that it's left, top, right, bottom, with each pane in the dock area go from top to bottom on the left most column first, then the next column and so on. I tested the focus cycle with Tab just in case, and it cycled top, left, right, and bottom. Soi I had Claude fix that implementation so that the F6 focus cycling matches closely with tab cycling. Now the implementation is complete and I can submit the PR.

**Toolkit**

- Tool: Claude
- What it produced: A workable fix, with some bugs initially.
- Difficulties: Kept implementing what it suggested even when I told it not to. (e.g., cycling focus on hidden panes, floating docks, left dock over top dock first)
- What changed: I had to manually tell Claude not to do that and set guardrails myself, and it acted accordingly.

---

## Pull Request

**PR Link:** https://github.com/OpenChemistry/avogadroapp/pull/931

**PR Description:** This pull request resolves issue [#910](https://github.com/OpenChemistry/avogadroapp/issues/910) - Add F6 / Shift+F6 to move keyboard focus between docks and the 3D view, by adding two `QShortcut`s to cycle focus between the 3D view and visible panes.

**Maintainer Feedback:**

- 11/10/2026: maintainer said he can approve the change as is.
- 11/11/2026: merged my changes to main.

**Status:** Merged.

**Toolkit**

- Tool: ship-gate
- What it produced: Passes on both checks (build and clang-format). Also marked my PR draft as accept against my rubric, ran it against my voice guide, and offered suggestions, like clarifying AI policy.
- Difficulties: Doesn't read `.github/PULL_REQUEST_TEMPLATE`, so it thought no pull request template existed. Also suggested deleting the pull request template itself (the Developer Certificate of Origin). Cannot check if the commits are signed off with my full name although Claude Code did. Complained about the title being there as well as the Shift+F6 test not being present.
- What changed: Removed title and moved it into `pr_title.md`, added `Shift+F6` tests. Pasted checks section. Kept the DCO since Claude Code mentions it is worth keeping.

---

## Learnings and Reflections

**Technical Skills Gained**

I learned the following technical skills, listed below:

* C++
    * Qt Functions and Syntax
    * Lambda functions
    * Syntax for calling object/pointer functions
    * Using `geometry()` to specify pane positions within a dock area
    * Comparison functions in C++
    * Using `cmake` to build applications in C++
    * Formatting in `clang-format`
* GitHub
    * Downloading and updating git submodules
    * Changing the author for unpushed commits
    * Excluding local files with `echo [file] >> .git/info/exclude`

**Challenges Overcome**

* Fighting Claude
    * Learning how to fight Claude in general is a big challenge. This came in two separate issues during plan review and implementation, regarding cycling focus through hidden panes and cycling focus through hidden docks. Claude suggested I change the plan or deleted the steps. I deleted the steps thinking that behavior shouldn't be possible. Claude assumed otherwise and implemented so that the focus hit panes that are hidden or have no focusable elements. The same goes for floating docks, even though in WSL it isn't possible. As a result I had to point it out to Claude and suggested I add in more checks to step 1 of the implementation plan.
* Updating the skill package
    * It is already overwhelming that Claude told me to update `rubric.md`, `references/evidence-guide.md`, `procedure.md`, and sometimes `SKILL.md` when I already spent an ample amount of time calibrating the skill to other real examples. I do realize keeping track of my doing is what I'm supposed to do as a software engineer, but it is taxing when you realize that is twice the amount of work involved. Not to mention context switching from actual programming to recalling what I just did. As for now, I have a separate file to log changes as soon as I actually make said change.

**What I'd Do Differently Next Time**

Next time I contribute to open-source, when I have a question, I should have run it through Claude to see if said question was answerable locally first, rather than wait five days for a response. In addition, if Claude gives me a choice between deleting tests vs. updating the plan, I should have prioritized updating the plan to cover said checks. Finally, when it comes to tracking what I have done so far, I'll reserve some space to log any notes in their respective pages so I don't run into friction on opening them up every time.

---

## Resources Used

- Official Build Documentation: https://avogadro.cc/develop/build.html#develop-build
