# ReDiverse project page

Static site for *Restoring Diversity in Distilled Image and Video Generators by Probing Activations*, built on the
[Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template). No build step:
`index.html`, the template's stylesheets in `static/css/`, and `assets/` (about 240 MB):

- `assets/demo/`: an animated 55-second overview video (silent, 1080p) at the top of the page.
- `assets/img/`: five prompts per model (SDXL, SD3), six seed-matched student / ReDiverse pairs each at native 1024 px.
- `assets/vid/`: up to five seed-matched clips per prompt at native resolution (Wan 2.1 832x480, MiniMax-H3 1344x768).
- `assets/fig/`: figures from the paper.

The page is published with GitHub Pages from `rediverse-distillation/rediverse-distillation` (Deploy from a branch ->
`main` / root) at https://rediverse-distillation.github.io/rediverse-distillation/. Pushing to that branch republishes the page. The same history is the `website` branch of
`H-furkan/rediverse`, which served the earlier address https://h-furkan.github.io/rediverse/; neither branch is named
`gh-pages`.

Local preview: `python3 -m http.server 8000` in this folder, then open http://localhost:8000.
