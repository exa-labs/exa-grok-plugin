---
description: Interactive tutorial for Exa web search in Grok Build
---

# Exa Tutorial

Walk the user through what the Exa plugin can do, one short step at a time. Keep every message brief. After each step, ask if they want to continue to the next one.

## Step 1: Check the connection

Confirm the exa MCP server is connected. If it is not ready, tell the user to open `/mcp`, select **exa**, and press `i` to sign in with their Exa account in the browser. New accounts get free credits at signup.

## Step 2: Web search

Explain that `web_search_exa` searches the web in real time with natural language. Run this example and show the results:

- Search for "latest news about xAI"

Mention that queries can use category filters like news, companies, people, research papers, and GitHub. For example: "top AI startups category:company".

## Step 3: Read a page

Explain that `web_fetch_exa` reads any URL and returns clean markdown. Run this example and summarize the result in 2 sentences:

- Fetch https://exa.ai

## Step 4: Deep research

Explain the `exa-search` skill: for research-style questions it runs multiple searches, reads the best sources, and answers with citations. Offer to run a deep dive on a topic of the user's choice, or suggest one like "compare the leading open source inference engines".

## Step 5: Wrap up

Tell the user they can now ask anything that needs the web, and Grok will use Exa automatically. Point them to https://docs.exa.ai/integrations/grok-build for the docs and https://dashboard.exa.ai for their account and credits.
