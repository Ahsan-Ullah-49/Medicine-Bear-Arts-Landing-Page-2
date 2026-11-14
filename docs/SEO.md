# SEO and social sharing

Last updated: 2026-11-14.

## Site identity and current indexing scope

- Requested public host: `https://sales.medicinebeararts.com/`.
- The HTML declares that URL as its canonical page, and the sitemap lists that root URL.
- The selector uses `?product=<slug>` on one HTML page. These are campaign/share selections, not distinct indexable product pages; they canonicalize to the root.
- The page has a descriptive title and summary, Open Graph and X/Twitter sharing tags, and `WebSite`/publisher JSON-LD using verified brand/site information and supplied logo.
- No `Product` structured data is emitted. Product content is selected and rendered in browser JavaScript, live price and availability can change in Shopify, and no distinct canonical route currently exists for each item.

The current site-level SEO foundation is prepared locally. It is not a launch-complete SEO setup: the domain does not resolve as of the 2026-11-14 lookup, and no host, HTTPS deployment, Search Console property, or post-deployment crawl check is configured. Do not describe the site as published or indexed.

## Catalog scale and product SEO

The copy preserves the existing 12-product campaign catalog. The owner now plans for approximately 20–25 products total after receiving client-supplied links, product details, and approved media. This is a planning range, not a code-imposed maximum. New items should follow [PRODUCT_INTAKE_TEMPLATE.md](PRODUCT_INTAKE_TEMPLATE.md), and their product facts must be verified before publication.

Adding an item to `js/products.js` makes it available in the interactive collection; it does **not** give it an independently crawlable URL, title, description, canonical, share preview, or product structured data. If the client expects each product to have its own organic search listing or product-specific social preview, implement a distinct crawlable route per product with unique approved page copy, title/description, canonical, image metadata, and appropriate structured data based on current Shopify data. Verify that the chosen static host serves those routes and that the sitemap lists only real canonical pages. The route architecture and SEO copy are still pending; do not claim per-product SEO is complete.

If the sales page is intended only as one paid-campaign landing page, keep the root as the sole canonical page and use query URLs only for campaign selection. In either case, avoid making unsupported product, cultural, materials, origin, or benefit claims. The sales page's self-canonical signal does not guarantee that a search engine will choose it over similar official-store content. Keep the campaign useful and distinct; do not change the original store's canonical settings.

## Files and upkeep

- `index.html`: page title, summary, canonical, Open Graph/X cards, and website/publisher JSON-LD.
- `robots.txt`: permits crawling and advertises the sitemap.
- `sitemap.xml`: currently contains only the canonical root page. Update `lastmod` only when indexed page content changes, and add URLs only after distinct canonical pages exist.
- `js/products.js`: interactive campaign catalog. An entry here alone is not an SEO product page.
- `docs/PRODUCT_INTAKE_TEMPLATE.md`: per-product source data, media, approval, and SEO intake/checklist.

The social image currently uses the supplied logo. Replace it with a client-approved landscape share image only after creating and checking that asset. Do not put snapshot prices or availability in static metadata; Shopify is the source of truth.

## SEO release checklist

Before public indexing, select the host, map the requested subdomain to it, enable HTTPS, and confirm the deployed root, `robots.txt`, and `sitemap.xml` work on the exact HTTPS hostname. Check that the page is not blocked by host settings, confirm canonical and sitemap hosts match, verify the property in Google Search Console, submit the sitemap, inspect the canonical Google selects, and check deployed social previews. If separate product SEO is required, also verify every product route, unique metadata and canonical, structured data against live Shopify facts, sitemap membership, and crawlability on the selected host. A DNS lookup on 2026-11-14 returned that the requested hostname does not exist. This local project has not been hosted or published.

## References

- [Google Search Central: canonicalization](https://developers.google.com/search/docs/crawling-indexing/canonicalization)
- [Google Search Central: specifying a canonical URL](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)
- [Google Search Central: title links](https://developers.google.com/search/docs/appearance/title-link)
- [Google Search Central: snippets and meta descriptions](https://developers.google.com/search/docs/appearance/snippet)
- [Google Search Central: JavaScript-generated structured data](https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript)
- [Google Search Central: build and submit a sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
