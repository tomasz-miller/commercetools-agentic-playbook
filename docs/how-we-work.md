# How we work

Opinionated workflow used to deliver [zero-to-ct-storefront](https://github.com/tomasz-miller/zero-to-ct-storefront) with a coding agent and the official commercetools AI plugin.

Official overview: [Building on commercetools with AI](https://docs.commercetools.com/dev-tooling/build-with-ai-overview).

## Mental model: skills vs MCP

| | Skills | Knowledge MCP |
|--|--------|-----------------|
| What | Persistent playbooks (`SKILL.md` + references) the agent loads when a task matches | Live docs, schemas, and query validation on demand |
| Think of it as | “How we always build this” | “Check the exact specs right now” |
| Gives you | Consistency across projects | Currency (no stale training data) |

Use **both**. Skills alone drift from API reality; MCP alone lacks opinionated architecture.

Optional **Commerce MCP** lets the agent call *your* project APIs (needs credentials). Keep it for IDE/ops; do not confuse it with shopper UX.

## Toolchain

| Tool | Role |
|------|------|
| [Cursor](https://cursor.com) (or another agent that reads `SKILL.md` + MCP) | Coding agent |
| [commercetools AI plugin](https://github.com/commercetools/commercetools-ai-plugins) | Skills + slash commands |
| Knowledge MCP | Docs / schema / validate before CT API code |
| Node.js 22 + **pnpm** | Runtime and package manager |
| Merchant Center | Project, API clients, Checkout, Connect |

## Install plugin (Cursor)

1. Cursor → **Settings → Plugins**
2. Install from Git URL: `https://github.com/commercetools/commercetools-ai-plugins`
3. Confirm Knowledge MCP responds (ask the agent to search commercetools docs)

## Knowledge MCP in the project

Minimal Cursor config (example from the storefront PoC):

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

Public endpoint — no API key. See [Knowledge MCP docs](https://docs.commercetools.com/dev-tooling/mcp/knowledge-mcp).

## Hard rules that kept the PoC safe

These are the rules that matter more than any prompt:

1. **Never** put commercetools credentials in the client bundle
2. Browser talks only to **BFF routes** (`/app/api/*`); BFF talks to CT
3. Use **TypeScript SDK v3** (`ClientBuilder` pattern)
4. Before writing CT API code: **search docs via Knowledge MCP**, then validate REST/GraphQL when generating queries
5. One feature slice per agent session; human reviews BFF and SDK layers
6. Public docs in **English**

Full write-up in the storefront repo: [AGENT_CODING.md](https://github.com/tomasz-miller/zero-to-ct-storefront/blob/main/docs/AGENT_CODING.md) and [CURSOR_SETUP.md](https://github.com/tomasz-miller/zero-to-ct-storefront/blob/main/docs/CURSOR_SETUP.md).

## Division of labour

| Layer | Human | Agent |
|-------|-------|-------|
| Merchant Center / API clients / Connect install | Owns | Assists with checklists |
| BFF + CT SDK | Reviews every change | Drafts |
| UI (coss / App Router pages) | Tests flows | Generates most of the code |
| Credentials & scopes | Owns | Must not invent Project-wide manage scopes for storefront clients |

In the storefront PoC, roughly **85–95%** of application code was agent-generated; humans owned CT project setup, Stripe/Connect, and review gates (`lint`, `typecheck`, unit tests).

## Suggested session shape

1. State the **business slice** (e.g. “guest cart + discount codes”), not “build the shop”
2. Point the agent at the matching skill (storefront / checkout / platform)
3. Require Knowledge MCP before SDK calls
4. Run lint / typecheck / unit tests before merging
5. Update a short build log so demos and time reports stay honest

## What not to do

- One giant open-ended prompt for the entire commerce domain
- Skipping MCP validation “because the model knows commercetools”
- Putting `commerce-mcp` credentials into a public demo without a security review
- Treating agent output as production-certified without review and tests
