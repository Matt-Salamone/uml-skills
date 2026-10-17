# Acceptance and maintenance

Read when accepting, revising, disputing, or checking implementation against a diagram.

## Exploratory to accepted

Keep exploratory sketches in temporary discussion storage. Rendering or presenting one does not accept it. The caller records human agreement on the supporting decision and explicitly identifies the diagram versions included in it, by source revision, content hash, or another unambiguous version identity. Silence or changing the topic establishes nothing. For a team, follow its existing approval process; no additional mandatory approval process is introduced.

After that agreement, save each accepted diagram alongside its specification, decision record, or documentation:

- Stable descriptive basename, shared by source and SVG, for example `reservation-lifecycle.puml` and `reservation-lifecycle.svg`. Add a PNG of the same version when needed by the surface.
- Stated scope and abstraction, and a **proposed-design** or **current-implementation** designation. Acceptance is separate from designation: a proposed design can be accepted before implementation.
- Link from the supporting document to source and preview, and a link back to the supporting document from the source header and preview caption or adjacent record. Include the accepted version identity and any unresolved questions outside the agreed scope.
- Implementation evidence links for current-implementation claims, covering the claimed scope. These can name code revisions and locations, tests, or observed runtime behavior; explain what each establishes.

Keep metadata with the supporting document or source, rather than inventing a new global registry. Generate previews from the authoritative source. Do not edit images independently.

## Revision

The agent changing a model identifies affected accepted diagrams and updates source and previews as part of that work. Inspect the new previews and check linked documents and related views for contradictions. Reuse existing diagrams instead of creating unrelated replacements for the same scope.

- Presentation-only changes, such as spacing or color with no change in meaning, retain acceptance. Regenerate and inspect previews and retain traceability to the accepted semantics.
- Meaning or scope changes require agreement on the revised decision and explicitly identified diagram version. Prepare the revision immediately if useful, label it proposed, and retain the previous accepted version in available history until agreement.
- If the correct interpretation cannot be established, surface that uncertainty. Mark all affected views **stale** (known to lag the model) or **disputed** (meaning or authority unresolved), state the discrepancy visibly beside the preview and in its supporting record, and link the unresolved question. Preserve the previous accepted version in available history before overwriting it. Continue unrelated work without treating the disputed relationship as settled or silently preferring code over diagram or diagram over code.

## Checking implementation

Before changing proposed-design to current-implementation, compare its full stated scope with implementation evidence. Rendering, tests passing elsewhere, and human approval alone do not establish implementation correspondence.

- Full match: reuse the diagram with updated context and evidence links, regenerate as needed, and inspect the preview after changing its designation.
- Differences or partial implementation: retain the proposed design and create a distinct current-implementation view, with its own descriptive basename, scope, evidence, and explicit differences. Partial implementation does not justify relabeling the whole proposed design.

Resolve contradictions across views, prose, and evidence through the caller's conversation. Record the human's answer, update every affected view, and apply the appropriate presentation-only or semantic revision procedure.
