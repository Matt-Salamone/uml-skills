---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

If the user passes a ticket reference, fetch it from the issue tracker and state its title before starting. If the reference is ambiguous, ask.

Recover linked diagram sources, previews, and agreed versions from the ticket, spec, or conversation before implementation. Check that their scope and seams cover this work. If the covering component view or its agreement is missing, or a discrepancy affects the agreed scope, interfaces, dependencies, or seams, call the Skill tool with "uml" to prepare the revised component view and any helpful complementary diagrams, then obtain targeted clarification before implementing the affected decision. Preserve the existing approval for unaffected work. Apply this checkpoint even when TDD is unsuitable.

Call the Skill tool with "tdd" where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, call the Skill tool with "code-review" to review the work.

Commit your work to the current branch.
