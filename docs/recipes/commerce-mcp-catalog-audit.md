# Recipe: Commerce MCP catalog audit (IDE / ops)

**MCP:** [Commerce MCP](https://docs.commercetools.com/dev-tooling/mcp/commerce-mcp) + Knowledge MCP  
**Not for:** Shopper-facing chat in the storefront  
**Purpose:** Let the coding agent inspect *your* project data while you design or debug

## Before you prompt

1. Create a dedicated API client with **least privilege** (e.g. view products / categories — avoid Project manage)
2. Configure Commerce MCP with env credentials (never commit them)
3. Restart the agent session so it picks up MCP config

## Prompt

```text
Using commerce-mcp (live project) and commercetools-knowledge for API shape:

1. List how many published products exist and sample 5 product keys/names
2. Summarize the category tree depth and top-level category names
3. Check whether Product Search indexing looks healthy enough for a storefront demo
4. Flag any obvious catalog issues for a B2C demo (missing prices, empty categories, unpublished bestsellers)

Do not modify any resources. Read-only. Summarize findings in a short markdown report.
```

## Safety

- Prefer read-only scopes for demos to colleagues
- Do not paste secrets into chat logs you will publish
- This is **ops / enablement**, not a customer chatbot — see [capability map](../capability-map.md)

## Follow-up ideas

- “Which products lack images?”
- “List discount codes that are active this week”
- “Find carts older than 30 days” (only with appropriate scopes)
