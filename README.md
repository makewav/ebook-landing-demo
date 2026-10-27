# The Quiet Engine — ebook landing page

Open `index.html` by double-clicking it in a browser: it is plain HTML + CSS with no build step, no npm and no network requests, and it renders straight from the filesystem (keep `index.html`, `styles.css` and `assets/` in the same folder so the relative paths keep working). All visible copy comes verbatim from Part 2 of `SPEC.md`; everything the spec did not supply is left as a clearly marked placeholder, listed below.

## Placeholders to replace before launch

| # | Where | What is there now | Replace with |
|---|-------|-------------------|--------------|
| 1 | `#proof` section | The whole section is a placeholder block reading exactly `[TODO: social proof — verified testimonials only]` | Verified social proof only. Nothing was published here on purpose: no ratings, review counts, reader counts, country counts, "featured in" logos, testimonials or attributed quotes, real or invented. Add the 4-stat row, the publication row, the 3 testimonial cards, the review line and the pull-quote band only once you have verified quotes, consented names and licensed logos. |
| 2 | All buy buttons | `https://example.com/checkout/ebook` and `https://example.com/checkout/pack` | Your real checkout URLs for the ebook and the Full Engine Pack (both CTAs must point at the same configured product IDs) |
| 3 | `<head>` | `https://example.com/the-quiet-engine` (canonical, `og:url`) and `https://example.com/assets/cover.svg` (`og:image`, `twitter:image`) | Your real domain, plus a 1200×630 PNG card image (the SVG cover is not a valid social card) |
| 4 | `assets/cover.svg` | Placeholder 3D mockup cover | Real cover art |
| 5 | Author block (`#author`) | Inline placeholder portrait and inline placeholder signature; name, role, bio and credential rows are the spec's illustrative copy | Real headshot (160px, circular), real signature image, and the real author's name, title, bio and credentials |
| 6 | "More from Rae →" link | `href="#"` (`data-placeholder="author-archive"`) | Your author archive / newsletter URL |
| 7 | Footer links | Refund policy, Terms, Privacy and both product links point at `href="#"` (`data-placeholder="refund-policy-url"`, `terms-url`, `privacy-url`, `product-url`) | Real policy pages and product links |
| 8 | Footer note | `[TODO: delivery and VAT / sales-tax note for digital products]` | Your delivery and VAT / sales-tax note (the spec supplies no shipping copy) |
| 9 | Support email | `hello@quietengine.co` (hero, FAQ, final CTA, footer) | Your real support inbox |
| 10 | Legal line in `#final-cta` | "Prices in USD. Product and company names in reader testimonials and statistics are illustrative examples for this page spec unless you replace them with verified quotes." | Keep it, but confirm it still matches the page once real testimonials and statistics are added back |

## Notes on what is not built here

- **Analytics** (SPEC Part 3, items 22–26): no `cta_click`, `checkout_start`, `lead_submit`, `faq_expand` or `scroll_depth` events fire. This static page has no analytics platform attached.
- **Email capture** (SPEC Part 3, item 18): no capture form, because a form needs a real provider endpoint and a success state, and a dead form would break on `file://`. Add it in the FAQ section, above the accordion, tagging the source `ebook_landing`.
- **Post-purchase delivery, refunds, VAT notes, sitemap/robots.txt and the OG card image** are deployment tasks (SPEC Part 3, items 21, 29, 30, 43–47) and are not part of this static build.
- **FAQ implementation**: the accordion uses native `<details>` / `<summary>` (first item open, every answer present in the HTML source, keyboard operable with Enter and Space) instead of JS-driven `aria-expanded` buttons, so the only JavaScript on the page is the mobile nav toggle and the launch countdown.
- **Countdown**: one small inline `<script>` counts down to Nov 12, 2026 23:59 ET. When it expires the timer hides, the copy switches to "Launch pricing has ended — standard price below", prices revert to $49 / $129, and the bonus row hides. To preview that state locally, temporarily change `LAUNCH_END` in the inline script to a past date.
- **No social proof is published anywhere** — not in the hero, the author block, the offer or the footer.
