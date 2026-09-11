# Project Atlases

Make project analysis tangible through two complementary artifacts:

**Process atlas** — Explore how the application works: who acts, which actions are available, what allows a transition, and what changes afterward. Walk through representative scenarios and alternative paths, with explanations alongside the simulation.

**Data-model atlas** — Explore the complete schema, including fields, types, keys, nullability, and relationships. Search tables and fields, drag entities around the canvas, show or hide individual tables, and inspect relationship endpoints through tooltips. Pan, zoom, and collapse either sidebar to focus on the model.

The skill instructs the agent to work from the project's current specification or code, distinguish proposed behavior from implemented behavior, and keep unresolved decisions visible. It also covers updating existing atlases without losing their interactions and checking both model accuracy and usability in a browser.

The default deliverables are standalone HTML files that open locally:

```text
docs/process-atlas.html
docs/data-model-atlas.html
```

You can request either atlas independently. The skill provides authoring instructions; your agent generates the artifacts for your project.


## Install

```sh
npx skills add TommyBez/personal-skills --skill project-atlases
```

See the [repository README](../../README.md#install) for agent selection and installation scope.

## Examples

Ask your agent to use `project-atlases` and identify the document, schema, or implementation it should represent. For example:

> Use the project-atlases skill to create a process atlas from docs/architecture.md. Show the main workflow, alternative paths, actors, prerequisites, and the data changed by each action.

> Use the project-atlases skill to create a data-model atlas from the database schema. Include every table and field, with draggable entities, visibility toggles, and relationship tooltips.

> Use the project-atlases skill to update both atlases after the latest schema and workflow changes. Preserve their existing interactions and verify that they match the current specification.


## Skill contents

- [SKILL.md](SKILL.md): entry point and shared authoring workflow.
- [Process atlas reference](references/process-atlas.md): simulation and interaction guidance.
- [Data-model atlas reference](references/data-model-atlas.md): schema exploration and interaction guidance.
