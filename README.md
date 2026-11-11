# ReDiverse project page

Static site for *Restoring Diversity in Distilled Image and Video Generators by Probing Activations*, built on the
[Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template) in the layout of the
[BudgetPix page](https://karaozgur.com/BudgetPix/) (its `static/css/` and `static/js/` files, fonts, ruled section titles,
tabbed slideshows). No build step: `index.html`, `static/`, and `assets/` (about 280 MB):

- `assets/demo/`: an animated 73-second overview video (silent, 1080p) at the top of the page: the 55-second render
  re-timed with ffmpeg (the finished state of the dense slides is held longer, the two clip slides play at 0.75x).
- `assets/img/<key>/{student,rediverse}_{0..5}.jpg`: twelve prompts per model (SDXL, SD3), six seed-matched pairs each at
  native 1024 px. The seven newest per model come from the rated pools of the `ReDiverse_results` Drive folder (seeds picked
  by eye from each prompt's preview). No prompt is used for both models.
- `assets/vid/<key>/{student,rediverse}_{0..4}.mp4`: eight MiniMax-H3 and ten Wan 2.1 prompts, five seed-matched clips
  each, at native resolution (Wan 2.1 832x480, MiniMax-H3 1344x768), except `h3_forest`, `h3_candle`, `wan_forest`,
  `wan_carousel`, `wan_hummingbird` and `wan_lion`, which are the reviewer site's 640 px renders (the native clips are on
  the server).
- `assets/cmp/`: the Method Comparison section, from the anonymous reviewer site (https://iclr-2027-14418.github.io/,
  downloaded only, never modified): `img/<key>/{student,dpdmd,noiseopt,rediverse}_{0..5}.jpg` (512 px, the same six seeds
  in every row) and `vid/<key>/{student,dfd,rediverse}_{0..4}.mp4`; for `h3_forest`, `h3_candle`, `wan_forest` and
  `wan_carousel` only the DFD clips are here, the student and ReDiverse clips are the `assets/vid/` ones.
- `assets/fig/`: figures from the paper.

The page is published with GitHub Pages from `rediverse-distillation/rediverse-distillation` (Deploy from a branch ->
`main` / root) at https://rediverse-distillation.github.io/rediverse-distillation/. Pushing to that branch republishes the page. The same history is the `website` branch of
`H-furkan/rediverse`, which served the earlier address https://h-furkan.github.io/rediverse/; neither branch is named
`gh-pages`.

The example lists are `VIDS`, `IMGS` and `CMP` near the bottom of `index.html` (`[key, prompt]` per slide). Video Results
and Image Results show each prompt as a student-to-ReDiverse dial: ReDiverse's sample (or clip, played in step) is wiped in
over the student's sample of the same noise. The Method figures sit side by side.

Local preview: `python3 -m http.server 8000` in this folder, then open http://localhost:8000.
