---
name: exa-research
description: |
  Deep research using Exa advanced search. Use this skill for company research,
  people search, competitive analysis, market research, academic papers, financial
  reports, or any task requiring filtered, structured web search with domain
  restrictions, date ranges, and category filters.
allowed-tools:
  - mcp__exa__web_search_advanced_exa
  - mcp__exa__web_fetch_exa
---

# Exa Research

## Via the Exa MCP (preferred)

This plugin bundles the Exa MCP server. Use the **`web_search_advanced_exa`** tool for research tasks that need precise filtering.

## When to use

- Company research, competitor analysis, market research
- People search (LinkedIn profiles, professional backgrounds)
- Academic paper discovery
- Financial report search (SEC filings, earnings reports)
- Any search requiring domain, date, or category filters

## Available categories

| Category | Best for |
|---|---|
| `company` | Company homepages, metadata (headcount, funding, revenue) |
| `news` | Press coverage, announcements, recent articles |
| `people` | LinkedIn profiles, public bios |
| `personal site` | Personal blogs, portfolio sites |
| `financial report` | SEC filings, earnings reports, investor presentations |
| `research paper` | Academic papers, studies |
| _(no category)_ | General web results, broader context |

## Examples

### Company research
```
web_search_advanced_exa {
  "query": "AI infrastructure startups San Francisco",
  "category": "company",
  "numResults": 20,
  "type": "auto"
}
```

### People search
```
web_search_advanced_exa {
  "query": "VP Engineering AI infrastructure",
  "category": "people",
  "numResults": 20,
  "type": "auto"
}
```

### News with date filter
```
web_search_advanced_exa {
  "query": "Anthropic AI safety",
  "category": "news",
  "numResults": 15,
  "startPublishedDate": "2025-01-01"
}
```

### Domain-restricted deep search
```
web_search_advanced_exa {
  "query": "React server components best practices",
  "type": "deep",
  "numResults": 10,
  "includeDomains": ["react.dev", "github.com", "vercel.com"]
}
```

### Financial reports
```
web_search_advanced_exa {
  "query": "Q4 2025 earnings report technology",
  "category": "financial report",
  "startPublishedDate": "2025-10-01",
  "numResults": 20
}
```

## Category filter restrictions

When using `category: "company"`, these parameters are **not supported**:
- `includeDomains` / `excludeDomains`
- `startPublishedDate` / `endPublishedDate`

When using `category: "people"`, these parameters are **not supported**:
- Date filters, `excludeDomains`, `includeText`, `excludeText`
- `includeDomains` only supports LinkedIn domains

`includeText` and `excludeText` only accept **single-item arrays** across all categories.

## Tips

- Start with `category: "company"` for discovery, then drop the category for deeper dives
- Generate 2-3 query variations for broader coverage, then merge and deduplicate
- Use `type: "deep"` for thorough results when precision matters
- Use `web_fetch_exa` to read full content of promising results
