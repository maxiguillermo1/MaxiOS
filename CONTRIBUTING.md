# Contributing to MaxisOS

Thank you for helping improve MaxisOS. This project is [MIT-licensed](LICENSE). By contributing, you agree that your contributions will be licensed under the same terms.

## Ways to help

- **Report issues** — unexpected helper behavior, unclear docs, or setup problems. Include what you asked, what happened, and what you expected.
- **Suggest improvements** — agent prompts, routing, onboarding flow, or user-facing docs.
- **Submit pull requests** — fixes, examples, or small, focused enhancements.

## Project layout (where to edit)

| Area | Purpose |
|------|---------|
| `agents/` | Agent definitions (YAML frontmatter + system instructions). Primary source for behavior. |
| `skills/` | Generated from agents; run `python3 scripts/generate-skills.py` after changing agents if you use the skills layout. |
| `references/` | Shared text agents read (`agents-registry.md`, `agent-orchestration.md`, `agents.md`). Keep in sync with routing rules. |
| `docs/` | User guides (`getting-started.md`, `examples.md`, `DISCLAIMERS.md`, `agents/`). |
| `scripts/` | `launchme.sh`, `updateme.sh`, `generate-skills.py` — installer and tooling. |

Routing and delegation rules for Claude Code live in **`CLAUDE.md`** at the vault root after install (copied or merged by your workflow). Changes that affect “who handles what” should stay consistent with **`references/agents-registry.md`** and **`CLAUDE.md`** in this repository.

## Guidelines

1. **Keep changes focused** — one logical change per pull request when practical.
2. **Match existing style** — tone and structure of nearby agent or doc files.
3. **Preserve agent frontmatter** — `name`, `description`, `tools` / model fields must remain valid for Claude Code.
4. **Do not remove safety boundaries** — wellness-related or medical disclaimers in prompts and docs should stay prominent where they apply.
5. **Test locally** — run `bash scripts/launchme.sh` or `updateme.sh` in a test vault when you change scripts; exercise changed agents in Claude Code when you can.

## Pull requests

- Use a clear title and description (what changed and why).
- Link related issues if any.
- For substantive behavior changes, mention any trade-offs or follow-up work.

## Code of conduct

Be respectful and constructive. Harassment or abuse in issues or pull requests is not acceptable.

## Questions

Open a [GitHub issue](https://github.com/maxiguillermo1/MaxisOS/issues) on the MaxisOS repository for discussion before large refactors or new agents.
