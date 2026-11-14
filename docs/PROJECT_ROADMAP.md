# Project roadmap

Current stage: **independent local copy and root-page SEO foundation complete; product-intake documentation prepared; product additions, product-route SEO decision, and launch setup pending**. Phase order is a planning guide; dependencies and client approvals govern actual implementation. See [PROJECT_STATUS.md](PROJECT_STATUS.md) for verified progress.

## 2026-11-14 fork milestone

- Completed a byte-verified copy of the source working tree into `Medicine Bear Arts Landing Page 2`; created a fresh local Git repository with no remote to keep pushes isolated from the original project.
- Preserved all 12 existing product entries and local assets. The owner plans for approximately 20–25 total products; an intake template and update checklist are prepared, while additions remain pending approved Shopify links/details and media.
- Added the requested sales-subdomain canonical, social metadata, brand/site JSON-LD, `robots.txt`, `sitemap.xml`, and [SEO.md](SEO.md).
- Added a dedicated browser cart namespace and sales-page attributes to newly created Shopify carts. The original page is unchanged; both still use the same Shopify store, and an order has not been used to verify attribute carry-through.
- Still pending: choose and connect the hosting provider, attach `sales.medicinebeararts.com`, verify HTTPS, create/connect the new hosted Git remote, and complete post-deployment SEO and commerce checks. No production changes were made.

## Phase 1: Planning and documentation — completed

Document requirements, proposed architecture, project constraints, assistant instructions, decisions, and unresolved questions. Confirm the scope and gather approvals for subsequent work. Documentation completion does not imply architecture or integration validation.

## Phase 2: Product preparation — in progress

Preserve the 12 current entries and prepare for approximately 20–25 total products. Use [PRODUCT_INTAKE_TEMPLATE.md](PRODUCT_INTAKE_TEMPLATE.md) to collect verified names, specifications, Shopify links and variants, approved marketing content, imagery, rights, and per-product SEO needs. Confirm Canada/CAD publication and availability from live Shopify data. Add products only after the client supplies and approves the required facts and media; then review catalog layout and asset performance at the final scale.

## Product SEO dependency — decision pending

The current SEO baseline covers one canonical landing page. Decide whether the client needs only campaign selection links or a distinct organic-search page for each product. If the latter, select and implement a crawlable route strategy, unique approved metadata and copy, verified structured data, and matching sitemap entries before claiming product-level SEO readiness. Product details and the chosen route strategy are not yet available.

## Phase 3: Frontend design — in progress

Review client brand assets and design references; build a responsive landing page with a dynamic product hero, custom imagery, and recommendations. Agree on accessibility, performance, and content expectations before finalizing the design.

## Phase 4: Dynamic functionality — initial foundation in progress

Implement configurable product URLs, featured-product switching, navigation, galleries, variant selection, quantity interactions, and defined invalid-product and error states. Coordinate variant interactions with the actual Shopify data model.

## Phase 5: Shopify integration — in progress

Validate API access and compatibility, connect live commerce data and the custom multi-product cart, implement quantity controls and availability validation, persistence and recovery, and redirect to the official secure Shopify checkout. Test actual store and checkout compatibility. Do not assume synchronization with the existing theme cart.

## Phase 6: Advertising tracking — not started

Audit existing integrations, agree consent and event ownership, then configure and verify Google Ads/GA4, Meta, and TikTok events. Verify attribution and confirmed purchases on the Shopify side and avoid duplicate events. Tracking and production changes need authorization.

## Phase 7: Testing — not started

Test all product URLs and fallback states, variant and cart interactions, changing inventory/prices, checkout with multiple items, mobile layouts, accessibility, performance, consent, and analytics including confirmed test purchases. Record results and resolve defects.

## Phase 8: Deployment — not started

Agree domain, hosting and deployment method; obtain explicit production approval; configure the approved environment and perform launch verification, including checkout and tracking. DNS, store, and production changes are not authorized by this roadmap alone.
