# Showcases

Two complementary proofs. Use the right story for the audience.

---

## 1. zero-to-ct-storefront — agent-assisted B2C delivery

**Story:** A backend-focused developer ships a working B2C storefront on commercetools sample data in ~2 weeks (~42h net), mostly with a coding agent + official CT AI skills and Knowledge MCP.

| | |
|--|--|
| **Live** | https://zero-to-ct-storefront.vercel.app/ |
| **Repo** | https://github.com/tomasz-miller/zero-to-ct-storefront |
| **Demo script** | [DEMO_SCRIPT.md](https://github.com/tomasz-miller/zero-to-ct-storefront/blob/main/docs/DEMO_SCRIPT.md) (~10–15 min) |
| **Time report** | [TIME_REPORT.md](https://github.com/tomasz-miller/zero-to-ct-storefront/blob/main/docs/TIME_REPORT.md) |

### What shipped

- Browse → cart → commercetools Checkout + Stripe → order confirmation → account
- Product Search, facets, sort, pagination, autocomplete, Quick View, wishlist
- Product discounts, cart discount codes, stock / low-stock, multi-market (DE/GB/US)
- Order again + Orders-ranked bestsellers
- ~343 unit tests + ~37 E2E tests; CI on GitHub Actions

### CT AI surface used

- Skills: **storefront**, **platform**, **checkout** (+ commerce-patterns in B2C practice)
- **Knowledge MCP** on every CT API change
- Vercel production (plugin-aligned deploy practices)

### Intentionally not in this PoC

- Shopper-facing “AI assistant” via Commerce MCP
- B2B quotes / approvals
- Custom Connect application authored with the connect skill
- Production ESP / email verification

**Audience:** technical buyers, architects, delivery leads evaluating *how fast* CT projects start with agents.

---

## 2. commerce-ai-tool — LLM product search accelerator

**Story:** A reusable search widget (React / Next.js / Angular) that interprets natural language, voice, and images into commercetools Product Search — company IP, not an official CT skill.

| | |
|--|--|
| **Repo** | https://github.com/tomasz-miller/commerce-ai-tool |
| **Packages** | `@commerce-ai-tool/core`, `server`, `react`, `angular` |

### What it demonstrates

- Text search via LLM (OpenRouter or AWS Bedrock)
- Voice (STT) and image (vision) → product attributes → CT search
- Server-only secrets; optional facets, cache, i18n on the widget

### How it relates to CT AI

| Official CT AI | commerce-ai-tool |
|----------------|------------------|
| Helps *developers* build CT integrations correctly | Helps *shoppers* search with AI |
| Skills + Knowledge MCP in the IDE | Runtime LLM adapters + CT Product Search |
| No LLM required at runtime for the storefront PoC | Requires AI provider keys |

**Audience:** merchandising / CX conversations, accelerator / marketplace discussions, differentiation beyond “we used the plugin.”

---

## Combining them in a pitch

1. Open the **live storefront** — show purchase path and agent-delivery narrative (~42h).
2. Optionally show **commerce-ai-tool** as the next layer: AI discovery on the same platform.
3. Point to this playbook’s [capability map](./capability-map.md) when asked what else the official plugin covers (Connect, commerce-mcp ops, B2B).
