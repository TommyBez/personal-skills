# Personal Skills

A growing collection of reusable skills for AI coding agents. Each skill captures a focused workflow, with instructions and supporting resources that agents can apply across projects.

Browse the catalog, install the skills that fit your work, and use them with Codex, Claude Code, Cursor, or another compatible agent. Skill documentation and instructions are in English; generated artifacts can use your project's language.

## Skill catalog

| Skill | What it helps you do |
| --- | --- |
| [Project Atlases](skills/project-atlases/README.md) | Create and maintain interactive HTML process simulations and explorable data-model diagrams from project specifications or code. |

Each skill's page describes its capabilities, expected outputs, and usage examples.

## Install

With Node.js and npm available, run this from your project directory to choose skills from the collection:

```sh
npx skills add TommyBez/personal-skills
```

The [Skills CLI](https://github.com/vercel-labs/skills) guides you through skill selection, agents, and installation method. Installation is scoped to the current project by default. Add `-g` to make the selected skills available across your projects.

To target an agent:

| Agent | Project installation |
| --- | --- |
| Codex | `npx skills add TommyBez/personal-skills -a codex` |
| Claude Code | `npx skills add TommyBez/personal-skills -a claude-code` |
| Cursor | `npx skills add TommyBez/personal-skills -a cursor` |

Combine agents in one command with `-a codex -a claude-code -a cursor`.

To install a specific skill, add `--skill` followed by its name. For example:

```sh
npx skills add TommyBez/personal-skills --skill project-atlases
```

These instructions cover local coding agents. For Claude's web app and Cowork, manage skills through [Claude's account-level skill settings](https://code.claude.com/docs/en/skills#use-skills-in-cowork-and-cloud-sessions).

## Use a skill

Name the skill in your request, describe the result you want, and point the agent to the relevant project files. Each catalog entry links to examples tailored to that skill.

For explicit invocation:

| Agent | How to invoke |
| --- | --- |
| Codex | Type `$` followed by the installed skill's name. |
| [Claude Code](https://code.claude.com/docs/en/skills) | Type `/` followed by the installed skill's name. |
| [Cursor](https://cursor.com/docs/skills) | Type `/` and select the installed skill. |

## Manage installed skills

List your installed skills:

```sh
npx skills list
```

Update installed skills:

```sh
npx skills update
```

To update just one skill, append its name to the update command.

## Versioning

Each skill has its own `MAJOR.MINOR.PATCH` version, recorded in `metadata.version` in its `SKILL.md`. This uses the standard [Agent Skills metadata field](https://agentskills.io/specification#metadata-field).

For this collection:

- **Patch**: corrections and clarifications that preserve the workflow and expected outputs.
- **Minor**: new capabilities that preserve existing usage.
- **Major**: changes that require adapting how the skill is used or change its expected outputs incompatibly.

A published version covers the entire skill directory, including its supporting resources. Each release has a Git tag named `<skill-name>-v<version>` and [release notes](https://github.com/TommyBez/personal-skills/releases). Published tags stay fixed; subsequent changes receive a new version. Repository-only documentation changes do not require a skill release.

The installation commands above use the default branch, which may contain unreleased changes. To install a particular release, use its tag URL and select the skill:

```sh
npx skills add https://github.com/TommyBez/personal-skills/tree/project-atlases-v1.0.0 --skill project-atlases
```

The tag selects the snapshot; `metadata.version` labels it, rather than acting as a package-manager version constraint. To move to a different release, install from that release's tag URL. Use the untagged source and `skills update` when you want to follow ongoing development.

## Repository layout

Each skill lives in its own directory under `skills/`:

```text
skills/<skill-name>/
├── SKILL.md        # Instructions loaded by the agent
├── README.md       # Overview and usage examples
└── ...             # Supporting resources, when needed
```

Depending on the workflow, a skill may include references, scripts, assets, or agent-specific metadata. Its `SKILL.md` is the entry point for the agent; its README is the starting point for readers.
