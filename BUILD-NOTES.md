# Kiwiseal Roofing site, build notes

Built with Skill 02 (`website-build-rules`) from `../context.md` and `../BRAND.md`.
Design system lifted from the reference build at
`github.com/pavlegosicsales-cell/projektni-biro-kos` (live: projektni-biro-kos.vercel.app).

## What was taken from the reference, and what was not

**Taken as is:** the whole component anatomy and motion system in `styles.css`, plus
`main.js` and `lenis.min.js`. Floating pill nav with its three scroll states, the
38 percent hero wash, the word by word heading split, scroll reveal, the sticky
stacking project cards, the subgrid warranty cards, the overlapping process panels,
the FAQ accordion, the wizard, and the whole footer.

**Changed:** the palette tokens and every hard coded navy `rgba()` behind them, the
button colour logic, the nav logo lockup, and one new component (`.choice-ico`).
All Serbian comments translated.

## Section mapping

| Kiwiseal section | Reference block it uses |
|---|---|
| Hero | `.hero` |
| About + stats | `.overview-top` + `.stat-row` |
| Who we work for (3 cards) | `.feature-grid` |
| Services (photo + 5 rows) | `.services-split` |
| Our work (3 sticky cards) | `.project-stack` |
| Why Kiwiseal (2 cards) | `.warranty-split` |
| How it works (3 steps) | `.process-grid` |
| Reviews | `.testi-grid` |
| FAQ | `.faq-split` |
| Before we started (2 cards) | `.work-grid` |
| Footer | `.footer` |
| Contact wizard | `.wizard` |

Every section the reference has is used, and every section Kiwiseal needs found a
home. Nothing was dropped for want of a matching block.

## Palette

Reference navy `#151F38` / orange `#DF7F41` replaced with Kiwiseal navy `#142342`
(sampled from the logo tile, and the text colour the live site already uses) and
membrane orange `#F6AD55` (the live site CTA colour).

The reference put white text on a burnt orange button. Kiwiseal's orange is too
light for that, and the live site already pairs it with navy text, so the button is
`#F6AD55` with `#142342` text, about 7.6:1. It flips to navy with white text on
hover. `--flame-deep` (`#B4631B`) is the contrast safe tone and is the only orange
allowed to carry white text: stat tiles, step tags, work dates, accent words on light.

## Fonts

Kept the reference stack: Outfit (display), Noto Sans (body), Inter (h3 and h4).
Poppins and Roboto on the old site are the GoHighLevel defaults, not a brand choice,
so there was nothing to preserve. Easy to swap in the design pass if you want.

## Images

`images/` holds 21 files prepared from two sources:

- Aerial and roof detail shots extracted from the old site's CDN. Those files were
  multi megabyte SVGs with base64 rasters inside; the rasters were pulled out and
  saved as JPEGs.
- Job, crew and before/after photos from the client's Facebook album.

The six before/after photos arrived with a headline burned into the top of the frame
(`BELLEVUE ROAD / ROOF RESTORED` and so on). Each is re-cropped from the original
with the top 31 percent removed, so no card ships a photo with text sitting on it.

The footer band was originally the branded Kiwiseal van banner, which has the
company name and strapline printed across it. A photo with text on it under a
headline reads badly, so it was swapped for a clean aerial of a restored roof.

`logo.png` is the transparent white emblem, trimmed to its content. Because the mark
carries its own tiny wordmark inside the wreath, which is unreadable at nav size, the
nav runs a lockup instead: the badge on a navy tile next to a set `KIWISEAL` wordmark
that inverts with the bar.

## Still to do

1. **Form backend.** `ENDPOINT` at the top of `main.js` is empty. Run Skill 03.
2. **Which inbox** should the form notify, `sales@` or `info@`?
3. **Waikato branch** has no address or phone yet, so it is a region option in the
   form but has no entry in the contact page branch list.
4. **Videos.** Seven exist on the old site but could not be pulled. If the client
   supplies them, the hero and the process steps are the natural homes.
5. The **cost calculator** from the old site (`/roofing-price-calculator`) is not in
   this build. Worth adding as a fourth page.
