---
name: to-spec
description: "Synthesize the conversation into a spec and publish it to the issue tracker, with targeted clarification of unresolved UML assumptions."
disable-model-invocation: true
---

This skill takes the current conversation context and codebase understanding and produces a spec. Synthesize what you already know without a fresh interview, except for the targeted UML clarification below. Preserve the existing seam confirmation step.

The issue tracker and triage label vocabulary should have been provided to you. If not, tell the user to run `/setup-matt-pocock-skills`.

## Process

1. Explore the repo to understand the current state of the codebase, if you haven't already. Use the project's domain glossary vocabulary throughout the spec, and respect any ADRs in the area you're touching.

2. Sketch out the seams at which you're going to test the feature. Existing seams should be preferred to new ones. Use the highest seam possible. If new seams are needed, propose them at the highest point you can. The fewer seams across the codebase, the better - the ideal number is one.

Before confirming these seams, call the Skill tool with "uml" for the tracer-bullet approval checkpoint. Supply the feature scope, proposed seams, and existing diagrams. Present the required inspected component view with the seam proposal; reuse an agreed view when it still covers the decision. Other helpful diagram types are welcome in addition to the component view. Include complementary views when they clarify behavior or expose assumptions. Follow UML recovery if rendering is unavailable and defer the visually dependent confirmation.

Check with the user that these seams match their expectations, identifying the diagram versions included in that agreement. Preserve the accepted source, previews, and version references with the spec so downstream tickets can reuse them.

When synthesis establishes meaningful relationships, behavior, or structure relevant to a decision, including apparent agreement, call the Skill tool with "uml". Supply the current decision, relevant glossary and existing diagrams, and known uncertainties, reusing context from earlier discussion skills. Use its inspected previews, assumptions, and suggested questions. If a diagram exposes an unresolved assumption, pause finalization, show the smallest relevant view, identify the specific assumption, and obtain the human's clarification before treating it as settled. Preserve existing decisions elsewhere. Keep conversation and spec/decision recording here; pass recorded agreement back to UML for artifact handling.

3. Write the spec using the template below, then publish it to the project issue tracker. Apply the `ready-for-agent` triage label - no need for additional triage.

<spec-template>

## Problem Statement

The problem that the user is facing, from the user's perspective.

## Solution

The solution to the problem, from the user's perspective.

## User Stories

A LONG, numbered list of user stories. Each user story should be in the format of:

1. As an <actor>, I want a <feature>, so that <benefit>

<user-story-example>
1. As a mobile bank customer, I want to see balance on my accounts, so that I can make better informed decisions about my spending
</user-story-example>

This list of user stories should be extremely extensive and cover all aspects of the feature.

## Implementation Decisions

A list of implementation decisions that were made. This can include:

- The modules that will be built/modified
- The interfaces of those modules that will be modified
- Technical clarifications from the developer
- Architectural decisions
- Schema changes
- API contracts
- Specific interactions

Do NOT include specific file paths or code snippets. They may end up being outdated very quickly.

Exception: if a prototype produced a snippet that encodes a decision more precisely than prose can (state machine, reducer, schema, type shape), inline it within the relevant decision and note briefly that it came from a prototype. Trim to the decision-rich parts, not a working demo, just the important bits.

## Testing Decisions

A list of testing decisions that were made. Include:

- A description of what makes a good test (only test external behavior, not implementation details)
- Which modules will be tested
- Prior art for the tests (i.e. similar types of tests in the codebase)

## Diagrams

Durable links to accepted component source and preview, their agreed version identity, scope, and test seams. Include any helpful complementary views. Diagram artifact links are an exception to the file-path restriction above. Use tracker-accessible attachments or repository links for a real tracker, or saved artifacts linked from a local spec; temporary paths cannot carry agreement into a fresh session.

## Out of Scope

A description of the things that are out of scope for this spec.

## Further Notes

Any further notes about the feature.

</spec-template>
