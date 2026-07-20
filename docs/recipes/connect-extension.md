# Recipe: Scaffold a Connect API Extension

**Skill:** [commercetools-connect](https://docs.commercetools.com/dev-tooling/skills/commercetools-connect.md)  
**MCP:** Knowledge MCP  
**Status in our initiative:** **Not yet demonstrated** as a separate PoC — this recipe closes the narrative gap until you run it.

## Goal

Produce a minimal Connect application that registers an **API Extension** (for example, validate cart custom fields or enrich order metadata) using the connect skill’s project structure — not by installing only a third-party connector from the marketplace.

## Prompt

```text
Using the commercetools-connect skill and commercetools-knowledge MCP:

Scaffold a minimal production-shaped Connect application that:
- Uses the recommended Connect project structure
- Implements one API Extension triggered on Cart update (or Order Create — pick one and justify)
- Validates or enriches a single, clearly documented field
- Includes local test instructions and deployment notes for Connect
- Documents required OAuth scopes and Extension destination URL configuration

Constraints:
- TypeScript
- No commercetools credentials in the client or in committed files
- Do not invent Extension APIs — validate against Knowledge MCP / docs
- Keep the business rule trivial (PoC), focus on correct Connect wiring

After scaffolding, give me a checklist for Merchant Center / Connect deployment steps I must do by hand.
```

## Why this matters for GTM

The storefront PoC proves **storefront + checkout skills**. A tiny Connect app proves the plugin also accelerates **integration / event-driven** work — a different buyer conversation (ops, OMS, ERP hooks).

## After you run it

Link the new repo from [capability map](../capability-map.md) and change status from **Not demonstrated** to **Demonstrated**.
