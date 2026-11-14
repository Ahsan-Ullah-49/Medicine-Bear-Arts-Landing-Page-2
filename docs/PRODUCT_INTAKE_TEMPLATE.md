# Product intake and catalog update guide

Last updated: 2026-11-14.

Use one copy of the intake record below for every new product. The project currently contains 12 products; the working target is approximately 20–25 products total after the client supplies the next batch. This is a target range, not a fixed limit. Keep all existing entries unless the owner explicitly approves a removal or replacement.

## Batch checklist

Before editing `js/products.js`, collect the client’s Shopify links and approved assets, complete one record per product, and resolve missing facts with the client. Then:

1. Confirm the public Shopify product page is correct and available in the Canadian storefront. Capture current product/variant identity, option names, price, currency, and availability from Shopify; treat CSV data as a reference snapshot.
2. Confirm the product name, campaign description, specifications, option labels, image order, video/poster, alt text, asset usage rights, and required client approval. Do not invent product or cultural claims.
3. Choose a stable unique slug and confirm no existing entry uses it. Keep each `storeUrl` pointed at the matching Shopify product.
4. Add the product object and its local asset paths to `js/products.js`, preserving the existing catalog. Map each purchasable variant to the matching live Shopify variant; do not guess IDs or option combinations.
5. Check the product selection URL, featured gallery, recommendation card, option selection, WhatsApp link, cart add, live price/availability, and desktop/mobile layout. Update docs/counts only to reflect what is actually present and checked.
6. Decide whether the product needs its own organic-search page. The existing `?product=<slug>` selection is not a separate SEO page. If yes, implement and verify a distinct crawlable route and its metadata/structured data before marking product SEO ready. See [SEO.md](SEO.md).

## Copy this record once per product

### Product: [client/store name]

**Client source and approval**

- Client contact / source of supplied data:
- Public Shopify product URL:
- Shopify product title (exact):
- Product is published and purchasable in Canada: [ ] yes [ ] no [ ] confirm
- Product or option exclusions / availability notes:
- Client approval for final listing and copy: [ ] pending [ ] approved — date/name:

**Catalog configuration**

- Proposed stable slug (lowercase, unique):
- Client-approved campaign display name:
- Shopify product handle / verified product identity:
- Currency/market checked live (expected Canada/CAD):
- Variants and exact option names/values (attach Shopify export if helpful):
- Variant IDs checked against live product data: [ ] yes [ ] pending
- Current live price and availability checked (date):
- Campaign description / verified specifications:
- WhatsApp message wording or special ordering notes:

**Media and rights**

- Approved primary/featured image path:
- Gallery image paths and display order:
- Video path and poster image, if applicable:
- Alt text for each meaningful image:
- Client confirms rights/permission to use these assets here: [ ] pending [ ] approved — date/name:
- Responsive/compressed copies prepared: [ ] pending [ ] complete

**SEO and sharing**

- Does this product need its own organic-search landing page? [ ] yes [ ] no [ ] client to decide
- Approved search intent/topic notes (not a `meta keywords` list):
- Unique page title, if a distinct route is approved:
- Unique search summary/description, if a distinct route is approved:
- Proposed public canonical route, if a distinct route is approved:
- Approved social share image, if different from product image:
- Claims/source checks for materials, origin, artist, or cultural wording:
- Product facts for structured data rechecked live in Shopify: [ ] pending [ ] complete

**Implementation and handoff**

- Catalog entry added and slug checked:
- Local media paths resolve:
- Featured-product and recommendation views checked:
- Variants, price, availability, and cart behavior checked:
- Mobile and desktop presentation checked:
- Product SEO route and metadata checked, if required:
- Client review status / remaining questions:

## Before sending the updated project to the client

- Reconcile the product count against `js/products.js`; do not describe the planned 20–25 total as achieved until the entries are actually supplied and added.
- Confirm every product's Shopify URL, live variants, CAD price, and availability; note temporarily unavailable items accurately.
- Confirm approved copy, asset rights, alt text, and no unsupported claims.
- Recheck all product links, cards, galleries, options, cart additions, WhatsApp messages, and responsive layouts for the changed catalog.
- Recheck asset size and loading after adding media; optimize production copies while keeping originals available.
- If product-specific SEO was requested, ensure each product has a real crawlable canonical route and matching metadata; update `sitemap.xml` only for real public routes.
- Update the status, roadmap, SEO notes, and catalog count after work is performed. Keep deployment, DNS, analytics, and checkout/order verification marked pending until those steps actually happen.
