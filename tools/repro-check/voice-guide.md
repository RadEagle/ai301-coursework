# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->

I am a professional software engineer who has experience in Python, TypeScript, React, PostgreSQL, and FastAPI. Looking to break into SQLAlchemy as it is compatible with Python and eliminates the labor work from migrating SQL tables.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

Rule: Name the version

To ensure a stranger can reproduce the bug, the reproduction comment needs to mention the version the bug is reproduced on.

- Wrong: "I can also reproduce this bug."
- Right: "--style is ignored on v1.20.0"

Rule: If different version, be explicit that it has the same behavior

To keep maintainers sane, if a different release exhibits the same behavior, the claim must call out that it is a different version, but the same bug persists.

- Wrong: "Issue: v1.20.0 | I can reproduce this bug at current, v1.21.0"
- Right: "Issue: v1.19.0 | Bug reproduced on 1.21.0. Different, more recent version, but I experience the same bug here as well."

Rule: Call out what files you are going to fix

To be more likely to get the issue assigned, the post should be specific on which files will be updated, usually in the repro report.

- Wrong: "A fix will be available soon."
- Right: "Knowing this, I plan to fix `index.css` so a fix should be up whenever it gets done."


## Things I never post

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->

- Promises I cannot keep
- Comments that come off as pretentious
- Comments that come off as condescending
- Comments that are dishonest
- Claiming issues over a stranger

## Upstream: how I talk to maintainers

### Claims I post

<!-- 1-2 rules. What your claim promises and how it sounds: intent,
a concrete first step, a realistic timeframe, in your register. Think
about what you refuse to do too: claiming over a stranger, squatting
silently, promising dates you cannot keep.

#### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

Rule: Give a realistic timeframe

Because this is affecting real GitHub issues, claim comments must adhere to realistic timelines that maintainers can tolerate.

- Wrong: "I should be able to reproduce this within two weeks." (On a straightforward issue)
- Right: "I should be able to reproduce this issue within this week." (On a straightforward issue)

### Questions I ask

<!-- 1-2 rules. What a question of yours must carry before it goes
up: answerable from the maintainer's chair, what you already tried,
one question rather than five. -->

Rule: Keep it to one question.

To keep the maintainer from being overwhelmed, the question comment should not contain many unrelated questions.

- Wrong: "How do I set this up? Is it on Linux or on Mac? How long does the setup take? It's taking me hours!"
- Right: "I got the setup to work from source, but am confused on one part of the issue? Can you expand more on what it means for a section to be displayed?"

Rule: Questions must not be solvable without the maintainer's help

Questions that either I or Claude can solve do no help to the maintainer other than to waste their time. Ensure the user has mentioned they tried everything related to the question before asking said question in GitHub.

- Wrong: "What command should I run to run the build?" (When the command to run build is posted in documentation)
- Right: "I've tried the command to run the build from the documentation `cmake --build ./build` but it doesn't work. I made sure every required library is installed before running the code. Is this command the right one or is there a new command that I should run?"


### Pings I send

<!-- 1 rule is enough. When you nudge and how it sounds: measured
against the repo's own reply rhythm, never your clock, and never
pressure dressed as politeness. -->

Rule: Nudge nicely.

So the maintainer doesn't get ticked off by your urgency, nudges should be polite and remind the maintainer of your presence.

- Wrong: "It's been three days since I've posted my claim comment. Why haven't you responded?"
- Right: "Pinging to let you know about this issue's status in case you haven't seen it yet."

<!--
NO UNIT 2 GUIDE? The frame carries you. Write ALL the sections fresh
in your canonical guide, today: first the three unit 2 sections
listed below, then the Upstream section above. Write every rule as
plain text, outside these comment blocks. It is more writing, and it is
entirely doable; ask a TF if you want a second pair of eyes on your
first rules.

The unit-2 frame, so you do not need the old materials open:

  ## Who I am in threads
    2-3 lines. Who is talking when you comment: your experience level
    stated plainly, what you are doing in this repo, what readers can
    expect from you.

  ## Rules I write by
    3-5 rules, wrong/right pair each, same format as above.

  ## Things I never post
    A short list. Promises you cannot keep, tones you refuse,
    shortcuts you know you reach for when tired.
-->
