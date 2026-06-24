---
name: exa-company-research
description: |
  Research companies, find competitors, analyze markets, and build company lists.
  Use when the user asks to research a company, find competitors, do market
  analysis, build a company list, find startups in a space, or look up funding
  and headcount data. Exa indexes 50M+ company pages with structured metadata.
allowed-tools:
  - mcp__exa__web_search_advanced_exa
  - mcp__exa__web_fetch_exa
---

# Exa Company Research

Exa's company index covers 50M+ company pages — homepages, LinkedIn company
profiles, Crunchbase entries — with metadata including headcount, location,
funding, revenue, and industry classification.

## Discovery: find companies in a space

```
web_search_advanced_exa {
  "query": "AI infrastructure startups San Francisco",
  "category": "company",
  "numResults": 25,
  "type": "auto"
}
```

## Deep dive: research a specific company

Drop the category to search the full web. Use `includeDomains` to focus:

```
web_search_advanced_exa {
  "query": "Anthropic funding rounds valuation 2025",
  "type": "deep",
  "numResults": 10,
  "includeDomains": ["techcrunch.com", "crunchbase.com", "bloomberg.com"]
}
```

## News coverage

```
web_search_advanced_exa {
  "query": "Anthropic AI safety",
  "category": "news",
  "numResults": 15,
  "startPublishedDate": "2026-01-01"
}
```

## Competitive landscape

Use `additionalQueries` for broader coverage:

```
web_search_advanced_exa {
  "query": "vector database companies funding 2025",
  "additionalQueries": ["embedding search startups", "semantic search companies"],
  "category": "company",
  "numResults": 30,
  "type": "auto"
}
```

## Multi-step workflow

1. **Discover** with `category: "company"` — get the list
2. **Enrich** without category + `type: "deep"` — get detailed profiles
3. **News** with `category: "news"` + date filter — get recent coverage
4. **Fetch** specific pages for full content

## Category restrictions

When using `category: "company"`:
- `includeDomains` / `excludeDomains` — NOT supported
- `startPublishedDate` / `endPublishedDate` — NOT supported
- Use natural language instead: "founded after 2023", "Series B+"

These filters work fine when searching without a category.
