# commercetools Agentic Playbook

[![Columbus](./assets/columbus-logotype.svg)](https://www.columbusglobal.com/)

A practical map of what **commercetools AI tooling** enables — skills, MCP servers, and slash commands — with links to working proofs of concept.

This repository is documentation only. It does not ship an application. Use it to:

- Understand the official [commercetools AI plugin](https://docs.commercetools.com/dev-tooling/build-with-ai-overview) surface
- See what we have already demonstrated vs what we intentionally left out
- Run short prompt recipes with your own coding agent
- Onboard colleagues in about 30 minutes

## Start here

| Doc | Purpose |
|-----|---------|
| [Capability map](./docs/capability-map.md) | Skills, MCP, commands → status and PoC links |
| [How we work](./docs/how-we-work.md) | Cursor + plugin + Knowledge MCP workflow |
| [Showcases](./docs/showcases.md) | Live storefront PoC + LLM search accelerator |
| [What CT AI does / does not](./docs/what-ct-ai-does.md) | Honest boundaries for sales and delivery |
| [Getting started](./docs/getting-started.md) | Install toolchain and try Knowledge MCP |
| [Recipes](./docs/recipes/) | Copy-paste prompts for common tasks |

## Two kinds of value

```text
Official commercetools AI          Company / IP accelerators
─────────────────────────          ─────────────────────────
Skills + Knowledge MCP             commerce-ai-tool
  → build storefronts,             → LLM voice / image / text
    Connect apps, checkout           search widget for CT
    patterns correctly first time

commerce-mcp (optional)            Playbooks / GTM materials
  → agent talks to YOUR project    → this repo
```

Do not confuse **agent-assisted delivery** (official plugin) with **shopper-facing AI search** (our separate product). Both are useful; they sell different stories.

## Proofs of concept

| Showcase | What it proves | Links |
|----------|----------------|-------|
| **zero-to-ct-storefront** | Full B2C path with CT AI skills + Knowledge MCP (~42h net) | [Live](https://zero-to-ct-storefront.vercel.app/) · [Repo](https://github.com/tomasz-miller/zero-to-ct-storefront) |
| **ct-agentic-connect** | Connect `service` + Cart API Extension (min cart value) | [Repo](https://github.com/tomasz-miller/ct-agentic-connect) · [Deploy](https://github.com/tomasz-miller/ct-agentic-connect/blob/main/docs/DEPLOY.md) |
| **commerce-ai-tool** | Own accelerator: NL / voice / image product search on CT | [Repo](https://github.com/tomasz-miller/commerce-ai-tool) |

## Official references

- [Building on commercetools with AI](https://docs.commercetools.com/dev-tooling/build-with-ai-overview)
- [Build a storefront from scratch](https://docs.commercetools.com/dev-tooling/build-with-ai-storefront-from-scratch)
- [Knowledge MCP](https://docs.commercetools.com/dev-tooling/mcp/knowledge-mcp)
- [Commerce MCP](https://docs.commercetools.com/dev-tooling/mcp/commerce-mcp)
- [commercetools AI plugins](https://github.com/commercetools/commercetools-ai-plugins)

## License

[MIT](./LICENSE)

---

Published by [Columbus](https://www.columbusglobal.com/) — enablement material for agentic commercetools delivery.
