# Recipe: Add discount codes to a BFF storefront

**Skills:** `commercetools-storefront`, `commercetools-commerce-patterns`  
**MCP:** Knowledge MCP  
**Context:** Existing Next.js BFF storefront with a cart (e.g. zero-to-ct-storefront)

## Prompt

```text
Add cart discount code support to this commercetools BFF storefront.

Requirements:
- BFF endpoint to add/remove a discount code on the active cart (Cart update actions)
- Cart UI: input + apply/remove, show applied codes and discounted line/totals
- Apply codes on the Cart BEFORE creating a Checkout session
- Use commercetools-knowledge MCP to confirm Cart discount code actions and error shapes
- Keep CT credentials server-side; reuse the existing cart cookie/session pattern
- Add unit tests for the BFF mapper and happy-path apply failure (invalid code)

Do not change Checkout Browser SDK payment flow except ensuring the session uses the updated cart.
```

## Verify

1. Create a discount code in Merchant Center (or use sample data)
2. Add items → apply code → totals update
3. Start checkout; payment session reflects discounted cart
4. Invalid code returns a clear client error (no stack traces)

## Notes

Checkout handles payment, not coupon entry. Discount codes belong on the **Cart** API before session creation.
