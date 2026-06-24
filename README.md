# Exa Plugin for Grok Build

Search the web, extract content, and do deep research — directly from Grok Build.

This plugin bundles Exa's hosted [MCP server](https://github.com/exa-labs/exa-mcp-server) plus a set of skills, giving Grok Build the ability to search the web, read pages, and do structured research across companies, people, news, and more. Installing the plugin wires up the MCP automatically — the first search action signs you in through your browser, with no API key to paste.

**The hosted MCP is the primary way this plugin works** — its native `web_search_exa`, `web_search_advanced_exa`, and `web_fetch_exa` tools are the default execution path for every search operation.

## Features

- **Search** — Web search with clean, LLM-ready results
- **Advanced Search** — Category filters (company, people, news, research papers, financial reports), domain restrictions, date ranges, highlights, summaries, and subpage crawling
- **Fetch** — Read any webpage's full content as clean markdown with JavaScript rendering

All searches include automatic content extraction and ranking powered by Exa's search engine.

## Installation

### 1. Install the Plugin

In Grok Build, run `/plugin` and search for **exa**, then select it to install. This installs both the skills and the bundled Exa MCP server.

### 2. Sign In

The first time Grok uses an Exa tool, you'll be prompted to authorize in your browser (OAuth). Approve it once — no API key to copy or paste. You can also check the connection any time with `/mcp`.

**That's it.** No global npm install, no manual key management.

### Optional: API Key

For programmatic use or higher rate limits, get a free API key at [dashboard.exa.ai](https://dashboard.exa.ai/api-keys). Exa has a generous free tier.

## Usage

Once installed, Grok Build automatically uses Exa's MCP tools for web tasks. Just ask naturally:

**Search the web:**

```text
Search for "best practices for React testing" and summarize the key points
```

**Read a page:**

```text
Read https://docs.exa.ai and give me the highlights
```

**Company research:**

```text
Find AI infrastructure startups in San Francisco and list their funding info
```

**People search:**

```text
Find machine learning engineers at top AI labs
```

**News:**

```text
What are the latest developments in AI agents this week?
```

## Skills

| Skill | Description |
|---|---|
| `exa-search` | General web search and page reading |
| `exa-research` | Deep research with category filters, domain restrictions, date ranges |
| `exa-fetch` | Read a webpage's full content as clean markdown |

## Resources

- [Exa Documentation](https://docs.exa.ai)
- [Exa MCP Server](https://github.com/exa-labs/exa-mcp-server)
- [API Reference](https://docs.exa.ai/reference/search-api-guide)
- [Get API Key](https://dashboard.exa.ai/api-keys)

## License

MIT

## Support

- [Exa Discord](https://discord.gg/exa)
- [GitHub Issues](https://github.com/exa-labs/exa-mcp-server/issues)
- Email: hello@exa.ai
