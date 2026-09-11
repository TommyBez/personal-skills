---
name: project-atlases
description: Create and maintain interactive HTML process and data-model atlases during project analysis. Use for a process atlas, workflow/state simulator, data-model atlas, or explorable E-R diagram grounded in a project's specification or implementation.
metadata:
  version: "1.0.0"
---

# Project Atlases

Build tools that let readers explore how a project works and examine its data model. An atlas is valuable when it answers concrete questions and faithfully represents the analysis.

## Choose the deliverable

- **Process atlas**: what happens, who acts, what allows progress, and which data changes. Read [references/process-atlas.md](references/process-atlas.md).
- **Data-model atlas**: what each entity contains and how it relates to the others. Read [references/data-model-atlas.md](references/data-model-atlas.md).
- For both, read both references and use consistent names and meanings. If the request concerns only one atlas, limit the work to that deliverable.

During broader project analysis, suggest atlases when exploring paths or relationships helps resolve concrete questions. A simple answer about a field does not require building these artifacts.

## Establish what to represent

Read the current specification, schemas, or relevant implementation. Clarify whether the atlas represents a proposal or implemented behavior. Identify discrepancies without inventing rules to resolve them.

Derive an explicit model from these sources:

- Process: states, actions, actors, conditions, effects, and alternative paths.
- Data: entities, all fields, types, nullability, keys, and relationships.

If a missing decision affects behavior, mark it as unresolved or ask for the necessary information. Example values are teaching aids, not requirements.

Do not automatically carry roles, state counts, frameworks, versioning policies, history management, or concurrency mechanisms from one project into another. Represent the project's actual choices.

## Delivery format

Prefer standalone HTML files that work locally without external services, unless the user requests otherwise or project constraints require another approach. Preserve existing paths; suitable paths for new repository artifacts include:

- `docs/process-atlas.html`
- `docs/data-model-atlas.html`

Each atlas must be understandable on its own: project title, scope, control meanings, and explanations of how the process works. A source date or revision identifies the snapshot represented. A link to the specification is helpful, but using the atlas must not depend on opening it.

Keep model data separate from layout and rendering, even within the same file. When the source is structured, derive tables and relationships from it to avoid divergent manual copies. Updating the model must preserve existing interactions.

Write copy that describes the current project. Omit revision narratives, discarded alternatives, and explanations such as “this table no longer exists.” State the boundaries needed to interpret the simulation.

## Shared UX and verification

Prioritize readable names, clear selection state, recognizable actions, and accessible details. Density should support orientation first, then deeper inspection. Adapt the appearance to the project; an example's colors and layout are not a mandatory template.

Provide keyboard-operable controls, accessible labels, and visible focus. Arrange panels on smaller screens without losing content or controls.

Open the artifact in a browser and verify the main user journey and changed interactions. Compare content and relationships against the source; syntax checks do not establish model fidelity. Keep verification proportional rather than introducing test infrastructure solely for these HTML files.

Deliver links to the files and state what was actually verified. A process simulation does not prove the backend works. Creating atlases does not imply operational schema changes, migrations, or publishing.
