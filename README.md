# Medicine Bear Arts Landing Page 2

A separate, mobile-first static campaign storefront for Medicine Bear Arts. It presents the copied 12-product collection and sends live cart and checkout activity to the existing Shopify store.

## Separate project and target domain

This folder is an independent local Git repository for the requested `https://sales.medicinebeararts.com/` landing page. The source folder at `D:\Medicine Bear Arts` was not edited. The project files and assets were copied exactly before the SEO-specific updates; the new repository has its own Git history and no remote configured yet. Do not add the original project's remote as this repository's `origin`.

The sales hostname is the requested target. A hosting provider, DNS record, HTTPS deployment, and GitHub remote still need to be configured. This project continues to use the existing Shopify store for live Canadian-market commerce and checkout.

## What is included

- Twelve selectable products through `?product=<slug>` URLs.
- Product galleries, descriptions, options, quantity controls, and product-specific WhatsApp messages.
- Shopify Storefront Cart API integration in the Canadian market with CAD pricing.
- A multi-item bag that redirects to Shopify's secure checkout URL.
- A preview-only fallback if the Shopify API cannot be reached.
- A controlled, secondary trust path with concise artist/story, shipping, returns, materials, contact, and Shop All links to the official store.
- Provider-neutral campaign-link events for a future consented analytics container.
- Light and dark themes, smooth wheel scrolling, responsive desktop/mobile layouts, review carousel, and accessible keyboard controls.

## Project structure

```text
index.html             Page structure and local script order
css/styles.css         Responsive design, themes, hover states, and layout
js/products.js         Campaign catalog, copy, local media, snapshot fallback data
js/shopify.js          Public Shopify Storefront API and Cart API client
js/app.js              Rendering, routing, gallery, cart, and review behavior
js/theme.js            Saved light/dark theme behavior
assets/Logo/           Client logo
assets/Products/       Client-provided product images
assets/vendor/         Local Lenis smooth-scroll library and its MIT license
docs/                  Project notes, setup, deployment, and decision records
robots.txt             Crawler rules and sitemap location
sitemap.xml            Canonical landing-page URL
docs/SEO.md            Domain, canonical, indexing, and launch guidance
```

## Local preview

No packages or build command are needed. Open the project folder using a simple local web server, such as VS Code Live Server, and visit:

```text
http://127.0.0.1:5500/index.html
```

To feature a different product, use a URL such as:

```text
http://127.0.0.1:5500/index.html?product=celestial-moonlight-pendant
```

Opening `index.html` directly can show the layout, but use a local server for the most reliable Storefront API behavior.

## Cart and order separation

This project keeps its browser preview bag and Shopify cart ID in project-specific storage namespaces. Its newly created Shopify carts carry `sales_channel=Medicine Bear Arts Landing Page 2` and `sales_domain=sales.medicinebeararts.com`. Shopify supports cart attributes at cart creation, documents that checkout attributes persist through checkout, and exposes custom attributes on Storefront orders ([CartCreate](https://shopify.dev/docs/api/storefront/latest/mutations/cartCreate), [Checkout Attributes API](https://shopify.dev/docs/api/checkout-ui-extensions/latest/target-apis/checkout-apis/attributes-api), [Order](https://shopify.dev/docs/api/storefront/latest/objects/Order)).

These attributes are intended as a source label, but they have not been confirmed on a completed order and are not tamper-proof proof of origin. Do not use them as the only fulfillment or accounting control without an owner-authorized order check.

Shopify also supports `CartInput.sourceName` for native channel attribution, but its value must belong to a channel owned by the Storefront access token. This project currently uses tokenless Storefront API calls and has no configured channel-specific source name, so native **Sales by Channel** attribution is not configured ([CartInput](https://shopify.dev/docs/api/storefront/2026-10/input-objects/CartInput)).

Both landing pages still use the same Shopify store and product catalog. Orders will appear in the same Shopify admin/store; the marker distinguishes their source, but this is not a separate Shopify account or order database. A genuinely separate order system requires a separate Shopify store and its own product, inventory, checkout, payment, tax, and shipping setup. No test order has been placed.

## Shopify integration

The page uses the public Storefront API at `medicine-bear-arts.myshopify.com` in the Canadian market. It does not contain an Admin API credential, a private token, payment logic, or a custom backend.

When the Storefront API responds, the page reads current product variants, prices, availability, and the Shopify checkout URL. The displayed bag creates a Shopify cart. When the connection fails, the bag becomes a clearly labelled local preview and checkout is disabled.

A final live read audit confirmed the originally configured 11 products in the Canadian storefront, including their titles, CAD prices, variant IDs, and availability. Heart of the Night Brass Earrings was then added from the client CSV and independently confirmed live in the Canadian storefront. A successful checkout redirect confirms that Shopify accepts a cart; it does not confirm payment or an order.

## Catalog and media updates

Edit [js/products.js](js/products.js) to add a product, change approved campaign copy, update local media paths, or change a product slug. Keep Shopify handles in `storeUrl` accurate because the app derives live product reads from that URL.

Use product media that is approved by the client. The current 55 PNG files are about 32 MB in total. Convert and resize copies for production before paid traffic, while retaining the supplied originals separately.

## GitHub and static deployment

This is a static site. Commit the full project, including `assets/vendor/` and `assets/Products/`, to a GitHub repository. GitHub Pages, Netlify, Cloudflare Pages, Vercel static hosting, or another HTTPS static host can serve it without a build step.

For GitHub Pages:

1. Create a repository and upload this folder.
2. In **Settings → Pages**, select **Deploy from a branch**.
3. Choose the branch containing `index.html` and the repository root (`/`).
4. Wait for the Pages URL, then test all featured-product URLs and a Shopify checkout redirect.
5. Add a custom domain only after the client approves its hosting and DNS plan.

See [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md) for the release checklist and [docs/QA_REPORT.md](docs/QA_REPORT.md) for the completed pre-deployment checks. Campaign trust content and measurement handoff are documented in [docs/CAMPAIGN_TRUST_CONTENT.md](docs/CAMPAIGN_TRUST_CONTENT.md) and [docs/ANALYTICS_HANDOFF.md](docs/ANALYTICS_HANDOFF.md).

## Before client launch

- Confirm the client approves every product image, description, review, and testimonial attribution.
- Optimize the product images and test the page over mobile data.
- Perform a merchant-approved Shopify checkout test without relying on this page to process payment.
- Confirm shipping, taxes, payment methods, inventory, and Canadian market settings in Shopify.
- Configure and verify consent-aware analytics before paid ads launch.
- Test the deployed HTTPS URL on mobile and desktop, including the dark theme, WhatsApp links, product options, bag operations, and checkout redirect.

## Why `assets/vendor` stays

`assets/vendor/` contains the locally bundled Lenis JavaScript and CSS that power the requested smooth desktop scrolling. Its MIT license is included as `LENIS-LICENSE.txt`. Removing that folder would break smooth scrolling and remove the required license notice.

## License

The campaign source and client assets remain Medicine Bear Arts project material. The Lenis files in `assets/vendor/` are distributed under their included MIT license.
