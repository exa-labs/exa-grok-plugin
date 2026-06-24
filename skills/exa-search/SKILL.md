---
name: exa-search
description: |
  Search the web and read pages. Use whenever the user asks to search, look up,
  find information, research a topic, find recent news, or says "search for",
  "find me", "look up", "what's happening with". Exa uses semantic search —
  write natural language queries, not keyword strings.
allowed-tools:
  - mcp__exa__web_search_exa
  - mcp__exa__web_fetch_exa
---

# Exa Search

Search the web with `web_search_exa`. Read a specific page with `web_fetch_exa`.

## Search

```
web_search_exa {
  "query": "how Next.js app router handles server components",
  "numResults": 10
}
```

Write queries as natural language descriptions of what you want to find. Exa
ranks by semantic relevance — "companies building autonomous vehicles in Detroit"
works better than "autonomous vehicle company Detroit".

## Fetch

Read the full content of a URL as clean markdown:

```
web_fetch_exa {
  "url": "https://react.dev/blog/2024/12/05/react-19"
}
```

Use after search to get the full text of a promising result.

## Workflow

1. Search to find relevant pages
2. Fetch specific results when you need more than the snippet
3. Synthesize across sources

## When to escalate to exa-research

Use the `exa-research` skill instead when you need:
- Category filters (company, people, news, papers, financial reports)
- Domain restrictions (`includeDomains` / `excludeDomains`)
- Date range filters
- Highlights or summaries
