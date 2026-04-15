---
name: tech-trend-radar
description: Use when generating current technology, AI model ranking, product, startup, funding, regulation, or market trend reports from recent industry updates
author: Chad Liu
---

# Trend Radar

Generate an industry trend report from recent, credible technology and market updates. Prioritize fresh signals, source quality, model reranking, GitHub momentum, business impact, and clear next actions.

## When to Use

Use this skill when the user asks for:

- Weekly, monthly, or quarterly technology trends
- AI, SaaS, developer tools, cloud, security, startup, or regulation updates
- Model reranking, leaderboard changes, and current top model summaries
- GitHub Trending and open-source momentum summaries
- Market signal summaries for planning, investing, product strategy, or competitive tracking
- A concise report that distinguishes major shifts from ordinary news

Trigger examples:

```text
Write this week's AI trend report
Show current top 10 AI models and ranking changes
Generate a trend radar for developer tools
Summarize GitHub Trending for AI agents this month
Summarize recent market trends in AI agents
What changed in SaaS and AI this week?
```

## Research Workflow

1. Define the report period. Default to `1w` unless the user specifies `1w`, `1m`, `3m`, or an exact date range.
2. Search by category, not only by generic keywords. Combine company names, product names, ecosystem terms, and event types.
3. Check model leaderboards for reranking, new entrants, score deltas, and category shifts.
4. Check GitHub Trending and repository momentum for relevant categories, languages, and keywords.
5. Prefer primary and high-signal sources before commentary.
6. Cross-check major claims with at least two credible sources when possible.
7. Deduplicate repeated coverage of the same announcement.
8. Score each item by novelty, impact, source quality, ranking movement, open-source traction, and actionability.
9. Separate confirmed facts from interpretation. Label uncertain items as `Watch`.

## Time Windows

Use three standard windows to separate short-term noise from durable trends:

| Window | Use For | Signal Focus |
|--------|---------|--------------|
| `1w` | Weekly scan | launches, releases, incidents, funding, GitHub Trending spikes |
| `1m` | Monthly pattern | repeated adoption, repo growth, new categories, competitor movement |
| `3m` | Quarterly shift | platform changes, durable market direction, ecosystem consolidation |

When reporting multiple windows, compare them explicitly: `1w = new spike`, `1m = traction`, `3m = durable direction`.

## Source Priority

Use higher-priority sources first:

| Priority | Source Type | Examples |
|----------|-------------|----------|
| 1 | Official announcements | company blogs, product release notes, API changelogs, pricing pages |
| 1 | Primary technical artifacts | GitHub releases, RFCs, benchmark reports, model cards, research papers |
| 1 | Model leaderboards | LMArena/Text Arena, Artificial Analysis, LiveBench, SWE-bench, OpenRouter rankings |
| 1 | GitHub momentum | GitHub Trending, stars, forks, releases, issue velocity, contributor activity |
| 2 | Business records | funding announcements, acquisition news, earnings calls, regulatory filings |
| 2 | Trusted industry media | The Verge, TechCrunch, The Information, Stratechery, VentureBeat, The Pragmatic Engineer |
| 3 | Community signals | Hacker News, Reddit, X posts, Discord/Slack communities, GitHub stars/issues |

Community signals should support a trend, not be the only evidence for a high-impact claim.

## Model Reranking Signals

Track AI model ranking movement as a dedicated signal. Always state which leaderboard is used because rankings measure different things:

| Leaderboard | Measures | Use For |
|-------------|----------|---------|
| LMArena / Text Arena | Human preference battles | General chat quality and user preference |
| Artificial Analysis | Composite intelligence, speed, cost | Balanced capability and deployment comparison |
| LiveBench | Dynamic benchmark performance | Reasoning, coding, math, and contamination-resistant evals |
| SWE-bench | Real-world coding tasks | Coding agent and software engineering capability |
| OpenRouter Rankings | Real API usage | Developer adoption and production demand |

For each reranking item, capture:

- **Current Top 10**: rank, model, provider, score or usage metric, source, timestamp
- **Core change**: new entrant, rank gain/loss, score delta, usage spike, category win, or pricing-driven adoption
- **Why it changed**: model release, benchmark update, price change, context window, tool use, coding quality, availability
- **Impact**: product choice, API routing, coding workflow, cost strategy, or competitive positioning
- **Confidence**: high when leaderboard source and timestamp are clear; lower when based on secondary summaries

## GitHub Trending Signals

Track GitHub Trending as an early indicator, especially for developer tools, AI agents, infrastructure, and security. Search by relevant languages and topics such as `Python`, `TypeScript`, `Rust`, `Go`, `AI`, `LLM`, `agent`, `RAG`, `MCP`, `security`, and `devtools`.

For each notable repository, capture:

