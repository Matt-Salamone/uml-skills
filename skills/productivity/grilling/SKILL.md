---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

When discussion establishes meaningful relationships, behavior, or structure relevant to a decision, including apparent agreement, call the Skill tool with "uml". Supply the current decision, relevant glossary and existing diagrams, and known uncertainties, reusing context from other skills in this discussion. Incorporate its inspected previews and concrete suggested questions into the interview rounds and wait for the human's answers. When a round uses a diagram, embed its inspected preview in the same final response as the questions that reference it. Make those references explicit so the user can answer without opening tool activity or earlier commentary. Keep ownership of the conversation and decision recording here; pass recorded agreement back to UML for artifact handling.

Start every assistant turn during active grilling with a compact **progress forecast**, using the latest answers to update it. Put the forecast at the top of the final response, before questions, diagrams, or other discussion; if commentary opens the turn, show it there too so progress is visible immediately and survives collapsed tool activity.

Show a ten-cell text progress bar, the number of fully answered rounds, and an estimated count of remaining rounds **including the current round**. Fill the bar in proportion to completed rounds divided by completed plus estimated remaining rounds. Count answered rounds, not messages: follow-up turns on a partially answered round do not complete another round. Track this in the conversation without creating progress files.

List the major topics of **each** estimated remaining round in order, marking the first as the current round. Later topics are a provisional roadmap, not settled decisions or permission to ask dependent questions early. Label the count and roadmap as estimates that may change with unexpected answers, new dependencies, or reopened decisions. When the estimate or roadmap changes, briefly explain why. Recompute honestly even if the bar moves backward; the forecast is not a round cap or a reason to truncate the frontier. When the frontier is empty, show a full bar, zero rounds remaining, and shared-understanding confirmation pending until the user confirms.

Format a round like so:

```
Progress (estimate): [###-------] 2 rounds completed; ~4 remaining, including this round.
Remaining topics: this round: constraints; next: alternatives; then: failure handling; then: final review.
This estimate may change as answers reveal new dependencies or reopen decisions.

❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Word each question so "yes" accepts your recommended answer.

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it; don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.
