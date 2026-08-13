# Niko J Mtema — Portfolio

Two ways to view the same work, no build step (static HTML/CSS/JS):

- **`index.html`** — an interactive 3D "mini world". Fly between project buildings on an
  island, click one to open its galleries, and step into interiors.
- **`portfolio.html`** — the classic scrolling portfolio (about, skills, projects, contact).

The two pages link to each other, and both link to the CV.

## Repo structure

```
your-repo/
├── index.html              ← 3D world  (GitHub Pages serves this automatically)
├── portfolio.html          ← classic scrolling portfolio
├── Niko-Mtema-CV.pdf        ← CV (the download buttons link to it)
├── images/                  ← all project images (26 files)
└── models/                  ← OPTIONAL: drop custom .glb 3D models here (see below)
```

## Deploy to GitHub Pages

1. Upload `index.html`, `portfolio.html`, `Niko-Mtema-CV.pdf`, and the `images/` folder.
2. Settings → Pages → Source = *Deploy from a branch* → Branch `main` → folder `/ (root)`.
3. ~1 minute later the 3D world is live at `https://<username>.github.io/<repo>/`.

## Adding a NEW project to the 3D world

Everything is driven by one config list near the top of the `<script type="module">`
block in `index.html` — look for `const PROJECTS = [ … ]`. Copy a block and fill it in:

```js
{
  id:'newproject',              // unique short id
  title:'New Project',
  sector:'Residential',         // small label above the title
  status:'Studio Project',
  angle:15,                     // where it sits on the island ring (0-360 degrees)
  type:'pavilion',              // massing style if you have no 3D model:
                                //   'tower' | 'blocks' | 'house' | 'pavilion' | 'plate'
  color:0xd8cfc1,               // main building colour
  hero:'images/new-1.jpg',      // the photo shown on the project's billboard sign
  exterior:['images/new-1.jpg','images/new-2.jpg'],
  interior:['images/new-int-1.jpg'],   // shown by the "Enter interior" button ([] if none)
  sitePlan:'images/new-plan.jpg',      // optional — adds a "Site plan" button
  model:'models/new.glb',              // optional — loads YOUR 3D model instead of the massing
  blurb:'One paragraph describing the project.'
}
```

Camera framing, the floating label, the photo billboard, hover and click are all
generated automatically. Drop the referenced images in `images/` (and any `.glb` in
`models/`) and it appears in the world — no other code changes needed.

### Custom 3D models (optional)
If you export a project as a small **glTF `.glb`**, set its path in `model:` and it
replaces the auto-generated massing on that plot. Keep models low-poly and under a few MB
so the page stays fast. If a model fails to load, the world falls back to the procedural
massing automatically.

## Notes

- The 3D world loads Three.js and the fonts from CDNs over HTTPS — works on GitHub Pages,
  needs an internet connection. If a device can't run WebGL, it shows a link to
  `portfolio.html` instead.
- The contact form (on `portfolio.html`) posts to FormSubmit.co → `mnick123456@gmail.com`.
  Submit it once on the live site and click the confirmation email to activate delivery.
- Images are compressed for fast loading. Keep new images web-sized (≈1600px, < ~500 KB).
