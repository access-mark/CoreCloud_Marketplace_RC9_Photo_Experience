# RC5 — Unified marketplace rebuild

## Scope
- Replaced the visible public-facing pages with one consistent editorial design system.
- Single laptop catalogue at `shop.html`; legacy `employee-purchase.html` redirects to it.
- New business landing page, homepage, employee programme, lifecycle, contact, cart, warranty and terms presentation.
- Responsive header/footer, mobile navigation, product filters and a local quote basket.
- Existing RC3 backend preserved in `commerce/` for separate testing and deployment. No live payment processing is enabled.
- Representative products are **not** verified stock. All enquiry forms use FormSubmit.

## Limitations / release gates
1. FormSubmit destination and live email delivery require activation and verification.
2. `https://www.corecloud-marketplace.com/thank-you.html` is the production return URL; change for staging if needed.
3. Product images are clearly illustrative vector art, not actual device photographs. Replace with licensed, SKU-accurate imagery when verified.
4. No actual prices, availability or warranties have been invented.
5. The RC3 backend is preserved but **not connected** to the quote-first storefront; staging API tests are separate.
6. PayFast and Sage remain unverified; no live payments.
7. Legal terms, POPIA privacy policy, consumer returns and VAT documentation require review.
8. Browser/mobile visual QA and live end-to-end testing required before production.
9. Old cart links may exist in external bookmarks; cart.html now represents the personal quote basket; business quotes go through contact.html.
