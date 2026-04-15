# Repository Guidelines

## Project Structure & Module Organization

This repository stores local skill packages. Each skill lives in its own top-level directory, such as `tech-trend-radar/`.

- `tech-trend-radar/SKILL.md`: main skill definition, including frontmatter, usage instructions, report format, and customization notes.
- `tech-trend-radar/_meta.json`: registry metadata for the published skill.
- `tech-trend-radar/.clawhub/origin.json`: installation source metadata from ClawHub.

Keep skill-specific docs and assets inside the related skill directory. Add new skills as sibling directories with their own `SKILL.md`.

## Build, Test, and Development Commands

There is no package manager, build system, or automated test runner configured in this repository. Use lightweight validation commands before committing:

```bash
rg --files
```

Lists tracked project files and helps confirm new files are in the expected location.

```bash
sed -n '1,80p' tech-trend-radar/SKILL.md
```

Checks that skill frontmatter and opening instructions remain readable.

```bash
git status --short
```

Reviews changed files before commit.

## Coding Style & Naming Conventions

Write skill documentation in Markdown. Use concise headings, short paragraphs, and fenced code blocks for commands or structured examples. Keep YAML frontmatter at the top of each `SKILL.md` with fields such as `name`, `description`, and `author`.

Use lowercase, hyphenated directory names for skills, for example `tech-trend-radar`. Prefer ASCII text unless the content specifically requires another language.

## Testing Guidelines

No formal tests are present. For documentation-only changes, manually verify Markdown structure, examples, and any JSON snippets. For metadata changes, ensure JSON files remain valid:

```bash
python -m json.tool tech-trend-radar/_meta.json
python -m json.tool tech-trend-radar/.clawhub/origin.json
```

When adding executable scripts or generated outputs, include a clear command for reproducing or validating them in the skill documentation.

## Commit & Pull Request Guidelines

The current history uses short, imperative commit messages such as `init project`. Continue with concise messages that describe the change, for example `update trend radar keywords` or `add contributor guide`.

Pull requests should include a brief summary, list of changed skill directories, and validation performed. Link related issues when available. Include screenshots only when a change affects rendered output or published documentation previews.

## Agent-Specific Instructions

Do not edit registry metadata unless the task is explicitly about publication or installation details. Keep changes scoped to the relevant skill directory and avoid introducing build tooling unless it is needed by an actual skill implementation.
