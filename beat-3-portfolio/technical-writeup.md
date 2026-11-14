# Writing a Plan to Implement Accessibility Shortcuts

## Overview
The tool I will talk about is the `plan-check` AI skill. This tool is used to check that your implementation plan is sound before you write your first line of code. I first calibrated its rubric using examples gathered from CodePath, and then applied it to my working plan to implement an accessibility feature. After some back-and-forth discussions, I eventually carried out the plan that got its pull request merged to the main branch on the first round.

## What happened
It all started back in October 2nd, when I read the [eval-package](https://github.com/codepath/ai301-unit3-starter/tree/main/eval/packages) and constructed my `plan-check` tool, including `procedure.md`, `references/evidence-guide.md`, and `rubric.md`. I then ran this tool against the eval-package and got 19/20 verdicts correct. [1](https://github.com/RadEagle/ai301-coursework/blob/main/beat-1-sandbox/unit-3/eval-run.txt). Since I got a passing score, it is ready for the live version.

The [issue](https://github.com/OpenChemistry/avogadroapp/issues/910) where my plan will be checked against the `plan-check` tool involves a feature request to implement two accessibility shortcuts to quickly cycle focus between visible panes. After verifying such shortcuts do not exist and writing a plan to add said feature, running `plan-check` caught many issues, including a lack of a test plan, lack of an AI line, and unanswered questions on whether to make an extra visible pane (the Z-Matrix Editor) in scope. [2](https://github.com/RadEagle/ai301-coursework/blob/main/beat-2-contribution/contribution-story.md) 
> What it produced: reject due to unanswered questions, lack of a test plan, and lack of an AI line. Lots of rubric gaps that unit 3 did not account for, including evidence guide comment file name, ambiguity of "Plan Steps", lack of a repro comment..., procedure missing `scope.md`, and dealing with unanswered questions.

After a few days with the maintainer unable to respond, I came to the conclusion that the Z-Matrix Editor will be out of scope as it lives in a plugin elsewhere in the code.

Claude also listed gaps in the tool itself, to which I later updated to ensure consistency. [3](https://github.com/RadEagle/ai301-coursework/blob/main/tools/plan-check/check-notes.md) 
> The evidence guide puts the plan comment in `comment.md`, but your file is `plan-comment.md`... The procedure never says to check `scope.md` rules... The rubric doesn't say how to treat a plan that depends on an unanswered question on the thread.

After resolving the gaps, I had to fight Claude to ensure the focus wouldn't land in panes that are in a floating dock or collapsed such that it doesn't have any focusable elements. Claude suggested that I either update my plan and add it to Step 1 or delete the tests. No matter how much I edited the plan or modified the tests, it kept complaining about the same issue, so I ended up deleting them. This gave Claude the green light to include them in scope and implemented the whole feature.

This led to two complaints, the first about floating docks. Below is a conversation I had with Claude [4](https://github.com/RadEagle/ai301-coursework/blob/main/tools/plan-check/plan-check-log.md)
> You: "I tested the app and the panes can't be in floating docks in the first place"
> Claude: "...the code says they can... Qt's default makes every `QDockWidget` floatable... You're testing under WSL. WSLg's window handling is known to break dock dragging and floating."
> Claude, on Tab: "Tab can't move focus into a floating dock in Qt... My recommendation: Skip floating docks, the same way Tab does."

The second came after Claude implemented and I tested. [5](https://github.com/RadEagle/ai301-coursework/blob/main/tools/plan-check/plan-check-log.md)
> "the fix mostly works, however, it cycled focus to panes with no focusable elements, like layers and display type settings... before applying the fix, tell me where to update plan.md first, run the plan-check, and then actually apply the fix"

It's so frustrating having to call this out, even **after** I deleted test plans surrounding this very situation, as a normal user would be confused on where the focus went.

Eventually, we got the basic functionality to work and I made my first commit. However, it is still far from finished as when I reordered the panes, the focus doesn't cycle sensibly anymore. So I changed the plan so that it cycles from top to bottom regardless of the content order and ran it through `plan-check` and it complained below. [6](https://github.com/RadEagle/ai301-coursework/blob/main/tools/plan-check/plan-check-log.md)
> Why "Plan complies with thread" fails: ... The issue body, written by ghutchis, asks for the panes "in a fixed order." Test 4 expects on-screen order instead.

This is where I had to update `rubric.md` one more time, to account for ambiguous wording. As for how to resolved the "fixed order" ambiguity, I felt it would be more intuitive if it cycled in on-screen order and mimiced the `Tab` behavior as more users are familiar with it.

So, I got to finalizing the plan when the `plan-check` tool gave me a heads up regarding that panes can be in more docks, just not the left dock. I had an inkling of this happening since I tested the Z-Matrix Editor, which appeared in the right dock and not the left dock. Thus I let Claude do its thing and suggested that the focus should cycle left-top-right-bottom. However, when I tested it, it did not match the tab behavior, which went top-left-right-bottom, which is what I thought it would happen. So, I made the changes to account for that behavior in the plan and Claude made the final code changes so that I'd be satisfied with the result.

When I make my pull request, the maintainer liked it and merged it to the main branch without any questions. [7](https://github.com/OpenChemistry/avogadroapp/pull/931#pullrequestreview-5853707992)
> Sure, seems like a reasonable way to do it.

## Limitations and what's next
One limitation of using the `plan-check` tool is that it doesn't encourage me to change the plan, let alone pinpoint exactly where I'm supposed to change it, over deleting the tests. I had to fight Claude to make sure the behavior works as expected when it is implemented in the code, even after I had to point out the behavior didn't work as expected. Next time, I'll add a nod that ensures any deleted tests doesn't suddenly put it within the behavior scope. I will continue using this tool for my future plans so that I uncover more limitations and better understand how this tool works.