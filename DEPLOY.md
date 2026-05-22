# Embedding the artifact timeline in your Notion website

Two files are in this folder:

- `artifact-timeline.html` — fully interactive (zoom, branch focus, click-to-replay, author chips)
- `artifact-timeline-snapshot.svg` — static image of the bracket artifact, all branches and authors visible

Notion can render either, but they need different paths to get in. The interactive HTML needs a real web host; Notion's `/embed` block points at the URL. The static SVG can drop straight into Notion as an image.

Important: Figma is **not** a host for interactive HTML. A Figma file renders as design/prototype content inside Figma's viewer — it does not execute external HTML or JavaScript. If you want the timeline to be clickable inside Notion, use one of the hosts below. If you only need the visual, use the SVG path or import the SVG into Figma and embed the Figma file.

---

## Option A — static SVG into Notion (zero hosting)

1. Open your Notion page.
2. Type `/image` and choose the Image block.
3. Upload `artifact-timeline-snapshot.svg`.
4. Done.

Tradeoff: no interactivity. Best when you want a visual on the portfolio page itself and link out to the live version elsewhere.

## Option A2 — SVG via Figma, then embed Figma in Notion

1. In Figma: create a frame, drag `artifact-timeline-snapshot.svg` onto it.
2. Share → copy link (set access to "anyone with the link can view").
3. In Notion: type `/embed`, paste the Figma URL.

Tradeoff: still static, but Figma's viewer gives you zoom and pan on top of the image.

---

## Option B — interactive HTML, hosted on GitHub Pages (recommended)

Five steps, free, no build tools.

1. Create a new public GitHub repo (e.g. `artifact-timeline`).
2. Upload `artifact-timeline.html` to the repo. Rename it to `index.html` so the root URL serves it.
3. Repo → Settings → Pages.
4. Under "Source," choose `main` branch, `/ (root)` folder, save.
5. Wait ~60 seconds. Your URL is `https://<your-username>.github.io/artifact-timeline/`.

In Notion: type `/embed`, paste the URL, set the embed height to ~900px.

## Option B alternatives

If you'd rather not use GitHub:

- **Netlify Drop** (`netlify.com/drop`): drag the folder containing `artifact-timeline.html` (renamed to `index.html`) onto the page. Get a URL in 10 seconds. Free tier is generous.
- **Vercel**: `vercel deploy` from the command line, or drag-drop on the dashboard. Same result.
- **Cloudflare Pages**: connect a repo or upload a zip. Free, very fast.

All three accept a single HTML file. Pick whichever you already have an account on.

---

## Recommended setup for a portfolio piece

A common pattern that works well on a Notion portfolio page:

1. Embed the static SVG at the top of the section, large, as the "hero" visual.
2. Below it, embed the live HTML so the reader can interact without leaving the page.
3. A short caption explains what they're looking at and how to interact (drag the brush to zoom, click any node to replay).

This way the page reads correctly even if the embed fails to load (which Notion embeds occasionally do), and motivated readers get the interactive version.

---

## If you want me to tailor this further

Tell me which host you've picked (GitHub Pages, Netlify, Vercel, Cloudflare) and I'll give you the exact one-screen instructions for it. If you want a custom domain on top of it, that's another ten minutes — I can write those steps too.
