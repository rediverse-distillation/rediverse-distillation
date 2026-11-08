# ReDiverse project page

Static site for *Restoring Diversity in Distilled Image and Video Generators by Probing Activations*, built on the
[Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template) in the layout of the
[BudgetPix page](https://karaozgur.com/BudgetPix/) (its `static/css/index.css`, ruled section titles, tabbed slideshows).
No build step: `index.html`, `static/css/` (Bulma and index.css), and `assets/` (about 240 MB):

- `assets/demo/`: an animated 55-second overview video (silent, 1080p) at the top of the page.
- `assets/img/<key>/{student,rediverse}_{0..5}.jpg`: twelve prompts per model (SDXL, SD3), six seed-matched pairs each at
  native 1024 px. The seven newest per model come from the rated pools of the `ReDiverse_results` Drive folder (seeds picked
  by eye from each prompt's preview). No prompt is used for both models.
- `assets/vid/<key>/{student,rediverse}_{0..4}.mp4`: eight prompts per model, five seed-matched clips each, at native
  resolution (Wan 2.1 832x480, MiniMax-H3 1344x768), except `h3_forest`, `h3_candle`, `wan_forest` and `wan_carousel`,
  which are the reviewer site's 640 px renders (the native clips are on the server).
- `assets/fig/`: figures from the paper.

The page is published with GitHub Pages from `rediverse-distillation/rediverse-distillation` (Deploy from a branch ->
`main` / root) at https://rediverse-distillation.github.io/rediverse-distillation/. Pushing to that branch republishes the page. The same history is the `website` branch of
`H-furkan/rediverse`, which served the earlier address https://h-furkan.github.io/rediverse/; neither branch is named
`gh-pages`.

The example lists are `VIDS` and `IMGS` near the bottom of `index.html` (`[key, prompt]` per slide).

Local preview: `python3 -m http.server 8000` in this folder, then open http://localhost:8000.
