# Tech Trend Radar

`tech-trend-radar` is a Codex/OpenClaw skill for generating technology and market trend reports from fresh industry signals. It focuses on source quality, AI model reranking, GitHub momentum, business impact, and clear next actions.

## Capabilities

- Tracks `1w`, `1m`, and `3m` windows to separate short-term spikes from durable trends.
- Monitors AI model reranking from LMArena/Text Arena, Artificial Analysis, LiveBench, SWE-bench, and OpenRouter.
- Captures GitHub Trending momentum, including stars, forks, releases, issue velocity, and contributor activity.
- Covers AI/ML, developer tools, SaaS, cloud infrastructure, security, startups, funding, regulation, and OpenClaw ecosystem updates.
- Produces structured reports with executive summaries, top signals, action items, category deep dives, sources, and watchlists.

## Usage Examples

Use prompts like:

```text
Write this week's AI trend report
Show current top 10 AI models and ranking changes
Generate a trend radar for developer tools
Summarize GitHub Trending for AI agents this month
What changed in SaaS and AI this week?
```

## Research Sources

Prioritize primary and high-signal sources:

- Official company blogs, release notes, changelogs, pricing pages
- GitHub releases, GitHub Trending, repository activity, RFCs
- Model leaderboards and evals: LMArena/Text Arena, Artificial Analysis, LiveBench, SWE-bench, OpenRouter
- Funding announcements, acquisitions, earnings calls, regulatory filings
- Trusted industry media and community signals when they support stronger evidence

## Report Output

Default report path:

```text
memory/research/tech-trend-radar-YYYY-WXX.md
```

Scoped report examples:

```text
memory/research/tech-trend-radar-ai-agents-YYYY-WXX.md
memory/research/tech-trend-radar-ai-agents-1m-YYYY-MM.md
memory/research/tech-trend-radar-ai-agents-3m-YYYY-QN.md
```

## Skill Files

```text
tech-trend-radar/
├── README.md
└── SKILL.md
```

`SKILL.md` contains the executable skill instructions, including the research workflow, report template, event payload, and keyword configuration.

## Maintenance

Keep the `SKILL.md` frontmatter valid and concise:

```yaml
---
name: tech-trend-radar
description: Use when generating current technology, AI model ranking, product, startup, funding, regulation, or market trend reports from recent industry updates
author: Chad Liu
---
```

Before committing, review the skill docs:

```bash
sed -n '1,80p' tech-trend-radar/SKILL.md
sed -n '1,120p' tech-trend-radar/README.md
git status --short
```
