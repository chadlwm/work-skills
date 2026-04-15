---
name: tech-trend-radar
description: Use when generating current technology, product, startup, funding, regulation, or market trend reports from recent industry updates
author: Chad Liu
---

# Trend Radar

Generate a weekly industry trend report from recent, credible technology and market updates. Prioritize fresh signals, source quality, business impact, and clear next actions.

## When to Use

Use this skill when the user asks for:

- Weekly or recent technology trends
- AI, SaaS, developer tools, cloud, security, startup, or regulation updates
- Market signal summaries for planning, investing, product strategy, or competitive tracking
- A concise report that distinguishes major shifts from ordinary news

Trigger examples:

```text
Write this week's AI trend report
Generate a trend radar for developer tools
Summarize recent market trends in AI agents
What changed in SaaS and AI this week?
```

## Research Workflow

1. Define the report period. Default to the last 7 days unless the user specifies a date range.
2. Search by category, not only by generic keywords. Combine company names, product names, ecosystem terms, and event types.
3. Prefer primary and high-signal sources before commentary.
4. Cross-check major claims with at least two credible sources when possible.
5. Deduplicate repeated coverage of the same announcement.
6. Score each item by novelty, impact, source quality, and actionability.
7. Separate confirmed facts from interpretation. Label uncertain items as `Watch`.

## Source Priority

Use higher-priority sources first:

| Priority | Source Type | Examples |
|----------|-------------|----------|
| 1 | Official announcements | company blogs, product release notes, API changelogs, pricing pages |
| 1 | Primary technical artifacts | GitHub releases, RFCs, benchmark reports, model cards, research papers |
| 2 | Business records | funding announcements, acquisition news, earnings calls, regulatory filings |
| 2 | Trusted industry media | The Verge, TechCrunch, The Information, Stratechery, VentureBeat, The Pragmatic Engineer |
| 3 | Community signals | Hacker News, Reddit, X posts, Discord/Slack communities, GitHub stars/issues |

Community signals should support a trend, not be the only evidence for a high-impact claim.

## Monitoring Categories

### AI/ML

- Models: OpenAI, Anthropic, Google Gemini, Meta Llama, Mistral, xAI, DeepSeek
- Agent frameworks: LangChain, LangGraph, AutoGen, CrewAI, OpenAI Agents SDK
- Capabilities: multimodal AI, coding agents, RAG, long context, reasoning, evaluation
- Business signals: AI startup funding, enterprise adoption, AI pricing, AI regulation
- Benchmarks: LMSYS, SWE-bench, Artificial Analysis, model cards, eval reports

### Developer Tools

- Coding assistants: Codex, GitHub Copilot, Cursor, Claude Code, Windsurf
- Dev platforms: GitHub, GitLab, Linear, Vercel, Netlify, Supabase
- Tooling: CI/CD, observability, testing, package managers, IDE extensions

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

Raise the score when a trend affects roadmap, budget, hiring, compliance, or competitive positioning. Lower it when evidence is weak, duplicated, or only speculative.

## Report Format

Use this structure for readable output:

```markdown
# Trend Radar YYYY-WXX

**Period**: YYYY-MM-DD to YYYY-MM-DD  
**Generated**: YYYY-MM-DD  
**Scope**: AI/ML, Developer Tools, SaaS, Cloud/Infra, Security, Startup/Funding, OpenClaw  
**Signal Count**: 00 reviewed, 00 selected

## Executive Summary

- **Main shift**: ...
- **Biggest opportunity**: ...
- **Biggest risk**: ...
- **Recommended action**: ...

## Top Signals

| Rank | Signal | Category | Score | Status | Why It Matters |
|------|--------|----------|-------|--------|----------------|
| 1 | ... | AI/ML | 9 | Confirmed | ... |
| 2 | ... | Developer Tools | 8 | Confirmed | ... |
| 3 | ... | SaaS | 7 | Watch | ... |

## Action Items

- [ ] ...
- [ ] ...
- [ ] ...

## Category Deep Dive

### AI/ML

#### [Signal Title]

- **Score**: 9/10
- **Status**: Confirmed / Watch / Rumor
- **What changed**: ...
- **Why it matters**: ...
- **Evidence**: [Source name](URL), [Source name](URL)
- **Impact window**: immediate / 1-3 months / 6-12 months
- **Watch next**: ...

### Developer Tools

#### [Signal Title]

- **Score**: 8/10
- **Status**: Confirmed
- **What changed**: ...
- **Why it matters**: ...
- **Evidence**: [Source name](URL)
- **Impact window**: ...
- **Watch next**: ...

## Weekly Stats

| Category | Signals Reviewed | Selected | Critical | vs Last Period |
|----------|------------------|----------|----------|----------------|
| AI/ML | 00 | 00 | 00 | +0% |
| Developer Tools | 00 | 00 | 00 | +0% |
| SaaS | 00 | 00 | 00 | +0% |

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
- Use tables for comparison and bullets for analysis.
- Include links for every important claim.
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
  "scope": ["AI/ML", "Developer Tools", "SaaS"],
  "highlights": [
    {
      "title": "...",
      "score": 9,
      "category": "AI/ML",
      "status": "Confirmed"
    }
  ],
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
  "AI/ML": ["OpenAI", "Claude", "Gemini", "Llama", "AI agents", "SWE-bench"],
  "Developer Tools": ["Codex", "GitHub Copilot", "Cursor", "Vercel", "LangGraph"],
  "SaaS": ["Notion AI", "Linear", "Slack AI"],
  "OpenClaw": ["OpenClaw", "HarnessClaw", "Claude API"]
}
```

Keep keyword lists specific enough to reduce noise, but broad enough to catch new product names and adjacent market shifts.
