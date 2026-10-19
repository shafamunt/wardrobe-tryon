# Wardrobe Try-On App Shell

A mobile-friendly, local-first closet and outfit preview app for Shafayet (Project 2 of 4).

## What it is

- Upload photos of your own clothes (photos stay on the device, saved in the browser's IndexedDB).
- Organize them into categories: Tops, Bottoms, Dresses, Outerwear, Shoes, Accessories.
- Rename items and delete them.
- Build outfits in the Try-On tab by picking one item per slot over a neutral mannequin silhouette.
- An "AI try-on (coming soon)" button is present but disabled. The AI garment swap comes later, once real photos exist.
- Two closets: "My closet" and "Wife's closet." A profile switcher in the header flips between them; each closet has its own photos and its own saved outfit picks. Items are tagged with a `profile` field in IndexedDB, and outfits live under per-profile localStorage keys (`wardrobe-outfit-v1-me`, `wardrobe-outfit-v1-wife`). Records saved before profiles existed are treated as "me".

The app ships with zero sample inventory. Every empty view explains what to add and how.

## How to run it locally

No build step, no server, no dependencies. Just open the file in a browser:

```
open wardrobe.html
```

Or double-click `wardrobe.html` in your file manager. Everything (CSS, JS, the mannequin SVG) is inlined in that one file.

Hosted artifact slug: `wardrobe-try-on` (web_static). Open and share it from its artifact card in Muse.

## Continuing this work

Another AI picking this up should:

1. Read `wardrobe.html`. It is the entire app: inline CSS in `<style>`, inline JS at the bottom of `<body>`.
2. Key areas to edit:
   - `CATS` and `SLOTS` near the top of the script for categories and outfit slots.
   - `renderCloset()` / `itemCard()` for the closet grid.
   - `renderSlots()` / `renderTryonSummaryOnly()` for the try-on canvas.
   - The IndexedDB helpers (`openDb`, `dbAdd`, `dbGet`, `dbPut`, `dbDel`, `dbAll`) for persistence.
3. Keep the standing rules: plain punctuation (no em dashes), no fake inventory, photos stay client-side, disabled AI features must stay clearly labeled as future.
4. When the work is done, hand the result back to Shafayet's Muse so it can rebuild and redeploy the hosted artifact. Do not publish or share the file anywhere yourself.

## Status

Shell only. Waiting on Shafayet's clothing photos (one by one, plain backgrounds) before the AI try-on feature can be built.
