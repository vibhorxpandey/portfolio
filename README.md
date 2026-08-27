# vibhorpandey.in

`FACTS.md` is authoritative. The site copy and both resume variants derive their numbers
from it — never the other way around. If a fact changes, update `FACTS.md` first, with
its source, then propagate to `index.html` and `resume.tex`.

One `index.html` and `/media/`. No build step, no bundler, vanilla JS. Edit and deploy.

**Add a project:** add a `.vent` block in `01 Building` (or a `<tr>` in `03 Evidence` if it has a measured result), then add a matching entry to the `DOCS` array in the script — the retriever only knows what is in `DOCS`, and the load counter reads `DOCS.length` automatically.

**Add a video:** put `slug-1400.mp4`/`.webm` plus `slug-poster.jpg` in `/media/`, copy a `figure.fig.reveal` block, swap `<picture>` for `<video muted playsinline loop preload="metadata" poster="...">`, and keep `width`/`height` set so nothing shifts on load.
