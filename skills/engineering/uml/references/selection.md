# Selection and refinement

Read when choosing or refining a view. At tracer-bullet approval checkpoints, include the component view required by SKILL.md. Use the question to choose additional helpful views and to select views outside those checkpoints. All UML diagram types and constructs remain available; these are starting points:

- Concepts and relationships: class or object views. Include consequential multiplicities, ownership, identity, and lifecycle constraints. An association does not automatically mean composition; shared aggregation and composition are different claims.
- Interaction order and responsibility: sequence or communication views. Show consequential messages, synchronous/asynchronous behavior, alternatives, loops, and failures.
- Allowed lifecycle transitions: state machines. Show consequential events, guards, actions, and terminal states. An interaction trace alone cannot establish all legal transitions.
- Workflows and concurrent work: activity views. Distinguish decisions from forks and merges from joins; name relevant guards and responsibility partitions.
- Software organization and runtime placement: component, package, composite structure, or deployment views. Distinguish dependencies, provided/required interfaces, ownership, and deployment placement.
- Other questions: choose another UML view or construct when it expresses the uncertainty better, including use cases, timing, profiles, and interaction overviews. Renderer support must be checked for the exact construct.

Start with the uncertainty most likely to change the decision. Include detail that could change an answer even when nobody requested it. Omit incidental attributes and operations. A small diagram with a missing consequential multiplicity is too small.

Use multiple views readily when each adds useful information. Sequence and state views can jointly test interaction order and legal lifecycle behavior. Keep domain names, relationships, messages, and transitions compatible. State any scope or abstraction difference explicitly; omission is acceptable, contradiction needs a question.

When alternatives affect the decision, show small contrasting sketches or clearly marked variations. Recommend an interpretation and explain why; the human settles the assumption. Do not hide an unresolved choice behind a tidy arrow. After an answer, revise the existing view, explain the changed meaning, render and inspect it, then test the revised interpretation before continuing.

Read the matching case in [examples.md](examples.md) for selection and refinement judgment, rather than copying its illustrative domain rules into the current project.