- **Repository**: owner/name and link
- **Category**: AI/ML, Developer Tools, Cloud/Infra, Security, or other
- **Window**: `1w`, `1m`, or `3m`
- **Momentum**: stars gained, forks, release activity, contributors, issue velocity
- **Why it matters**: product category, technical novelty, adoption signal, or ecosystem relevance
- **Caveat**: hype, demo-only status, weak maintenance, unclear license, or duplicated project

## Monitoring Categories

### AI/ML

- Models: OpenAI, Anthropic, Google Gemini, Meta Llama, Mistral, xAI, DeepSeek
- Agent frameworks: LangChain, LangGraph, AutoGen, CrewAI, OpenAI Agents SDK
- Capabilities: multimodal AI, coding agents, RAG, long context, reasoning, evaluation
- Business signals: AI startup funding, enterprise adoption, AI pricing, AI regulation
- Benchmarks and reranking: LMArena/Text Arena, Artificial Analysis, LiveBench, SWE-bench, OpenRouter, model cards, eval reports

### Developer Tools

- Coding assistants: Codex, GitHub Copilot, Cursor, Claude Code, Windsurf
- Dev platforms: GitHub, GitLab, Linear, Vercel, Netlify, Supabase
- Tooling: CI/CD, observability, testing, package managers, IDE extensions
- GitHub Trending: fast-growing repos, new frameworks, agent tools, MCP servers, CLIs, infra templates

### SaaS/Productivity

- Notion, Slack, Linear, Atlassian, Salesforce, HubSpot, Microsoft 365, Google Workspace
- AI features, workflow automation, collaboration, pricing, enterprise adoption

### Cloud/Infrastructure

- AWS, Azure, Google Cloud, Cloudflare, Docker, Kubernetes, serverless, databases
- GPU supply, inference platforms, edge compute, cost optimization

### Security/Privacy

- Vulnerabilities, supply-chain attacks, identity, compliance, AI safety, data governance

### Startup/Funding

- Seed to IPO funding, acquisitions, shutdowns, category creation, Korean startups, global AI startups

### OpenClaw Ecosystem

- Anthropic announcements, Claude API updates, community showcases, OpenClaw, HarnessClaw

## Scoring Criteria

| Score | Meaning | Criteria |
|-------|---------|----------|
| 9-10 | Critical | Industry-wide shift, immediate action needed, major platform or regulation change |
| 7-8 | High | Major company move, strong adoption signal, pricing or capability change |
| 5-6 | Medium | Useful signal, early traction, worth monitoring |
| 1-4 | Low | Minor update, rumor, narrow relevance |

Raise the score when a trend affects roadmap, budget, hiring, compliance, open-source adoption, or competitive positioning. Lower it when evidence is weak, duplicated, only speculative, or based only on short-lived GitHub hype.

## Report Format

Use this structure for readable output:

```markdown
# Trend Radar YYYY-WXX

**Period**: YYYY-MM-DD to YYYY-MM-DD  
**Window**: 1w / 1m / 3m  
**Generated**: YYYY-MM-DD  
**Scope**: AI/ML, Developer Tools, SaaS, Cloud/Infra, Security, Startup/Funding, OpenClaw  
**Signal Count**: 00 reviewed, 00 selected

## Executive Summary

- **1w signal**: ...
- **1m signal**: ...
- **3m signal**: ...
- **Model reranking**: ...
- **Biggest opportunity**: ...
- **Biggest risk**: ...
- **Recommended action**: ...

## Top Signals

| Rank | Signal | Category | Window | Score | Status | Why It Matters |
|------|--------|----------|--------|-------|--------|----------------|
| 1 | ... | AI/ML | 1w | 9 | Confirmed | ... |
| 2 | ... | Developer Tools | 1m | 8 | Confirmed | ... |
| 3 | ... | SaaS | 3m | 7 | Watch | ... |

## GitHub Trending Watch

| Repository | Category | Window | Momentum | Why It Matters | Caveat |
|------------|----------|--------|----------|----------------|--------|
| owner/repo | AI/ML | 1w | +000 stars, 0 releases | ... | ... |
| owner/repo | Developer Tools | 1m | +000 stars, active issues | ... | ... |

## Model Reranking Watch

**Leaderboard**: LMArena / Artificial Analysis / LiveBench / SWE-bench / OpenRouter  
**Checked**: YYYY-MM-DD HH:MM TZ  

| Rank | Model | Provider | Metric | Change | Core Reason |
|------|-------|----------|--------|--------|-------------|
| 1 | ... | ... | score / usage | +0 | ... |
| 2 | ... | ... | score / usage | -1 | ... |
| 3 | ... | ... | score / usage | new | ... |
| 4 | ... | ... | score / usage | 0 | ... |
| 5 | ... | ... | score / usage | +2 | ... |

## Action Items

- [ ] ...
- [ ] ...
- [ ] ...

## Category Deep Dive

### AI/ML

#### [Signal Title]

- **Score**: 9/10
- **Status**: Confirmed / Watch / Rumor
- **Window**: 1w / 1m / 3m
- **What changed**: ...
- **Why it matters**: ...
- **Evidence**: [Source name](URL), [Source name](URL)
- **Model reranking**: leaderboard, rank, score/usage, change reason if relevant
- **GitHub signal**: repo link, stars/forks/releases if relevant
- **Impact window**: immediate / 1-3 months / 6-12 months
- **Watch next**: ...

### Developer Tools

#### [Signal Title]

- **Score**: 8/10
- **Status**: Confirmed
- **Window**: 1w / 1m / 3m
- **What changed**: ...
- **Why it matters**: ...
- **Evidence**: [Source name](URL)
- **Model reranking**: leaderboard, rank, score/usage, change reason if relevant
- **GitHub signal**: repo link, stars/forks/releases if relevant
- **Impact window**: ...
- **Watch next**: ...

## Weekly Stats

| Category | 1w Signals | 1m Signals | 3m Signals | Selected | Critical |
|----------|------------|------------|------------|----------|----------|
| AI/ML | 00 | 00 | 00 | 00 | 00 |
| Developer Tools | 00 | 00 | 00 | 00 | 00 |
| SaaS | 00 | 00 | 00 | 00 | 00 |

## Watchlist for Next Week

- [ ] ...
- [ ] ...
- [ ] ...

## Sources Reviewed

- [Source](URL) - short note
- [Source](URL) - short note

---

Generated by `trend-radar`.
```

