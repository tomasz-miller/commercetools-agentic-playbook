# Recipe: Scaffold a B2C storefront

**Skills:** `commercetools-storefront`, `commercetools-platform`, `commercetools-checkout`  
**MCP:** Knowledge MCP (required) · Commerce MCP (optional)  
**Official guide:** [Build a storefront from scratch](https://docs.commercetools.com/dev-tooling/build-with-ai-storefront-from-scratch)

## Before you prompt

1. Merchant Center: Frontend B2C API client (include Checkout sessions + Orders as needed; **not** Project manage)
2. Activate Product Search and start indexing
3. Optional: confirm Checkout permissions for a demo
4. Empty git repo folder open in your agent; plugin installed

## Prompt

```text
Generate a complete B2C storefront connected to commercetools.

Scope:
- home page
- product listing + facets (use the Product Search API)
- product detail
- cart
- checkout using Checkout Browser SDK
- customer authentication and account area
- search page

Constraints:
- Next.js App Router with BFF routes under /app/api
- TypeScript SDK v3 ClientBuilder; credentials server-side only
- Before any CT API code: use commercetools-knowledge MCP to confirm endpoints and scopes
- Prefer pnpm if the stack allows
- Do not invent APIs; validate queries when generating them
```

You can add: “Ask me before choosing framework alternatives” or “Act without confirmations for a demo scaffold.”

## After the agent finishes

1. Fill `.env` with CT credentials + a strong `SESSION_SECRET`
2. `pnpm install && pnpm dev` (or the generated scripts)
3. Hit the homepage; verify search and add-to-cart
4. For production deploy, prefer `/deploy-vercel` or `/deploy-netlify` so credential checks run

## Reference PoC

Our delivered variant (extended beyond the minimal scaffold):  
https://github.com/tomasz-miller/zero-to-ct-storefront · https://zero-to-ct-storefront.vercel.app/
