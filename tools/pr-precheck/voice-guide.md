# Voice guide: how I talk upstream

<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2; paste your filled week-2 voice-guide.md here, whole. It is not
re-authored and it is not graded as new work this week.

Then reread it with the plan comment in mind. Your claim and repro
comments promised and reported; a plan comment commits you to an
approach in front of the people who maintain the code. If your rules
do not cover that register (for example: how you state an approach you
are not certain of, or how you respond when a maintainer already
suggested a direction), extend the guide with what it needs. Extending
is allowed and encouraged; starting over is not required.

Live mode reads this file before your plan comment goes out and
reports any rule your draft breaks. Eval mode ignores it entirely,
because your voice is yours and carries no gold labels.
-->

## Who I am in threads

<!-- Paste your week-2 section here. -->

I am a professional software engineer who has experience in Python, TypeScript, React, PostgreSQL, and FastAPI. Looking to break into SQLAlchemy as it is compatible with Python and eliminates the labor work from migrating SQL tables.

## Rules I write by

<!-- Paste your week-2 rules here, wrong/right pairs and all. Add any
rule the plan-comment register needs that your week-2 comments did
not. -->

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

<!-- Paste your week-2 list here; extend it if planning tempts you
toward new ones (overpromised timelines are the classic). -->

- Promises I cannot keep
- Comments that come off as pretentious
- Comments that come off as condescending
- Comments that are dishonest
