# Capability map

Status of the official commercetools AI surface relative to our proofs of concept.

**Legend**

| Status | Meaning |
|--------|---------|
| **Demonstrated** | Used in a public PoC with evidence |
| **Partial** | Used in practice, but not the full skill scope |
| **Documented only** | Covered here as a recipe / narrative, no separate PoC repo |
| **Out of scope** | Conscious non-goal for the current initiative |
| **Not demonstrated** | Gap — candidate for a future thin PoC |

---

## MCP servers

| Capability | Status | Evidence / notes |
|------------|--------|------------------|
| [Knowledge MCP](https://docs.commercetools.com/dev-tooling/mcp/knowledge-mcp) — docs search, OAS/GraphQL schema, query validation | **Demonstrated** | Required in [zero-to-ct-storefront](https://github.com/tomasz-miller/zero-to-ct-storefront) agent workflow |
| [Commerce MCP](https://docs.commercetools.com/dev-tooling/mcp/commerce-mcp) — agent calls *your* project APIs | **Documented only** | IDE/ops tooling; not wired into storefront shopper UX. See [commerce-mcp catalog audit](./recipes/commerce-mcp-catalog-audit.md) |

---

## Skills

| Skill | Status | Evidence / notes |
|-------|--------|------------------|
| [commercetools-platform](https://docs.commercetools.com/dev-tooling/skills/commercetools-platform/) — SDK, auth, data model, predicates, concurrency | **Demonstrated** | TypeScript SDK v3 `ClientBuilder`, correlation ID + concurrent-modification middleware in storefront |
| [commercetools-storefront](https://docs.commercetools.com/dev-tooling/skills/commercetools-storefront/) — Next.js BFF B2C/B2B storefront patterns | **Demonstrated** (B2C) | Full purchase path: discovery, cart, checkout, auth, wishlist, promotions, multi-market. **B2B modules** (quotes, approvals, impersonation) → **Out of scope** |
| [commercetools-checkout](https://docs.commercetools.com/dev-tooling/skills/commercetools-checkout/) — Checkout + PSP connectors | **Demonstrated** | Checkout Browser SDK + Stripe Connect connector installed in Merchant Center |
| [commercetools-commerce-patterns](https://docs.commercetools.com/dev-tooling/skills/commercetools-commerce-patterns.md) — pricing, discounts, shipping, tax, B2B orders, import | **Partial** | B2C pricing/discounts/shipping/tax via storefront. B2B order flows and bulk import → **Not demonstrated** |
| [commercetools-connect](https://docs.commercetools.com/dev-tooling/skills/commercetools-connect.md) — Connect apps, extensions, subscriptions, Custom Views | **Demonstrated** (service / API Extension) | [ct-agentic-connect](https://github.com/tomasz-miller/ct-agentic-connect) — min cart value Extension on Cart Create/Update; deploy notes in [DEPLOY.md](https://github.com/tomasz-miller/ct-agentic-connect/blob/main/docs/DEPLOY.md). Subscriptions / Custom Views → **Not demonstrated** |

---

## Slash commands

| Command | Status | Notes |
|---------|--------|-------|
| `/nextjs-setup-project` | **Partial** | Storefront scaffolded with CT AI plugin patterns; exact slash-command history may vary by agent |
| `/deploy-vercel` | **Partial** | Production on Vercel with auto-deploy; see storefront [DEPLOY.md](https://github.com/tomasz-miller/zero-to-ct-storefront/blob/main/docs/DEPLOY.md) |
| `/deploy-netlify` | **Out of scope** | Not used |

---

## Adjacent (not official CT AI skills)

| Asset | Kind | Status |
|-------|------|--------|
| [commerce-ai-tool](https://github.com/tomasz-miller/commerce-ai-tool) | Company IP — LLM / voice / image search for CT catalogs | **Demonstrated** separately |
| Mozaik / other CT platform surfaces | Product access | Waiting / separate track — does not block this playbook |

---

## Coverage at a glance

```text
Demonstrated well     Knowledge MCP · platform · storefront (B2C) · checkout · connect (API Extension service)
Partial               commerce-patterns · deploy slash commands
Recipes only          commerce-mcp ops
Conscious gaps        B2B storefront modules · Connect event/job/Custom Views · shopper-facing commerce-mcp · Netlify deploy
```

For sales: lead with the **storefront PoC** (time-to-value + live demo), then **Connect** for integration/extensibility. Use this map when a prospect asks “what else can the plugin do?”
