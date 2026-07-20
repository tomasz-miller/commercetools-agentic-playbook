# What commercetools AI does — and does not

Based on the official [Building on commercetools with AI](https://docs.commercetools.com/dev-tooling/build-with-ai-overview) overview and our delivery experience.

## What it fixes

| Pain without the plugin | With skills + Knowledge MCP |
|-------------------------|-----------------------------|
| Wrong API shapes, invented methods, multi-round corrections | Idiomatic patterns on the first pass more often |
| Hallucinated features or APIs from other vendors | Live schema and docs checks |
| Every team invents a different storefront architecture | Shared opinionated foundation (BFF, SDK v3, scopes) |
| Weeks to a reference implementation | Working storefront in a focused delivery window |

It also reduces dangerous mistakes: credentials in the browser, a new client on every request, missing scope discipline — *when* you keep hard rules in the repo (`AGENTS.md`, Cursor rules).

## What it does not do

From commercetools’ own framing (paraphrased):

- **Does not write your requirements** — the agent builds what you ask for
- **Does not own merchandising or business rules** — those stay yours
- **Does not replace review and testing** — your team owns the code
- **Does not harden for production beyond what skills prescribe** — QA, security, load testing still matter

Add our delivery lessons:

- **Does not replace Merchant Center / Connect setup** — humans still create API clients, activate Product Search, wire Stripe, fix Payment Integrations
- **Does not make Commerce MCP a shopper chatbot** — that is a product decision, not a default skill outcome
- **Does not remove token cost or MCP rate limits** — build in slices, not one endless agent loop

## How to talk about it

**Good:** “We use official CT skills and live Knowledge MCP so agents write correct commercetools integrations faster, with a proven BFF architecture.”

**Bad:** “AI builds the entire commerce platform unsupervised” or “commercetools now has built-in ChatGPT shopping.”

## Production stance

Treat agent output as a **strong starting point**, not a certified artifact. Our storefront PoC still ran lint, typecheck, unit tests, E2E, and human review on BFF/SDK code before calling a milestone done.

See also: [Security and best practices](https://docs.commercetools.com/dev-tooling/build-with-ai-security-best-practices) (official).
