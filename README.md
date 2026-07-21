# Exa Plugin for Grok Build

Search the web, research companies and people, find code, and read pages directly from Grok Build.

This plugin connects Grok Build to [Exa](https://exa.ai), a search engine built for AI agents. Exa indexes the full web plus specialized collections: 50M+ company pages, 1B+ people profiles, 100M+ research papers, financial reports, and news. The plugin uses Exa's hosted [MCP server](https://github.com/exa-labs/exa-mcp-server). Install it once, sign in to your Exa account in the browser, and it works automatically.

## Installation

1. Install Grok Build (see the [Grok Build docs](https://docs.x.ai/build/overview) for details):

```bash
curl -fsSL https://x.ai/cli/install.sh | bash
```

2. Sign in to your xAI account:

```bash
grok login
```

3. Start Grok Build by running `grok`, then open the marketplace:

```text
/marketplace
```

4. Find **exa** in the list and press `i` to install it.

5. Open the MCP servers tab with `/mcp`, select **exa**, and press `i` to sign in. Your browser opens the Exa sign-in page. New accounts get free credits at signup.

6. Once exa shows **ready**, ask Grok anything that needs the web.

## Tools

| Tool | What it does |
|---|---|
| `web_search_exa` | Semantic web search with inline category filters (`category:company`, `category:people`, `category:research paper`, ...) |
| `web_fetch_exa` | Read any webpage as clean markdown |

## Skills

| Skill | What it does |
|---|---|
| `exa-search` | Research orchestrator: plans the work, runs parallel searches with category filters, and compiles deduplicated, cited results |

## Resources

- [Documentation](https://docs.exa.ai)
- [API Reference](https://docs.exa.ai/reference/search-api-guide)
- [MCP Server](https://github.com/exa-labs/exa-mcp-server)
- [Benchmarks](https://github.com/exa-labs/benchmarks)
- [Blog](https://exa.ai/blog)
- [Get API Key](https://dashboard.exa.ai/api-keys)
