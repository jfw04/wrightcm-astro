# Project photo workflow

## Where photos come from
Only from that project's own `Pictures\Marketing` folder. Nothing else.

## How you control order and the hero
Rename files in that folder with a two-digit prefix:

```
00_IMG_9501.JPEG   <- HERO. The 00_ file is always the hero.
01_IMG_3985.JPEG   <- first photo in the story
02_IMG_6792.JPEG
03_IMG_5105.JPEG
...
IMG_7881.JPEG      <- no prefix = held back, not published
```

Two rules, that's the whole system:

1. **`00_` is the hero.** The big photo behind the page title.
2. **Prefixed = published, in that number order. Unprefixed = held back.**

To promote a photo, give it a number. To pull one off the page, remove its
prefix. To reorder, renumber. Gaps are fine (`01, 02, 05`) — order is what
matters, not the exact digits. Sort the folder by Name in Explorer and you're
looking at the page order top to bottom.

## What you don't control this way
The *layout* — which photos run full-width, which pair up side by side, and
which land in the closing gallery — lives in `src/data/projects/<slug>.json`.
Tell me the order you want and I re-flow the layout to match, so the pairs
still balance and the wide shots still land on the wide slots.

## When you change the numbering
Say so and I'll regenerate. That means:
- re-reading the Marketing folder in its new order
- rebuilding the 640 / 1024 / 1600 webp + jpg derivatives
- rebuilding the 3:2 index card and the 1200x630 social image
- re-flowing the layout and rewriting the alt text for anything that moved

Alt text is written per photo from what is actually visible in it, so a photo
that changes slots keeps its own description.

## Contact sheet
`_CONTACT-SHEET.jpg` in the Marketing folder shows every photo with its current
filename, so you can pick numbers without opening them one at a time.
Regenerate it whenever the folder changes.
