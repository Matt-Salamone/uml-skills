---
name: uml
description: Use UML to test shared understanding when a discussion establishes meaningful domain relationships, behavior, or software structure relevant to a decision, including apparent agreement. Use when drawing, refining, accepting, or maintaining UML views, or when another skill needs diagram guidance.
---

# UML

Make the current agreement **testable** with visual models. Support individuals and teams; assume a UML-trained audience and explain notation when asked. The calling skill owns the conversation and decision recording. This skill owns diagram work and artifact handling according to recorded agreement.

## 1. Identify the decision and recover context

Take the current decision, relevant glossary, existing diagrams, and known uncertainties from the caller or discussion. Reuse that context across skills in the same discussion. Read `GLOSSARY-MAP.md`, when present, to find the relevant glossary; otherwise use `GLOSSARY.md`. Identify the question each view helps answer and whether it describes proposed design or current implementation.

Introduce diagrams proactively whenever meaningful relationships, behavior, or structure could affect a decision, even when everyone appears to agree. Draw an exploratory sketch immediately without requiring advance permission to sketch. Acceptance and external rendering have separate safeguards below.

On **every invocation**, check local rendering availability, including when setup has already run. Read [rendering.md](references/rendering.md) to prepare previews, probe the configured renderer, and follow its recovery procedure if unavailable. A saved configuration is a hint, not evidence that rendering still works.

## Tracer-bullet approval checkpoints

When the caller is preparing user approval of a tracer-bullet breakdown or its testing seams, require an inspected **component diagram** covering the decision before approval. Show the relevant components, provided/required interfaces, dependency directions, affected boundaries, and test seams. Make each ticket's end-to-end path and independently observable outcome explicit in the view or its accompanying explanation. Distinguish structural dependencies from runtime execution order. A single-component change can use a small view of that component and its public seam; include only actual boundaries.

Reuse an agreed view when its scope and meaning still cover the decision. Revise it when scope, interfaces, dependencies, or seams change. Identify the versions covered by the caller's existing approval step; individual red-green cycles reuse that agreement while it remains valid. Apply the rendering recovery and acceptance rules below if a preview is unavailable or an assumption remains unresolved.

Other diagram types are welcome **in addition to the required component view** whenever helpful. Add sequence views for interactions, state views for lifecycle rules, activity views for workflow, or any other useful UML view. A component diagram alone does not establish execution order or end-to-end behavior. Outside these checkpoints, continue choosing views according to the question.

## 2. Choose and refine useful views

Read [selection.md](references/selection.md) when choosing or refining views, and the relevant case in [examples.md](references/examples.md) for domain relationships, interaction/lifecycle questions, or software structure.

Start with the uncertainty most likely to change the decision. Use the smallest view that makes the agreement testable, including consequential detail. All UML types and constructs remain available. Readily use complementary views when each contributes useful information; another view need not wait for the first to fail. Recommend alternatives with reasons when their differences matter, leaving consequential assumptions to the human.

Revise an existing sketch before continuing when a changed relationship, behavior, or structural assumption could affect the decision. Show what changed and test the revised interpretation. Use additional views when they reveal consequential information that the existing view cannot show clearly. Keep names and semantics compatible across views; state scope and abstraction differences.

## 3. Draw, render, and inspect

Use authoritative PlantUML source and generated SVG previews; generate PNG when the discussion surface requires it. Keep exploratory artifacts temporary. Read [rendering.md](references/rendering.md) for commands and, on failures or unsupported constructs, its troubleshooting branches.

Inspect the actual generated preview before presentation. Check separately:

- Rendering and readability: labels, directions, guards, multiplicities, and layout are legible and unclipped.
- Intended UML meaning: notation says what the question requires, including ownership and lifecycle constraints.
- Consistency: glossary, supporting prose, related views, messages, and transitions agree, or discrepancies are explicitly visible.
- Uncertainty: consequential assumptions and unresolved alternatives are visible instead of presented as settled facts.

A successful render proves only rendering. Support current-implementation claims with implementation evidence under [lifecycle.md](references/lifecycle.md), read whenever checking implementation, accepting, revising, or disputing diagrams.

Preserve and mark failed source **unrendered**, expose the failure, and offer a concrete local remedy or an external renderer authorized for the environment. Continue unrelated discussion; defer decisions requiring visual inspection until a preview is available. External rendering requires authorization for that environment. Preserve intended semantics when a construct is unsupported; seek a compatible renderer, then propose an explicit source-format exception for human agreement if necessary. Retain one authoritative source per diagram.

## 4. Expose assumptions and return to the caller

Embed each inspected preview needed for the current decision in the final user-facing response alongside the question it helps resolve. Tool output, inspection calls, and collapsed progress commentary do not count as presentation. Explicitly identify which relationship, transition, or assumption the user should examine. Identify consequential assumptions, contradictions, and concrete suggested questions, with a recommendation where useful. Distinguish proposed interpretations from human answers. Return the current source/preview locations and unresolved uncertainties so another skill can reuse them.

The caller incorporates questions into its workflow, waits for human clarification, and records decisions. With no caller, do that conversational work here. Agreement on a surrounding decision accepts only the explicitly identified diagram versions included in that agreement; silence or a topic change is not acceptance. Follow an existing team approval process without adding a mandatory one.

Read [lifecycle.md](references/lifecycle.md) when accepting a version, revising accepted material, marking a discrepancy, or checking implementation. Save accepted source and SVG alongside the supporting document with stable descriptive names, scope, designation, and reciprocal links. Semantic or scope changes remain proposed until agreed; presentation-only changes retain acceptance. Mark unresolved affected views stale or disputed and preserve previous acceptance in available history.

UML's benefit is a working assumption to revisit if actual use feels clunky or produces poor results. These quality checks and teaching examples do not require an effectiveness study or validation scenario suite.
