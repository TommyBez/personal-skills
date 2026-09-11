# Personal Skills

A personal collection of reusable skills for AI coding agents, starting with tools for making project analysis easier to explore and review.

Each skill packages a workflow in a `SKILL.md` file with supporting references. Install the skills you need, then ask your agent to apply them to your project.

## Available skills

| Skill | Purpose |
| --- | --- |
| [Project Atlases](skills/project-atlases/SKILL.md) | Turn a project specification or implementation into interactive HTML process and data-model atlases. |

### Project Atlases

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

With Node.js and npm available, run this from the project where you want to use the skill:

```sh
npx skills add TommyBez/personal-skills --skill project-atlases
```

The [Skills CLI](https://github.com/vercel-labs/skills) guides you through selecting agents and the installation method. Project installation is the default; add `-g` to make the skill available across your projects.

To target a specific agent:

| Agent | Project installation |
| --- | --- |
| Codex | `npx skills add TommyBez/personal-skills --skill project-atlases -a codex` |
| Claude Code | `npx skills add TommyBez/personal-skills --skill project-atlases -a claude-code` |
| Cursor | `npx skills add TommyBez/personal-skills --skill project-atlases -a cursor` |

You can select all three in one command:

```sh
npx skills add TommyBez/personal-skills --skill project-atlases -a codex -a claude-code -a cursor
```

These instructions cover local coding agents. Installing for Claude Code does not install the skill in Claude's web app or Cowork; those use [Claude's account-level skill settings](https://code.claude.com/docs/en/skills#use-skills-in-cowork-and-cloud-sessions).

## Use

Ask your agent to use `project-atlases` and identify the document, schema, or implementation it should represent. For example:

> Use the project-atlases skill to create a process atlas from docs/architecture.md. Show the main workflow, alternative paths, actors, prerequisites, and the data changed by each action.

> Use the project-atlases skill to create a data-model atlas from the database schema. Include every table and field, with draggable entities, visibility toggles, and relationship tooltips.

> Use the project-atlases skill to update both atlases after the latest schema and workflow changes. Preserve their existing interactions and verify that they match the current specification.

In Codex, you can explicitly invoke `$project-atlases`. In [Claude Code](https://code.claude.com/docs/en/skills), use `/project-atlases`; in [Cursor](https://cursor.com/docs/skills), type `/` and select the skill from the available commands.

## Keep skills up to date

List installed skills:

```sh
npx skills list
```

Update this skill:

```sh
npx skills update project-atlases
```

## Repository structure

```text
skills/
└── project-atlases/
    ├── SKILL.md                        # Entry point and shared workflow
    ├── agents/openai.yaml              # Codex display metadata
    └── references/
        ├── process-atlas.md             # Process simulation and interaction guidance
        └── data-model-atlas.md          # Schema exploration and interaction guidance
```

The instructions and references are in English. Ask the agent to write the generated atlases in the language appropriate for your project.
