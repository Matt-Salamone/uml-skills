## What it does

`uml` makes shared understanding **testable** with visual models of domain relationships, behavior, and software structure. It introduces useful diagrams proactively, including when you and the agent appear to agree, then exposes assumptions as concrete questions.

The conversation stays with the calling skill. UML supplies inspected previews and handles diagram artifacts according to recorded agreement; a successful render does not settle a design decision. It assumes a UML-trained audience and explains notation when asked.

## When to reach for it

Type `/uml`, or the [agent](https://www.aihero.dev/ai-coding-dictionary/agent) reaches for it automatically when a task fits.

- Use it for meaningful relationships, behavior, or structure that could change a decision, or to maintain an existing diagram.
- For an interview, use [grilling](https://aihero.dev/skills-grilling), which brings UML questions into its rounds.
- For concepts and terminology, use [domain-modeling](https://aihero.dev/skills-domain-modeling); for interfaces and dependencies, use [codebase-design](https://aihero.dev/skills-codebase-design). Both bring in UML when useful.

## Prerequisites

Visual decisions require a working local PlantUML renderer and a way to inspect its previews. [Setup](https://aihero.dev/skills-setup-matt-pocock-skills) can record a renderer, but UML checks availability every time, including without setup. The skill's rendering reference provides a versioned local CLI baseline using Java and PlantUML, with Smetana for the teaching examples. External rendering requires authorization for the environment.

## One question, useful views

The question chooses the view. A class view can test ownership and multiplicities; a sequence view tests interaction order; a state view tests allowed transitions. Useful complementary views can appear together immediately. All UML types and constructs remain available, subject to checking the renderer's actual support.

PlantUML source is authoritative. SVG previews are generated from it, with PNG when the discussion surface needs it. The agent inspects the preview before presenting it and checks intended meaning, consistency, and unresolved assumptions separately from rendering success. The [PlantUML documentation](https://plantuml.com/) describes the source language and renderer.

Exploratory sketches stay temporary. Agreement on a decision accepts the explicitly identified diagram versions included in it. Accepted source and previews live beside the supporting document, with scope, links, and a proposed-design or current-implementation designation. Claims about current implementation need implementation evidence. Semantic revisions need renewed agreement; unresolved discrepancies stay visibly stale or disputed.

## Common questions

**Will it draw even if we already agree?**

Yes. Apparent agreement can hide different interpretations. The diagram tests a concrete relationship or behavior; you can correct it or redirect the discussion.

**What happens if rendering fails?**

The source is preserved and marked unrendered, with the failure and a concrete remedy. Unrelated discussion continues, but decisions needing visual inspection wait for a preview. Switching renderers or formats preserves the intended meaning; a format exception requires your agreement.

**Does approving a decision mean every diagram is accepted?**

Only the explicitly identified versions included in that agreement. Silence and a topic change accept nothing. An existing team approval process still applies, without adding a new mandatory process.

## It's working if

- The inspected preview appears in the final response alongside a specific question about a relationship, transition, or assumption you can answer or correct, without opening tool activity or earlier commentary.
- Ownership, multiplicities, guards, and dependencies that affect the decision are visible.
- Your answer changes the existing model, and related views stay compatible.
- Proposed designs and current implementation remain distinguishable, with evidence for implementation claims.
- An unresolved discrepancy stays visible instead of turning into a settled requirement.

These are quality signals. UML's benefit remains a working assumption to revisit if actual use feels clunky or produces poor results.

## Where it fits

UML is a reach-for-it-anytime shared modeling discipline beneath grilling, domain-modeling, codebase-design, and [to-spec](https://aihero.dev/skills-to-spec). Wayfinder and grill-with-docs inherit it through their discussion skills. The caller keeps conversation and decision ownership; to-spec pauses for targeted clarification if a diagram exposes an unresolved assumption. [Ask-matt](https://aihero.dev/skills-ask-matt) maps the broader flows.
