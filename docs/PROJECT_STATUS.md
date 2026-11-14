# Project status

Last updated: 2026-11-14.

## Separate project copy and SEO foundation — local work completed

On 2026-11-14, the current working tree from `D:\Medicine Bear Arts` was copied into this independent project. All 91 source files matched by SHA-256 before SEO edits; this includes the source's pre-existing uncommitted `index.html` change. The original `.git` directory was intentionally excluded and this project was initialized as a separate local `main` repository with no remote. The source folder was left untouched.

The existing twelve product entries, their local media, and the Shopify Storefront API configuration were preserved. No new products were added because product identities/content/media were not supplied for this landing page. The copied page now targets `https://sales.medicinebeararts.com/` in its canonical, sharing metadata, JSON-LD, `robots.txt`, and `sitemap.xml`; SEO scope and launch steps are recorded in [SEO.md](SEO.md).

No host, DNS record, HTTPS deployment, GitHub remote, analytics configuration, or Search Console property has been set up. A DNS lookup on 2026-11-14 returned that `sales.medicinebeararts.com` does not exist. The page still uses the existing Shopify store for live Canadian-market commerce and checkout. Product-specific query URLs still represent one page, not separately indexable product pages. The owner now plans for approximately 20–25 total products; the original 12 remain configured, and no additional product data has arrived.

## Product catalog and SEO preparation — documentation updated

On 2026-11-14, the owner set an approximate target of 20–25 total products for this project. Added [PRODUCT_INTAKE_TEMPLATE.md](PRODUCT_INTAKE_TEMPLATE.md) with per-product Shopify, approved copy/media, variant, rights, SEO, and QA fields, plus a batch addition checklist. Updated the README, frontend setup, SEO, roadmap, decision log, and master context to reflect the target and preserve the current 12. No products or product facts were invented or added.

The current site-level SEO metadata remains local and root-only. `?product=<slug>` links still share the root canonical; distinct product search pages, product structured data, deployment, Search Console, DNS, and live indexing are not completed. If the client expects individual product SEO, that route work remains pending product data and a route decision.

## Cart and order-source separation

The new page uses a project-specific browser bag key and Shopify cart-ID namespace, plus `sales_channel` and `sales_domain` cart attributes when creating a Shopify cart. Shopify documents cart attributes as continuing through checkout; the Storefront Order type exposes custom attributes. This is intended to distinguish sales-page orders, but both pages still create orders in the same Shopify store/admin. No live checkout or test order has verified the finished order record, and a browser-supplied attribute is not tamper-proof proof of origin. Native Shopify channel attribution via `CartInput.sourceName` remains unconfigured because no matching channel-owned Storefront access token/source name is available in this project. A second Shopify store would be required for a separate order database.

## Current stage: Local Shopify integration and testing

The initial documentation foundation was completed and verified on 2026-11-03:

- Project requirements documented.
- Architecture proposal documented, with unvalidated choices identified.
- AI assistant instructions created.
- Development roadmap documented.
- Decision log initialized.

The owner subsequently authorized a mobile-first local frontend, product-specific URL selection, custom presentation and Shopify cart integration. The design and content still need product media and client review.

Tamseel-style locally bundled smooth wheel scrolling has been added and checked in a browser, including cart open/close and reduced-motion behavior. Touch scrolling remains native.

The owner supplied product CSVs, a logo, a Canadian-dollar preference, a WhatsApp number, and review screenshots. The local page now includes 12 catalog entries, 26 variant combinations and 55 configured images; CSV amounts are a fallback snapshot. Celestial Moonlight Pendant replaced Moon Beam at the owner's request. Reviews use the supplied text and screenshot-attributed initials. The owner explicitly requested a five-star visual treatment for every displayed review. Their numbered image order is preserved, and image paths, gallery navigation and responsive display were checked locally.

The owner confirmed that the Celestial folder images, including those engraved “Moon Beam” and “Eagle Spirit”, should be used. The Wolf gallery shows a purple gemstone while other gemstone options are selectable; a selection note is displayed until verified option-specific images are available. The supplied PNGs total approximately 58 MB, so media optimization remains a performance consideration.

The local page supports light and dark themes using a header toggle. The selected theme is saved in browser storage where available; light is the default. Mobile layout, theme persistence, and the cart's appearance were checked locally.

