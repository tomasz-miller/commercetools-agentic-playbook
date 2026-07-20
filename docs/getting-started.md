# Getting started (~30 minutes)

Goal: install the official toolchain, confirm Knowledge MCP works, and know where to go next.

## Prerequisites

- Node.js **22**
- Git
- A coding agent that supports `SKILL.md` and MCP ([Cursor](https://cursor.com), Claude Code, Copilot in VS Code, Codex, …)
- Access to [Merchant Center](https://mc.commercetools.com) (or a [free trial](https://commercetools.com/free-trial)) if you will call a real project

## 1. Install the commercetools AI plugin

In Cursor:

1. **Settings → Plugins**
2. Install from Git URL: `https://github.com/commercetools/commercetools-ai-plugins`

Other agents: follow the plugin’s README for install instructions.

## 2. Enable Knowledge MCP

Knowledge MCP is public (no API key). Example Cursor `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "commercetools-knowledge": {
      "type": "http",
      "url": "https://docs.commercetools.com/apis/mcp"
    }
  }
}
```

Docs: [Knowledge MCP](https://docs.commercetools.com/dev-tooling/mcp/knowledge-mcp).

## 3. Smoke-test the agent

Ask your agent something like:

```text
Using commercetools-knowledge MCP, summarize how Product Search differs from
Product Projection Search, and list the OAuth scopes a Frontend B2C API client
typically needs for cart + checkout sessions.
```

You should see MCP tool calls (search / schema / tips), not only model memory.

## 4. Optional — Commerce MCP

Only if you want the agent to hit **your** project APIs. Requires API client credentials and careful scope choice. Docs: [Commerce MCP](https://docs.commercetools.com/dev-tooling/mcp/commerce-mcp).

Do **not** commit secrets. Prefer a dedicated low-privilege client for experiments.

## 5. Optional — commercetools Project

For a storefront tutorial from empty folder:

1. Create a project (sample B2C data is fine)
2. Create a **Frontend B2C** API client (not Project manage)
3. Activate **Product Search** and index
4. Follow [Build a storefront from scratch](https://docs.commercetools.com/dev-tooling/build-with-ai-storefront-from-scratch)

Or clone our PoC and run locally:

```bash
git clone https://github.com/tomasz-miller/zero-to-ct-storefront.git
cd zero-to-ct-storefront
corepack enable && pnpm install
cp .env.example .env.local   # add your CT_* credentials
pnpm dev
```

## 6. Next reading in this playbook

1. [Capability map](./capability-map.md) — what we covered
2. [How we work](./how-we-work.md) — delivery rules
3. [Recipes](./recipes/) — copy-paste prompts
4. [Showcases](./showcases.md) — demos for colleagues or prospects
