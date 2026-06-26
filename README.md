# Niko J Mtema — Portfolio

Single-page architectural design portfolio. Static HTML/CSS/JS — no build step.

## Repo structure

```
your-repo/
├── index.html              ← the site (GitHub Pages serves this automatically)
├── Niko-Mtema-CV.pdf       ← your CV (optional but the "Download CV" buttons link to it)
└── images/
    ├── hero.jpg            civic / library building (hero, top right)
    ├── hotel-1.jpg         5-star hotel — dusk twin towers (gallery lead)
    ├── hotel-2.jpg         5-star hotel — pool aerial
    ├── hotel-3.jpg         5-star hotel — living room
    ├── hotel-4.jpg         5-star hotel — bedroom suite
    ├── res-1.jpg           residential house — night
    ├── res-2.jpg           residential house — daylight
    ├── housing-1.jpg       affordable housing — aerial sunset (lead)
    ├── housing-2.jpg       affordable housing — street corner
    ├── housing-3.jpg       affordable housing — colour window framing close-up
    ├── interior-1.jpg      interior — living room w/ TV
    ├── interior-2.jpg      interior — dining room
    ├── interior-3.jpg      interior — dark Eames lounge
    ├── interior-4.jpg      interior — bright living room (gallery lead)
    ├── interior-5.jpg      interior — bedroom, teal + orange
    ├── marble-1.jpg        marble — bathroom w/ tub
    ├── marble-2.jpg        marble — media wall
    ├── marble-3.jpg        marble — double-height dining + staircase (lead)
    ├── marble-4.jpg        marble — warm-wood bedroom
    ├── marble-5.jpg        marble — home cinema
    ├── sketch-1.jpg        cafeteria site plan 1:200      (already placed)
    ├── sketch-2.jpg        ground floor plan              (already placed)
    ├── sketch-3.jpg        section A–A                    (already placed)
    ├── sketch-4.jpg        construction details           (already placed)
    ├── sketch-5.jpg        coloured elevations            (already placed)
    └── sketch-6.jpg        colour-pencil perspective      (already placed)
```

The 6 `sketch-*.jpg` files are already in `images/`. You still need to add the 20
render images above (save them from chat with these exact lowercase names).

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `portfolio`).
2. Upload `index.html`, the `images/` folder, and your CV.
3. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*,
   Branch = `main`, folder = `/ (root)`. Save.
4. Wait ~1 minute. Your site is live at `https://<username>.github.io/portfolio/`.

## Notes

- The spinning globe loads the `cobe` library and the fonts from CDNs over HTTPS —
  works on GitHub Pages out of the box (needs an internet connection to render).
- The contact form uses a `mailto:` action. For reliable delivery on a live site,
  consider routing it through [Formspree](https://formspree.io) or Netlify Forms.
- All image paths are relative, so the site also works if you open `index.html`
  locally once the `images/` folder is populated.
