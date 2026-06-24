# Exa Plugin for Grok Build

Search the web, research companies and people, find code, and read pages — directly from Grok Build.

This plugin connects Grok Build to [Exa](https://exa.ai), a search engine built for AI agents. Exa indexes the full web plus specialized collections: 50M+ company pages, 1B+ people profiles, 100M+ research papers, financial reports, and news. The plugin bundles Exa's hosted [MCP server](https://github.com/exa-labs/exa-mcp-server) — install it once, authorize via browser, and every skill works automatically.

## What makes Exa different

Exa is a search engine, not a scraper. Where other tools crawl pages you already know about, Exa *finds* the right pages in the first place — ranking by semantic relevance across specialized indexes.

- **Category search** — query 50M+ companies, 1B+ people profiles, 100M+ papers, news, and financial reports as structured verticals, not generic web results
- **Semantic ranking** — natural language queries ("AI startups in Detroit building autonomous vehicles") outperform keyword strings
- **Search types for every latency** — from `instant` (~250ms) for chat to `deep-reasoning` (12-40s) for complex research
- **Content extraction** — `web_fetch_exa` reads any page as clean markdown with JS rendering

**Benchmarks** ([exa-labs/benchmarks](https://github.com/exa-labs/benchmarks)): Exa leads on RAG groundedness (79.4% vs Brave 76.3%, Tavily 61.1%), people search recall (R@10: 94.5% vs Brave 77.9%), and code content extraction (ROUGE-L: 83.2 vs next-best 73.7).

## Installation

In Grok Build, run `/plugin` and search for **exa**, then select it to install.

The first time Grok uses an Exa tool, you'll be prompted to authorize in your browser (OAuth). No API key needed. For higher rate limits, get a free key at [dashboard.exa.ai](https://dashboard.exa.ai/api-keys).

## Skills

| Skill | What it does |
|---|---|
| `exa-search` | General web search + page reading |
| `exa-research` | Advanced search with category filters, domain/date restrictions, highlights |
| `exa-company-research` | Company discovery, competitive analysis, market research |
| `exa-people-search` | Find professionals by role, company, location, expertise |
| `exa-code-search` | Find code examples, API docs, library references |
| `exa-fetch` | Read any webpage as clean markdown |

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
