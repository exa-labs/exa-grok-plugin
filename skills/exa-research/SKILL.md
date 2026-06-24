---
name: exa-research
description: |
  Advanced web research with category filters, domain restrictions, date ranges,
  and content controls. Use for company research, people search, news monitoring,
  academic papers, financial reports, or any search requiring precise filtering.
  This skill uses web_search_advanced_exa.
allowed-tools:
  - mcp__exa__web_search_advanced_exa
  - mcp__exa__web_fetch_exa
---

# Exa Research

Use `web_search_advanced_exa` for filtered, structured research. Exa indexes
50M+ companies, 1B+ people profiles, 100M+ research papers, and specialized
collections of news, financial reports, and personal sites.

## Categories

| Category | Index size | Best for |
|---|---|---|
| `company` | 50M+ pages | Company discovery, metadata (headcount, funding, revenue, industry) |
| `people` | 1B+ profiles | LinkedIn profiles, professional backgrounds, hiring |
| `news` | Live | Press coverage, announcements, current events |
| `research paper` | 100M+ papers | arXiv, OpenReview, PubMed, scientific literature |
| `financial report` | — | SEC filings (10-K, 10-Q, 8-K, S-1), earnings reports |
| `personal site` | — | Blogs, portfolios, independent analysis |
| _(no category)_ | Full web | General results when you don't know the surface |

## Company research

```
web_search_advanced_exa {
  "query": "AI infrastructure startups Series A San Francisco",
  "category": "company",
  "numResults": 25,
  "type": "auto"
}
```

Returns company pages with structured metadata. For deeper enrichment, use
`type: "deep"` to get synthesized profiles across multiple sources.

**Restrictions with `company` category:** `includeDomains`, `excludeDomains`,
`startPublishedDate`, `endPublishedDate` are NOT supported — use natural
language in the query instead (e.g. "founded after 2023").

## People search

```
web_search_advanced_exa {
  "query": "VP Engineering machine learning Bay Area",
  "category": "people",
  "numResults": 20,
  "type": "auto"
}
```

Searches across LinkedIn and other professional sources.

**Restrictions with `people` category:** Only `includeDomains` with LinkedIn
domains is supported. Date filters, `excludeDomains`, `includeText`,
`excludeText` are NOT supported.

## News

```
web_search_advanced_exa {
  "query": "Anthropic AI safety regulation",
  "category": "news",
  "numResults": 15,
  "startPublishedDate": "2026-01-01"
}
```

Supports full filtering — domain, date, text inclusion/exclusion.

## Research papers

```
web_search_advanced_exa {
  "query": "transformer attention mechanisms efficiency",
  "category": "research paper",
  "includeDomains": ["arxiv.org", "openreview.net"],
  "startPublishedDate": "2025-01-01",
  "numResults": 20,
  "type": "deep"
}
```

Full filter support. Good for literature reviews and finding recent work.

## Financial reports

```
web_search_advanced_exa {
  "query": "Q4 2025 earnings report technology",
  "category": "financial report",
  "startPublishedDate": "2025-10-01",
  "numResults": 20
}
```

**Restriction:** `excludeText` is NOT supported for this category.

## General filtered search (no category)

When you don't need a specific vertical, drop the category and use domain/date
filters for precision:

```
web_search_advanced_exa {
  "query": "React server components best practices",
  "type": "deep",
  "numResults": 10,
  "includeDomains": ["react.dev", "github.com", "vercel.com"],
  "startPublishedDate": "2025-06-01"
}
```

## Search types

| Type | Latency | Use case |
|---|---|---|
| `auto` | ~1s | Default, balanced |
| `instant` | ~250ms | Real-time chat, voice |
| `fast` | ~450ms | Speed-sensitive workflows |
| `deep` | 4-15s | Complex queries, structured output |
| `deep-reasoning` | 12-40s | Maximum reasoning for hard research |

## Global filter restrictions

- `includeText` and `excludeText` accept **single-item arrays only** — multi-item
  arrays cause 400 errors. Put multiple terms in the query string instead.
- For coverage, use `additionalQueries` to run 2-3 query variations in parallel.

## Query tips

- Write semantic queries, not keyword strings
- For coverage: use `additionalQueries` with phrasing variations
- Start with a category for discovery, drop it for broader context
- Use `enableHighlights: true` + `highlightsQuery` to extract specific passages
- Use `enableSummary: true` + `summaryQuery` to get targeted summaries
