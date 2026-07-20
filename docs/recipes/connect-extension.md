# Recipe: Scaffold a Connect API Extension

**Skill:** [commercetools-connect](https://docs.commercetools.com/dev-tooling/skills/commercetools-connect.md)  
**MCP:** Knowledge MCP  
**Status in our initiative:** **Demonstrated** — [ct-agentic-connect](https://github.com/tomasz-miller/ct-agentic-connect)

## Goal

Produce a minimal Connect application that registers an **API Extension** (for example, validate cart custom fields or enrich order metadata) using the Connect project structure — not by installing only a third-party connector from the marketplace.

## Reference PoC

| | |
|--|--|
| **Repo** | https://github.com/tomasz-miller/ct-agentic-connect |
| **Rule** | Reject Cart Create/Update when `totalPrice.centAmount` is below `MIN_CART_CENT_AMOUNT` (empty carts allowed) |
| **Extension key** | `ct-agentic-connect-cartUpdate` |
| **Deploy** | [DEPLOY.md](https://github.com/tomasz-miller/ct-agentic-connect/blob/main/docs/DEPLOY.md) |

## Prompt (reproduce from scratch)

```text
Using the commercetools-connect skill and commercetools-knowledge MCP:

Scaffold a minimal production-shaped Connect application that:
- Uses the recommended Connect project structure (create-connect-app TypeScript)
- Implements one API Extension triggered on Cart Create and Update
- Enforces a configurable minimum cart totalPrice.centAmount (HTTP 400 + errors[])
- Includes unit tests, local run instructions, and Connect deployment notes
- Documents required OAuth scopes (manage_extensions for post-deploy)

Constraints:
- TypeScript + npm (Connect runtime)
- No commercetools credentials in committed files
- Do not invent Extension APIs — validate against Knowledge MCP / docs
- Keep the business rule trivial (PoC), focus on correct Connect wiring

After scaffolding, give me a checklist for Merchant Center / Connect deployment steps I must do by hand.
```

## Why this matters for GTM

The storefront PoC proves **storefront + checkout skills**. A Connect service proves the plugin also accelerates **integration / event-driven** work — a different buyer conversation (ops, OMS, ERP hooks).
