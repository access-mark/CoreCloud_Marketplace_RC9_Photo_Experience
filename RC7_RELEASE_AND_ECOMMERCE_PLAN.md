# RC7 — Visual polish + commerce readiness audit

## Implemented
- Doubled header logo footprint relative to RC6 (57px to 108px desktop); responsive header sizing.
- Reduced hero heading weight from inherited 800 to 500; moderated size and widened copy column.
- Improved input and label contrast, visible focus outlines, section spacing and mobile breakpoints.
- Disabled an invalid legacy checkout.js that attempted an unverified direct PayFast redirect. Quarantined original as non-deployable text.
- Preserved existing RC3 commerce reservation backend and quote workflows.

## Existing backend (code inspected, not deployed)
- SQLite products, stock, order records, atomic reservations, private status lookup, admin product/status endpoints.
- /api/health explicitly reports payments disabled. No verified payment capture or real fulfilment integration.
- Seed catalogue is inactive with zero stock and zero prices by design. The illustrative six-family storefront is NOT a live sellable inventory catalogue.

## Required before full ecommerce production
1. Confirm actual supplier SKUs, serial/grade, inventory feed, VAT-inclusive prices, warranty, delivery charges and returns.
2. Host the backend on HTTPS with managed persistence, secret management, admin MFA/RBAC, abuse prevention, backups and monitoring. GitHub Pages alone cannot run the Python commerce server.
3. Integrate PayFast or other approved PSP on the server: generate signed transaction for a server-priced order; verify server-to-server notification signature, merchant ID, amount, status, source and idempotency before marking paid. Never trust browser success redirect.
4. Implement stock reservation expiry, order cancellation/refund, fulfilment and customer transactional emails, supplier reconciliation and Sage invoicing.
5. Complete POPIA, CPA and ECTA review; end-to-end sandbox checkout and mobile testing; verify all FormSubmit delivery.

**Status: design candidate / reservation backend. NOT live ecommerce. Do not enable live payment links or advertise immediate checkout.**
