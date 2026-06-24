---
name: exa-fetch
description: |
  Read a webpage's full content as clean markdown. Use when the user provides
  a URL, when you need the full text of a search result, or when the user says
  "read this page", "get the content of", "what does this page say".
allowed-tools:
  - mcp__exa__web_fetch_exa
---

# Exa Fetch

Read any webpage as clean, LLM-ready markdown with `web_fetch_exa`.

```
web_fetch_exa {
  "url": "https://docs.exa.ai/reference/search-api-guide"
}
```

Returns the page content with boilerplate, navigation, and ads stripped.
Handles JavaScript-rendered pages.

## When to use

- User shares a URL and wants it summarized or analyzed
- You found a promising search result and need the full text
- You need to verify a claim by reading the source

## Tips

- Combine with `exa-search` or `exa-research`: search first, fetch the
  best results for deeper reading
- For multiple pages on the same topic, fetch each and synthesize across them
- If fetch returns truncated content, the page may be very long — focus on
  the section most relevant to the user's question
