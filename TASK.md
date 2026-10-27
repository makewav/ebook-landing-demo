# Build task: ebook launch landing page

Build a single static landing page from `SPEC.md` in this directory.

## Deliverables

- `index.html` — the page. One file.
- `styles.css` — all styling, linked from `index.html`.
- `assets/cover.svg` — a simple placeholder ebook cover (3D-ish mockup look is nice, plain is fine).
- `README.md` — one short paragraph: how to open the page, and any placeholders the buyer must replace.

## Rules

1. **Copy comes from `SPEC.md`.** Use Part 2's headlines, subheads, body and CTAs **verbatim**. Do not rewrite, shorten or "improve" the copy. If Part 2 does not cover something Part 1 requires, use a clearly marked placeholder like `[TODO: guarantee text]` rather than inventing claims, prices, testimonials or statistics.
2. **No social proof — real, implied, or invented.** Do not add "featured in" / "as seen in" logos, publisher or press badges, reader counts, ratings, review counts, country counts, testimonials, or quotes attributed to anyone. The spec supplies none of these, and inventing them is false advertising. Where Part 1 asks for a proof or credibility section, render that section as an obvious placeholder block containing exactly `[TODO: social proof — verified testimonials only]`. List every such gap in `README.md`.
3. **Vanilla only.** No frameworks, no bundlers, no build step, no npm. Plain HTML + CSS. Inline SVG is fine. No external JS libraries — a small inline `<script>` for the mobile nav toggle is the only JS allowed.
4. **No network dependencies except Google Fonts.** If you prefer, use system font stacks and skip webfonts entirely.
5. **Responsive.** Mobile-first: single column under 768px, the two-column hero on desktop. Test the layout mentally at 360px, 768px, 1280px.
6. **Accessible basics.** Semantic landmarks (`header`, `main`, `section`, `footer`), one `h1`, real `alt` text on the cover, visible focus states, buttons are `<button>`/`<a>` not divs, colour contrast that passes AA for body text.
7. **Section order and anchors from Part 1.** Give each section the `id` Part 1 specifies (e.g. `#hero`), so nav links work.
8. **Sticky CTA.** If Part 1 calls for a floating badge or sticky buy bar, implement it with CSS only where possible.

## Animations — required in this revision

The client reviewed the current page and called it fantastic. Keep the design, copy, layout and structure **exactly as they are** — do not redesign, re-word, or re-order anything. This revision adds motion only.

Add:

1. **Scroll-reveal.** Sections and cards fade + rise (about 24px) into view as they enter the viewport, using one small `IntersectionObserver` in an inline script. Reveal once, then stop observing that element. Stagger card grids by ~60ms per item via a CSS custom property, not per-element CSS.
2. **Hero entrance.** On load, the headline, subhead, CTAs and the book mockup animate in with a short stagger (total under ~800ms). The mockup gets a slow, subtle float loop afterwards.
3. **Buttons.** Smooth colour/transform transitions on hover, a slight press-down on `:active`, and a soft glow on the primary CTA. Nothing that pulses forever or distracts from reading.
4. **Cards.** Gentle lift (translateY + shadow) on hover.
5. **Countdown.** Digits get a brief flip/fade whenever a unit changes.
6. **Smooth anchor scrolling** for the nav links, with the sticky header offset taken into account.

Rules for the animations themselves:

- **Transform and opacity only.** No animating `width`, `height`, `top`, `left` or `margin` — it thrashes layout.
- **Respect `prefers-reduced-motion: reduce`.** In a media query, switch every animation and transition off and make all reveal targets visible immediately. This is not optional; the page must be fully usable with motion disabled.
- **No new dependencies**, no animation libraries, no CSS frameworks. Vanilla CSS + the same small inline script.
- **No layout shift.** Elements must occupy their final space before animating in, so nothing jumps as the user scrolls (`content-visibility` or a reserved min-height where needed).
- **Never hide content from search engines or a broken JS load.** If the script fails, content must still be visible — drive the hidden state from a class the script adds, not one baked into the HTML.

## Definition of done

- `index.html` opens directly from the filesystem (double-click) with no console errors and no missing assets.
- Every section in Part 1 exists in the page, in order, with the `id` from the spec.
- Every CTA from Part 2 is present and styled as a button.
- `styles.css` contains no unused selector blocks, and no `!important` unless a comment explains why.
- `README.md` lists each placeholder you left.

## Working style

Do the work: create the files. Do not ask questions, do not summarise the spec back, do not write a plan document. When you are done, print a short completion note listing the files you created and the placeholders you left.
