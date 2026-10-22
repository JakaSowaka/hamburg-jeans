# Jeans House Hamburg – Web-Relaunch

Pure HTML + CSS. No JavaScript, no framework, no external requests on page load.

## Structure

```
index.html        Start
beratung.html     Passform-Beratung (fit consulting, visit steps, long/wide sizes)
marken.html       Marken & Modelle (all brands and models from the old site)
ueber-uns.html    Über uns (old "Wir lieben Jeans" page + sustainability)
laden.html        Laden & Anfahrt (address, hours, route, Facebook)
impressum.html    Impressum (placeholders marked in yellow)
datenschutz.html  Datenschutzerklärung (placeholders marked in yellow)
css/style.css     One shared stylesheet, commented in German
fonts/            Zilla Slab + Work Sans, self-hosted (OFL licence)
img/              Placeholder images under their final file names
```

## Checklist from the briefing

| Requirement | Where |
|---|---|
| 3–4+ linked subpages | 5 main pages + 2 legal pages, same navigation everywhere |
| HTML5 semantics | `header`, `nav`, `main`, `section`, `aside`, `figure`, `address`, `footer`, `dl`, `ol`. Passes the W3C validator (HTML and CSS) with 0 errors |
| Flexbox / Grid | Grid: hero, split sections, steps, brand list, footer. Flexbox: header, nav, buttons, sizes |
| Responsive | Mobile first, breakpoints at 40em, 56.25em, 70em. Tested at 390 px and 1440 px |
| Visual concept | Denim indigo, logo red only for actions, orange "contrast stitching" for dashed lines, kraft-paper hang tag for opening hours |
| CTAs for the store | "Route planen" and phone number in the hero, header, and at the end of every page |

## Things worth explaining in your presentation

- **Mobile menu without JavaScript:** the `<nav>` uses the HTML `popover` attribute. The "Menü" button opens it with `popovertarget="hauptmenue"`. On desktop, a media query resets the popover styles so the nav is always visible.
- **Hang tag:** pure CSS. `clip-path` cuts the corners, a `::before` circle is the eyelet, a dashed border is the stitching, and on the homepage a thin `::before` line on the wrapper is the string. It swings in once on page load; this is switched off for people with "reduce motion" enabled.
- **Privacy (DSGVO):** fonts are self-hosted instead of loaded from Google, and the map is a link instead of an embedded Google Maps iframe. The site sends no data to third parties until a visitor clicks.

## Replacing the images

Generate each image, save it **with exactly the same file name** into `img/`, and it appears automatically. JPG, landscape or portrait as listed. Prompts are written for any image generator:

| File | Format | Prompt |
|---|---|---|
| `hero.jpg` | 16:9, ~1920×1080 | Warm, inviting interior of a small independent jeans store in Hamburg, wooden shelves filled with neatly folded jeans in many washes, a friendly sales assistant in her 50s helping a customer, soft afternoon light, documentary photography, shallow depth of field, darker left side for text |
| `beratung.jpg` | 4:5, ~1000×1250 | Sales assistant kneeling with a tailor's measuring tape checking the hem length of a customer's jeans in front of a fitting-room mirror, warm natural light, authentic, candid, editorial photo |
| `laden-aussen.jpg` | 3:2, ~1500×1000 | Exterior of a small jeans shop in a red brick building on a Hamburg street, large display windows with jeans, blue window frames, overcast northern German daylight, realistic street photography, no readable text |
| `regal.jpg` | 3:2, ~1500×1000 | Close-up of folded jeans stacked on wooden shelves, gradient from light wash to raw indigo to black denim, soft side light, texture detail, product photography |
| `team.jpg` | 3:2, ~1500×1000 | Two friendly shop owners in their 50s and 60s standing behind the counter of a cozy jeans store, wearing denim shirts, smiling, authentic local business portrait |
| `details.jpg` | 1:1, ~1200×1200 | Macro photo of dark indigo jeans details: copper rivet, orange contrast stitching, worn leather back patch without logo, studio light |
| `kundin.jpg` | 4:5, ~1000×1250 | Young woman in high-waisted dark jeans and sunglasses posing casually on a Hamburg street, natural light, fashion editorial |
| `kunde.jpg` | 4:5, ~1000×1250 | Older man in his 60s sitting on a wooden chair wearing classic straight jeans and a vest, relaxed, warm light, character portrait |

Tip: avoid visible brand logos in the generated images.

## Open points for the client

- **Opening hours conflict:** the old homepage says Mo.–Fr. until 18:00, the old Kontakt page says until 19:00. The new site uses 18:00 everywhere; confirm and change in all pages if needed.
- **Logo:** the header uses a typographic version of the logo. Swap in the original logo file inside `<a class="logo">` if you have it.
- **Impressum / Datenschutz:** the old Impressum could not be read automatically. Copy the yellow-marked details from https://www.hamburg-jeans.de/impressum/ before going live.

## Deployment

Upload the whole folder (keep the folder structure) to the free hoster. `index.html` must be in the root. All links are relative, so it works on any URL.
To test locally, open `index.html` in the browser, or for exact hoster behaviour run `python3 -m http.server` in this folder and open http://localhost:8000.
