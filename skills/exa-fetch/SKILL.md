---
name: exa-fetch
description: |
  Read a webpage's full content as clean markdown. Use this skill when the user
  provides a URL and wants its content, or when you need to read the full text
  of a page found via search.
allowed-tools:
  - mcp__exa__web_fetch_exa
---

# Exa Fetch

## Via the Exa MCP (preferred)

This plugin bundles the Exa MCP server. Use the **`web_fetch_exa`** tool to read any webpage's content as clean, LLM-ready markdown.

## When to use

- User shares a URL and wants its content summarized or analyzed
- You found a promising search result and need the full text
- You need to extract structured data from a webpage

## Usage

```
web_fetch_exa {
  "url": "https://example.com/article"
}
```

Returns the page content as clean markdown, with boilerplate and navigation stripped.

## Tips

- Works on most public web pages — articles, docs, blog posts, forums
- Handles JavaScript-rendered pages
- Returns clean markdown, not raw HTML
- Combine with `exa-search` or `exa-research` for a full research workflow