## Writing Guidelines

- Lead with the conclusion, then provide evidence.
- Keep each signal compact: one short paragraph or 4-6 bullets.
- Use tables for comparison, especially across `1w`, `1m`, and `3m` windows.
- Include links for every important claim.
- For model reranking, include the leaderboard name, timestamp, metric definition, and current top 10.
- Include GitHub repository links for open-source signals.
- Avoid hype words unless the evidence supports them.
- Do not mix facts and speculation. Use `Confirmed`, `Watch`, or `Rumor`.
- When data is missing, say what is missing and how that affects confidence.

## Output Location

Save reports to:

```text
memory/research/trend-YYYY-WXX.md
```

If the user requests a different scope, include it in the filename:

```text
memory/research/trend-ai-agents-YYYY-WXX.md
memory/research/trend-ai-agents-1m-YYYY-MM.md
memory/research/trend-ai-agents-3m-YYYY-QN.md
```

## Cron Setup Example

Run every Monday at 09:00:

```bash
0 9 * * 1 openclaw run trend-radar
```

## Event Bus Integration

When a report is generated, publish:

```text
events/trend-update-YYYY-MM-DD.json
```

Format:

```json
{
  "type": "trend-report-generated",
  "timestamp": "2026-02-14T09:00:00Z",
  "week": "2026-W07",
  "window": "1w",
  "scope": ["AI/ML", "Developer Tools", "SaaS"],
  "highlights": [
    {
      "title": "...",
      "score": 9,
      "category": "AI/ML",
      "status": "Confirmed",
      "window": "1w"
    }
  ],
  "githubTrending": [
    {
      "repository": "owner/repo",
      "category": "Developer Tools",
      "window": "1w",
      "momentum": "+000 stars"
    }
  ],
  "modelReranking": {
    "leaderboard": "LMArena Text Arena Overall",
    "checkedAt": "2026-04-15T00:00:00Z",
    "top10": [
      {
        "rank": 1,
        "model": "...",
        "provider": "...",
        "metric": "..."
      }
    ],
    "coreChanges": ["..."]
  },
  "signalsReviewed": 96,
  "signalsSelected": 12,
  "criticalSignals": 3
}
```

## Customization

Edit keyword configuration at:

```text
workspace/trend-radar-keywords.json
```

Example:

```json
{
  "AI/ML": ["OpenAI", "Claude", "Gemini", "Llama", "AI agents", "SWE-bench", "model reranking"],
  "Model Reranking": ["LMArena", "Text Arena", "Artificial Analysis", "LiveBench", "SWE-bench", "OpenRouter rankings", "top 10 AI models"],
  "Developer Tools": ["Codex", "GitHub Copilot", "Cursor", "Vercel", "LangGraph", "GitHub Trending"],
  "GitHub Trending": ["AI", "LLM", "agent", "RAG", "MCP", "devtools", "security", "TypeScript", "Python", "Rust", "Go"],
  "SaaS": ["Notion AI", "Linear", "Slack AI"],
  "OpenClaw": ["OpenClaw", "HarnessClaw", "Claude API"],
  "windows": ["1w", "1m", "3m"]
}
```

Keep keyword lists specific enough to reduce noise, but broad enough to catch new product names and adjacent market shifts.
