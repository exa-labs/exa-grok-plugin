---
name: exa-code-search
description: |
  Find code examples, API docs, library references, and technical solutions.
  Use when searching for code snippets, API syntax, SDK usage, framework patterns,
  debugging help, or when the user says "how do I use", "code example for",
  "API reference for". Returns real code from GitHub, docs sites, and StackOverflow.
allowed-tools:
  - mcp__exa__web_search_exa
  - mcp__exa__web_fetch_exa
---

# Exa Code Search

Find real code snippets, API references, and technical documentation.

## Usage

```
web_search_exa {
  "query": "Python asyncio gather exception handling pattern",
  "numResults": 10
}
```

## Query patterns

Always include the **programming language** in the query to avoid cross-language
noise:

- "Go generics type constraint example" (not "generics example")
- "Rust tokio spawn blocking vs spawn" (not "async blocking")
- "Next.js 14 server actions form validation" (not "form validation")

Include exact identifiers when you have them — function names, class names,
config keys, error messages:

- "React useOptimistic hook with server action"
- "psycopg3 async connection pool example"
- "CUDA error 719 launch failure debug"

## Workflow

1. Search with a specific query including language + framework + version
2. Scan returned snippets — Exa returns text content inline, not just links
3. Fetch the full page with `web_fetch_exa` if you need more context
4. Extract the minimal working snippet and note version/constraints

## When to use exa-research instead

For domain-restricted technical searches (e.g., only results from `react.dev`
and `github.com`), use the `exa-research` skill with `includeDomains`.
