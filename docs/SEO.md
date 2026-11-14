# SEO and social sharing

Last updated: 2026-11-14.

## Site identity and canonical URL

- Requested public host: `https://sales.medicinebeararts.com/`.
- The HTML declares that URL as its canonical page, and the sitemap lists the same URL.
- The existing product selector uses `?product=<slug>` on one HTML page. These query URLs are campaign/share links, not separate indexable product pages; they canonicalize to the root page.
- The page has a descriptive title and summary, Open Graph and X/Twitter sharing tags, and `WebSite`/publisher JSON-LD using only the verified brand name, current site URL, official storefront URL, and supplied logo.
- No `Product` structured data is emitted. Product details are selected and rendered in browser JavaScript, prices and availability can change in Shopify, and the current routes do not provide a distinct canonical URL per product.

## Duplicate content and indexing scope

This project copies the existing 12-product campaign catalog and much of its product and trust content. The requested self-canonical signals that the sales subdomain is intended to be the landing page's preferred URL; it does not guarantee that a search engine will select it when similar content is available on the official storefront. Keep the campaign page useful and distinct, and review Search Console's selected canonical after publishing. Do not add fabricated product claims or change the original storefront's canonical settings.

The current SEO setup covers one landing page. It does not create 12 separately indexable product pages. If individual products need their own organic search results, add crawlable product routes with unique approved copy, per-route titles/descriptions, canonicals, and structured data based on current Shopify price and availability. Prefer generating that information in the page HTML when the route is built; JavaScript-generated product markup can make fast-changing shopping data less reliable for crawlers.

## Files and upkeep

- `index.html`: title, description, canonical, Open Graph/X cards, and website/publisher JSON-LD.
- `robots.txt`: permits crawling and advertises the sitemap.
- `sitemap.xml`: contains only the canonical root page. Update `lastmod` only when the indexed page content changes, and add a URL only after it is a real, canonical, public page.
- `js/products.js`: campaign catalog. Adding a product to this file adds it to the interactive collection, but not as a separate SEO landing page.

The social image currently uses the supplied logo. Replace it with a client-approved landscape share image only after creating and checking that asset. Do not add prices or availability to static metadata because Shopify is the source of truth and the local snapshot is only a fallback.

## Release checklist

Before public indexing, select the host, map the requested subdomain to it, enable HTTPS, and confirm that the deployed root, `robots.txt`, and `sitemap.xml` return successfully on the exact HTTPS hostname. Check that the page is not blocked by host settings, confirm the canonical and sitemap host match, verify the property in Google Search Console, submit the sitemap, and inspect the canonical Google selects. Check social previews with the deployed URL. A DNS lookup on 2026-11-14 returned that the requested hostname does not exist. These are pending launch steps; this local project has not been hosted or published.

## References

- [Google Search Central: canonicalization](https://developers.google.com/search/docs/crawling-indexing/canonicalization)
- [Google Search Central: specifying a canonical URL](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)
- [Google Search Central: title links](https://developers.google.com/search/docs/appearance/title-link)
- [Google Search Central: snippets and meta descriptions](https://developers.google.com/search/docs/appearance/snippet)
- [Google Search Central: JavaScript-generated structured data](https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript)
- [Google Search Central: build and submit a sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
