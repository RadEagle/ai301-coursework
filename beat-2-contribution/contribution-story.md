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
**Pull Request:** [GitHub PR link, once opened]

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

**Unit 6: Voice Guard and Memory File**

For the voice guard, nothing broke. I know this because I tested my draft claim comment on the voice guard and it told me it is ready to post.

For the repo-memory file, nothing broke there as well. I ran the scoped orientation command regarding the issue and provided me with useful information I can put into the template. There are no instructions revolving around commits, branches, and AI policy.

**Unit 7: [one line on the tool work]**

[2-4 sentences: the ship-gate and your gate manifest. What it produced
on your real branch, what fought you, what changed because of it.]

**Unit 8: [one line on the tool work]**

[2-4 sentences: the PR-monitor and your playbook. What it read, what it
drafted, what you did with the draft.]

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

[What a stranger would need to stand this up: your operating system,
the relevant versions (language, runtime, package manager, the project
itself), and how you set the project up. Then the challenges you faced
and how you solved them, or that none came up.]

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

1. Construct a list of panes that are **visible** and **not floating**, listed in the following order:
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

**Test Plan**

1. Cycle normally with `F6`
    1. Verify that you see the molecules list visible and not layers.
    2. Click on the title bar.
    3. Hit `F6`
    4. Hit the left and right arrow keys
    5. See that the molecule rotates
    6. Hit `F6` again
    7. See that the focus switches from the 3D view to the tools pane, and then display types, etc.
    8. Repeat the same steps with the layers pane visible.
2. Cycle backwards normally with `Shift + F6`
    1. Verify that you see the molecules list visible and not layers.
    2. Click on the title bar.
    3. Hit `Shift + F6`
    4. Hit the left and right arrow keys
    5. See that the molecule rotates
    6. Hit `Shift + F6` again
    7. See that the focus switches from the 3D view to the molecules list, and then display type settings, etc.
    8. Repeat the same steps with the layers pane visible.

**AI Use**
The new code will be LLM generated according to the plan I wrote above, but I will review it line-by-line before opening a pull request.

**Toolkit**

- Tool: plan-check
- What it produced: reject due to unanswered questions, lack of a test plan, and lack of an AI line. Lots of rubric gaps that unit 3 did not account for, including evidence guide comment file name, ambiguity of "Plan Steps", lack of a repro comment (since CodePath told me not to post the repro comment into the issue thread), procedure missing `scope.md`, and dealing with unanswered questions.
- Difficulties: Misordered steps. This tool is checked in step 6, but needs test plan, which is filled in step 8. Complains about whether floating docks should be included whilst cycling focus.
- What changed: Moved the Z-Matrix Editor to out of scope, added a test plan, an AI line. Updated `references/evidence-guide.md, procedure.md, and rubric.md` and added `check-note.md` to document changes. Found out that floating docks aren't feasible for the visible panes in question, so added a condition that the panes must not be floating under Proposed Solution Step 1.

---

## Testing Strategy

[What observable checks prove the fix: your reproduction steps re-run
against the built change (before and after), and the repo's own test
suite or checks with the outcome shown. "Tests pass" with nothing
observable named is not a strategy.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Implementation Notes

[A running log, added to as you work. Date each entry. What you
built, decisions you made when you made them, wrong turns included.]

**[Date]**

[Entry]

**[Date]**

[Entry]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Pull Request

**PR Link:** [GitHub PR URL when opened]

**PR Description:** [what the PR says; much of the content above
adapts into it]

**Maintainer Feedback:**

- [Date]: [feedback received, or "none yet"; silence is a normal
  state and costs you nothing]
- [Date]: [how you addressed it]

**Status:** [Awaiting review / Iterating / Merged / Closed. The
status is a fact you record, never a grade: the PR is graded as
opened.]

**Toolkit**

- Tool:
- What it produced:
- Difficulties:
- What changed:

---

## Learnings and Reflections

**Technical Skills Gained**

[What you learned technically, named concretely.]

**Challenges Overcome**

[What was hard and how you solved it; point at the real events, the
Toolkit blocks above are full of them.]

**What I'd Do Differently Next Time**

[Reflection on your process.]

---

## Resources Used

[What actually helped, not a reading list. List things this story
already shows you using: the doc you followed to set the environment
up, the thread that explained the bug, the person who answered you.
One real entry beats ten plausible ones.]

- [Link to documentation that helped]
- [Discussion, issue, or post that helped]
