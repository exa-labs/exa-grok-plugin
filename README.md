# Exa Plugin for Grok Build

Search the web, research companies and people, find code, and read pages — directly from Grok Build.

This plugin connects Grok Build to [Exa](https://exa.ai), a search engine built for AI agents. Exa indexes the full web plus specialized collections: 50M+ company pages, 1B+ people profiles, 100M+ research papers, financial reports, and news. The plugin bundles Exa's hosted [MCP server](https://github.com/exa-labs/exa-mcp-server) — install it once, sign in to your Exa account in the browser, and it works automatically.

## What makes Exa different

Exa is a search engine, not a scraper. Where other tools crawl pages you already know about, Exa *finds* the right pages in the first place — ranking by semantic relevance across specialized indexes.

- **Category search** — query 50M+ companies, 1B+ people profiles, 100M+ papers, news, and financial reports as structured verticals, not generic web results
- **Semantic ranking** — natural language queries ("AI startups in Detroit building autonomous vehicles") outperform keyword strings
- **Content extraction** — `web_fetch_exa` reads any page as clean markdown with JS rendering

**Benchmarks** ([exa-labs/benchmarks](https://github.com/exa-labs/benchmarks)): Exa leads on RAG groundedness (79.4% vs Brave 76.3%, Tavily 61.1%), people search recall (R@10: 94.5% vs Brave 77.9%), and code content extraction (ROUGE-L: 83.2 vs next-best 73.7).

## Installation

In Grok Build, run `/plugin` and search for **exa**, then select it to install.

On first connection, Grok prompts you to sign in to your Exa account in the browser (OAuth). No API key to paste — new accounts get free credits at signup.

## Tools

| Tool | What it does |
|---|---|
| `web_search_exa` | Semantic web search with inline category filters (`category:company`, `category:people`, `category:research paper`, ...) |
| `web_fetch_exa` | Read any webpage as clean markdown |

## Skills

| Skill | What it does |
|---|---|
| `exa-search` | Research orchestrator: plans the work, fans out parallel subagent searches with category filters, compiles deduplicated, cited results |

## Usage

Just ask naturally:

```text
Find AI infrastructure startups in San Francisco and compare their funding
```

```text
Search for the latest research papers on transformer efficiency
```

```text
How do I use Python asyncio gather with exception handling?
```

```text
Read https://react.dev/blog and summarize the latest post
```

## Recent updates

- **[Exa Agent](https://exa.ai/blog/exa-agent)** (June 2026) — frontier web research agents via API, combining model fusion with Exa's search for deep research, list-building, and entity enrichment
- **[Exa Deep revamp](https://exa.ai/blog/exa-deep)** (March 2026) — faster, cheaper deep search with structured outputs and field-level grounding
- **[Exa Instant](https://exa.ai/docs/changelog)** (February 2026) — sub-150ms search with neural quality
- **[Company Search](https://exa.ai/docs/changelog)** (January 2026) — fine-tuned retrieval model for 50M+ companies
- **[People Search](https://exa.ai/docs/changelog)** (January 2026) — 1B+ indexed profiles

## Resources

- [Documentation](https://docs.exa.ai)
- [API Reference](https://docs.exa.ai/reference/search-api-guide)
- [MCP Server](https://github.com/exa-labs/exa-mcp-server)
- [Benchmarks](https://github.com/exa-labs/benchmarks)
- [Blog](https://exa.ai/blog)
- [Get API Key](https://dashboard.exa.ai/api-keys)

## License

MIT