On 2026-11-04, additional presentation refinements were applied locally: desktop product galleries place vertical thumbnails beside a compact 4:5 image frame with centered side controls; the mobile header centers the logo above its three controls; reviews use a fixed-size horizontal carousel; and section spacing, typography, button fills, floating actions, and footer copy were adjusted. The desktop frame height now responds to available viewport height, recommendation buttons use the requested forward and reverse green-fill states, primary CTA buttons begin green and reveal their outline on hover, and cart and page-quantity controls share a forest-fill hover. Each review card shows its quotation mark at top left. Scripts load in dependency order at the end of the document. JavaScript syntax and CSS brace balance were checked locally. A headless-browser screenshot could not be produced in the current environment, so the latest refinement remains pending visual review.

The Storefront API is connected locally, using tokenless access to `medicine-bear-arts.myshopify.com` with Canada/CAD context. The original 11 configured products, their CAD prices, and variant IDs were read successfully. Heart of the Night Brass Earrings was subsequently read live as one available $80 CAD variant. Isolated Shopify test carts verified multi-product add, quantity changes, removal, returned totals, and an HTTPS checkout URL; a browser test reached the Shopify checkout page without placing an order. A stock-limited quantity adjustment was also tested. No successful payment or order, checkout settings, tracking, deployment, or launch has been tested or changed. Cart and checkout depend on live API access; failures fall back to a clearly labeled preview with checkout disabled.

On 2026-11-04, a GitHub-readiness audit added a root README, deployment checklist, security notes, Git attributes, and a recorded QA report. JavaScript syntax, CSS structure, local media paths, static-server responses, live CAD product reads, and source credential hygiene passed. A fresh temporary cart mutation was not run during that final audit because the local approval quota was unavailable; the earlier recorded isolated cart tests remain the cart-mutation evidence. No source code was published, deployed, or connected to GitHub as part of this audit.

On 2026-11-05, the client-directed controlled trust path was added without replacing the focused campaign layout: a short artist/story introduction, concise shipping, returns/exchange, and materials information, plus restrained official-store links in the footer. These secondary links open the matching public Medicine Bear Arts page in a new tab. They emit provider-neutral campaign-link events for future consented analytics integration. The official site supports worldwide shipping but does not publish a campaign-safe flat shipping price or delivery timeline, so this page correctly directs shoppers to checkout for available options and charges.

Later on 2026-11-05, five client-approved products were appended to the campaign from a supplied Shopify CSV and corresponding local image folders. The catalog then had 11 products, 25 snapshot variants, and 51 configured local images. A final Canadian storefront audit confirmed all 11 product titles, CAD prices, variant IDs, and availability; 24 variants were currently available. The Pink Bear Print Stud variant was not currently available for sale; the page receives live availability and disables unavailable variants rather than allowing an invalid cart action. Heart of the Night Brass Earrings was subsequently appended from a new client CSV with four approved local images. Its live Canadian storefront read returned one available $80 CAD variant, bringing the configured catalogue to 12 products, 26 snapshot variants, and 55 local images. No campaign layout or visual design was changed.

The post-product trust area was subsequently rebuilt without changing the campaign product experience. It now has a separate Meet the Artist / story section using the client-provided Jadeon portrait and client logo, a dedicated seven-question FAQ limited to owner-requested purchase-confidence topics, and a larger footer with the logo, WhatsApp CTA, and concise Explore, Learn, and Customer Care columns. The CTA keeps its original light presentation; shipping and returns links in the footer target their matching on-page FAQ entries. The content links to the relevant public Medicine Bear Arts pages and retains the existing campaign interaction tracking attributes.

The long-description control uses the browser-native details element with an explicit layout order: expanding a description reveals its remaining text first and places “View Less” after that text; collapsing returns “View More” below the preview copy. This behavior is keyboard accessible, respects reduced-motion preferences, and keeps the existing visual design unchanged.

## Not started

- Final media, product content review, and full commerce acceptance testing.
- Analytics integration and tracking configuration.
- Paid test order, shipping, tax, payment methods, and analytics verification.
- Deployment, hosting setup, and DNS changes.

## Next recommended action

When the client sends product links, details, and approved media, complete [PRODUCT_INTAKE_TEMPLATE.md](PRODUCT_INTAKE_TEMPLATE.md) for each item, add and verify the catalog entries while preserving the current 12, and confirm whether every product needs its own crawlable SEO page. Then review image/option matches, asset weight, content and testimonial permissions, and arrange merchant-approved end-to-end checkout testing, tracking, hosting, and deployment decisions. See [FRONTEND_SETUP.md](FRONTEND_SETUP.md) for local setup.

Update this file as work is actually performed and verified; distinguish proposed work, in-progress work, completed work, and blockers. Record dates and link supporting decisions or evidence where useful.
