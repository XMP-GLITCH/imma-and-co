# Imma & Co Jewelry

Link-in-bio page for Imma & Co — jewelry making and retail.

**Live:** https://xmp-glitch.github.io/imma-and-co/

## What it is

A single self-contained `index.html`. No build step, no dependencies, no
JavaScript. The only external request is the Google Fonts stylesheet
(Cormorant Garamond + Jost). To work on it, open `index.html` in a browser.

## Structure

- **Links** — TikTok, and a WhatsApp button that opens an intent sheet
- **Intent sheet** — three options, each opening WhatsApp with a different
  prefilled message so the first thing you receive says what the customer wants
- **Viewport lock** — the page is pinned to the device height and never
  scrolls; spacing is fluid via `clamp()` so it compresses instead of cropping.
  Below 600px tall (landscape) scrolling is restored, otherwise the WhatsApp
  button would be unreachable.

## Editing the WhatsApp messages

Each `wa.me` link carries its message in the `?text=` parameter, URL-encoded.
Every link has a comment above it showing the plaintext.

**The `&` in "Imma & Co" must stay as `%26`.** A literal `&` ends the query
string and silently truncates the message to "Hi Imma ".

Other escapes in use: space `%20`, `'` `%27`, `:` `%3A`, `?` `%3F`,
wave emoji `%F0%9F%91%8B`.

## Known issues

- On mobile the intent sheet can open partially below the fold, requiring a
  scroll to see all three options. Not yet fixed.
- The grab handle on the sheet is decorative — swipe-to-dismiss is not
  implemented. Close by tapping the backdrop or using the back button.

## Share preview

`og:image` points at `share-preview.jpg`, which does not exist yet. Add a
1200x630 JPG or PNG (not SVG, WhatsApp won't read it) at the repo root and the
preview will start rendering in WhatsApp and social shares.
