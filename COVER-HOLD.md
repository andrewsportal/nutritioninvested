# Cover on hold

The book cover came off nutritioninvested.com on 20 October 2026 so it can't be copied from the site. This branch is `main` as it was just before (commit `d0b331b`), with the cover still in place.

## What's held here

- `cover.jpg`: 832 x 1248, 164 KB. The cover exactly as it ran on the site, byte for byte.
- `share.jpg`: 1200 x 630, 50 KB. The link-preview image built from it.

## What `main` changed (commit `9cfa106`)

- The buy page shows `cover-placeholder.svg`, a title card in the same 832 x 1248 shape, so the layout didn't move. Its box matches the cover's to the pixel at phone, short-phone, tablet and desktop sizes.
- `share.jpg` on `main` is the title card on the page background.
- The book's `"image"` line came out of the structured data, and `og:image:alt` reads "Nutrition, Invested by Andrew Rios".
- `cover.jpg` was deleted from `main`.

## Putting it back

- If nothing near those lines has changed since `9cfa106`: `git revert 9cfa106` restores all of it exactly.
- Otherwise, on `main`:
  1. Copy `cover.jpg` and `share.jpg` from this branch.
  2. Point the cover `<img>` back at `./cover.jpg` with alt text "Nutrition, Invested book cover".
  3. Restore `"image": "https://nutritioninvested.com/cover.jpg",` in the Book structured data, after `"url"`.
  4. Set `og:image:alt` back to "Nutrition, Invested book cover".
  5. Delete `cover-placeholder.svg`.
- If a new cover replaces this one, save it as `cover.jpg` and rebuild `share.jpg` from it: 1200 x 630, the cover 560px tall, centered on `#F1F4EF` with a soft shadow.
