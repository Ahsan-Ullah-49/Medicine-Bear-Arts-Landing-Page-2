# Deployment and release checklist

## What can be deployed

This repository is a static frontend. It requires no server process, database, package installation, or environment variables. The browser communicates directly with Shopify's public Storefront API and then redirects buyers to the Shopify checkout URL returned for the active cart.

Use an HTTPS static host. GitHub Pages is suitable for a client preview. A final advertising launch should use the client-approved domain and hosting plan.

## Cart and order source

The sales landing page uses a separate browser cart key and cart-ID namespace, and adds `sales_channel` / `sales_domain` cart attributes on cart creation. The original page is not edited. Both pages currently use `medicine-bear-arts.myshopify.com`; orders remain in the same Shopify store. The attributes are intended to distinguish sales-page orders, but no test order has confirmed the finished order record and browser-supplied values can be changed. Native Shopify channel attribution is not configured: `CartInput.sourceName` requires a value owned by the Storefront access token, and this project has no dedicated channel token/source name. If the requirement is a separate Shopify admin/order database, configure a second Shopify store and its catalog and checkout before launch.

## Requested sales subdomain

The requested hostname is `sales.medicinebeararts.com`. The repository's canonical tag, social URL, JSON-LD, robots file, and sitemap are prepared for that hostname, but the host has not been selected and no DNS or deployment change has been made. A DNS lookup on 2026-11-14 returned that the name does not exist. The local Git repository has no remote. Do not point DNS or publish until the owner selects the host and confirms the production release.

After the host is selected, use the exact DNS target and verification instructions shown by that provider, enable HTTPS, and confirm the site is served at the requested hostname. Do not guess a provider-specific CNAME target. Keep any host-specific domain file or workflow out of this provider-neutral project until the host is chosen. Then verify the homepage, `robots.txt`, `sitemap.xml`, canonical host, product query URLs, and Shopify checkout on the deployed site. See [SEO.md](SEO.md) for indexing and Search Console steps.

## GitHub Pages

1. Create a new GitHub repository.
2. Upload the complete project root. Keep `index.html`, `css/`, `js/`, `assets/`, `docs/`, `README.md`, and `.gitignore`.
3. Open **Settings → Pages** in the repository.
4. Set the source to **Deploy from a branch**.
5. Select the intended branch and the root folder (`/`).
6. Wait for the deployment URL from GitHub Pages.
7. Test the HTTPS URL before sharing it with the client.

## Required post-deployment checks

- Open the default product and every configured `?product=<slug>` URL.
- Confirm the product image gallery, title, CAD price, availability, and options load from Shopify.
- Add an available product to the bag, adjust quantity, remove it, add a second product, and confirm totals remain CAD.
- Use **Continue to secure checkout** and verify Shopify receives the cart. Do not place an order unless the merchant authorizes a test order.
- Test the WhatsApp links, floating bag, theme toggle, review controls, desktop layout, and a mobile device.
- Check browser console errors and failed network requests.

## Client and Shopify checks

The page cannot independently confirm the merchant's shipping profiles, taxes, payment providers, checkout branding, inventory policy, or order status. Confirm those settings inside Shopify before running paid traffic.

## Performance work before paid ads

The supplied product PNGs are approximately 72 MB in total. Generate client-approved WebP or AVIF delivery copies and responsive sizes before an advertising launch. Preserve original client files outside the deployed build and update `js/products.js` with the optimized copy paths only after verifying each product image.

## Rollback

For GitHub Pages, restore the last known working commit or select the previous successful deployment in GitHub Pages. Shopify's existing store, theme, carts, and checkout remain independent from this static frontend.
