---
name: exa-search
description: |
  Web search with clean, ready-to-use content. Use this skill whenever the user
  asks to search the web, find information, research a topic, look something up,
  find recent news, discover sources, or says "search for", "find me", "look up",
  "what are people saying about", or "find articles about".
allowed-tools:
  - mcp__exa__web_search_exa
  - mcp__exa__web_fetch_exa
---

# Exa Search

## Via the Exa MCP (preferred)

This plugin bundles the Exa MCP server. When connected, use the native **`web_search_exa`** tool for general search and **`web_fetch_exa`** to read a specific page's full content as clean markdown.

## When to use

- You need to find pages, answer questions, or discover sources
- You want clean, LLM-ready content from web search results
- You need to look up recent information, news, or documentation

## How it works

**`web_search_exa`** — Search the web for any topic. Returns clean, relevant results with text content.

```
web_search_exa {
  "query": "your search query",
  "numResults": 10
}
```

**`web_fetch_exa`** — Read the full content of a specific webpage as clean markdown.

```
web_fetch_exa {
  "url": "https://example.com/page"
}
```

## Workflow

1. **Search first** — use `web_search_exa` to find relevant pages
2. **Fetch if needed** — use `web_fetch_exa` to read the full content of a specific result
3. **Synthesize** — combine the information into a clear answer

## Tips

- Write natural language queries — Exa understands semantic meaning, not just keywords
- For broad research, start with a general query and refine based on results
- Use `web_fetch_exa` when you need more detail than the search snippet provides
