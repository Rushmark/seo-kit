# AGENTS.md - SEO Kit

## Skills

### seo-agent
**Purpose:** Keyword discovery, ranking monitoring, competitor gap analysis
**Scripts:** seo-discover.sh, seo-monitor.sh, seo-compete.sh
**Data Sources:** Google Search Console API, DataForSEO API
**Schedule:** Weekly (Monday discover + monitor, Friday compete)

### seo-forge
**Purpose:** Brand-voice content generation with psychology frameworks
**Scripts:** seo-interview.sh, seo-research.sh, seo-check.sh
**Modes:** Interview (new brands), Refinement (weekly), Default (no brand context)
**Output:** Draft articles in markdown with frontmatter (title, keywords, schema)

### seo-checklist
**Purpose:** Technical SEO reference (meta tags, schema, llms.txt, topical authority)
**Type:** Reference document, not executable
**Usage:** Agent consults this when publishing or auditing pages

## Workflow

```
1. seo-check.sh      → Verify GSC + DataForSEO connections
2. seo-interview.sh  → Build brand voice (first run only)
3. seo-discover.sh   → Find keyword opportunities
4. seo-forge SKILL   → Write content targeting top opportunities
5. seo-monitor.sh    → Track what ranked, find strike zone pushes
6. seo-compete.sh    → Competitor gap analysis
7. Repeat 3-6 weekly
```

## Data Files

| File | Purpose |
|------|---------|
| `workspace/brand/voice-profile.md` | Brand voice from interview |
| `workspace/brand/audience.md` | Target audience profile |
| `workspace/brand/positioning.md` | Competitive positioning |
| `workspace/seo/rankings-snapshot.json` | Latest ranking data |
| `workspace/seo/opportunities.json` | Prioritized keyword list |
| `workspace/seo/competitor-gaps.json` | Keywords competitors have that you don't |
