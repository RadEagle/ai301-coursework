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

To ensure a stranger can reproduce the bug, the comment needs to mention the version the bug is reproduced on.

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
