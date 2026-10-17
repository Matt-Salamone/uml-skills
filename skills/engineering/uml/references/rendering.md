# Local source and previews

Read to prepare previews on every invocation. Read the recovery branches below when a check, render, or construct fails.

## Discover and probe

Read `docs/agents/uml-rendering.md` if present, then inspect available local PlantUML commands, Java/JAR paths, and any required layout engine. Reuse a working local setup. Check its version and render a small probe with the needed diagram family and constructs to temporary storage. Inspect the output; a command existing or a stale preview is not a successful probe. Repeat for materially different constructs as needed. Setup is optional and never replaces this invocation check.

Keep one authoritative `.puml` source per diagram. Render SVG from it; generate PNG from that same source when the surface needs PNG. Inspect the actual preview with available image/browser tools before showing it. If inspection tooling is unavailable, report that gap and defer visually dependent decisions. Present the preview with a concise model question. Regenerate previews after source changes.

## Reproducible CLI baseline

The teaching examples use PlantUML **1.2024.8**, a local Java runtime (tested with OpenJDK **25.0.4**), and bundled **Smetana** layout via `!pragma layout smetana` where needed. This baseline avoids requiring a separately installed Graphviz for these examples. It does not guarantee coverage of every UML construct. Reuse other working versions when suitable; record versions, engine, fonts, and invocation when reproducibility matters.

Obtain the versioned JAR from the [official release](https://github.com/plantuml/plantuml/releases/tag/v1.2024.8). Downloading tooling is separate from installing the skills. Keep it outside diagram artifact folders. The JAR used for the checked examples has SHA-256 `b88519d2f37c089a470ee7044ec011a72d130e70a61f7fcaa424179f1c1f4641`.

Example local commands, replacing the JAR and source paths:

```sh
java -version
java -jar /path/to/plantuml-1.2024.8.jar -version
java '-Djava.awt.headless=true' '-DPLANTUML_SECURITY_PROFILE=SANDBOX' -jar /path/to/plantuml-1.2024.8.jar -charset UTF-8 -failfast2 -tsvg /path/to/diagram.puml
java '-Djava.awt.headless=true' '-DPLANTUML_SECURITY_PROFILE=SANDBOX' -jar /path/to/plantuml-1.2024.8.jar -charset UTF-8 -failfast2 -tpng /path/to/diagram.puml
```

These commands work in a shell with Java on PATH; quote paths containing spaces. Outputs appear beside the source with matching basenames. The sandbox profile keeps the baseline self-contained and prevents remote includes. Use local reviewed definitions when more notation is needed. Check the exit status and inspect the generated file for error images and layout faults. For all teaching sources, pass the quoted `examples/*.puml` pattern in place of the single source path, from this skill folder.

Graphviz-based local setups may be preferable for some constructs or layouts. Probe them rather than silently switching semantics. See the official [CLI documentation](https://plantuml.com/command-line), [layout engines](https://plantuml.com/smetana02), and [security profiles](https://plantuml.com/security). The commands above use the pinned version's CLI flags.

## Recovery

- **No renderer or Java/JAR missing:** preserve the source with an **unrendered** status in the discussion or supporting record. Name the missing executable or path. Offer the concrete local remedy of a Java runtime plus the versioned JAR and commands above, or repair the recorded path. Offer an external renderer only with authorization for the environment.
- **Syntax error, crash, or unreadable layout:** expose the diagnostic and preserve the intended source. Correct syntax/layout and retry locally. Do not present an old preview as current or an error image as the diagram. If recovery fails, mark unrendered and defer only decisions requiring visual inspection; continue unrelated work.
- **Unsupported construct:** identify the exact renderer or syntax limitation and write down the intended UML meaning. Try another compatible local renderer or engine first. If PlantUML itself cannot express the construct, propose an explicit source-format exception for human agreement. Preserve one authoritative source and regenerate previews from it. A tool limitation is not a UML limitation; weakening the model silently is not recovery.
- **External renderer:** obtain authorization for that environment before sending source. PlantUML URLs encode recoverable source; they are not private just because the text looks compressed. Record the authorized service and scope. A local failure does not grant authorization. Use the same inspection and quality checks on the result.

When rendering remains unavailable, preserve and mark the source unrendered, explain the failure and remedy, continue unrelated discussion, and defer decisions requiring a preview. Keep the calling skill informed of the specific blocked question.
