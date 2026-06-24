---
name: exa-people-search
description: |
  Find people by role, company, location, or expertise. Use when the user asks
  to find people, look up professionals, search LinkedIn, find experts, build
  a prospect list, or research someone's background. Exa indexes 1B+ people
  profiles across LinkedIn and other professional sources.
allowed-tools:
  - mcp__exa__web_search_advanced_exa
  - mcp__exa__web_fetch_exa
---

# Exa People Search

Exa's people index covers 1B+ profiles across LinkedIn and professional
sources, with metadata including job title, company, education, and location.

## Find people by role

```
web_search_advanced_exa {
  "query": "VP Engineering AI infrastructure San Francisco",
  "category": "people",
  "numResults": 20,
  "type": "auto"
}
```

## With query variations for broader coverage

```
web_search_advanced_exa {
  "query": "machine learning engineer San Francisco",
  "category": "people",
  "additionalQueries": ["ML engineer SF", "AI engineer Bay Area"],
  "numResults": 25,
  "type": "deep"
}
```

## Research a specific person

Drop the category to search the full web:

```
web_search_advanced_exa {
  "query": "Dario Amodei Anthropic CEO background",
  "type": "auto",
  "numResults": 15
}
```

## Find mentions in press

```
web_search_advanced_exa {
  "query": "Dario Amodei interview",
  "category": "news",
  "numResults": 10,
  "startPublishedDate": "2026-01-01"
}
```

## Multi-step workflow

1. **Discover** with `category: "people"` — find profiles
2. **Context** without category — broader background
3. **News** with `category: "news"` — recent mentions
4. **Fetch** individual pages for full detail

## Category restrictions

When using `category: "people"`:
- Date filters — NOT supported
- `excludeDomains` — NOT supported
- `includeText` / `excludeText` — NOT supported
- `includeDomains` — **only LinkedIn domains** (e.g., "linkedin.com")

Drop the category for unrestricted filtering on a specific person.
