# ReDiverse project page

Static site for *Restoring Diversity in Distilled Image and Video Generators by Probing Activations*, built on the
[Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template) in the layout of the
[BudgetPix page](https://karaozgur.com/BudgetPix/) (its `static/css/` and `static/js/` files, fonts, ruled section titles,
tabbed slideshows). No build step: `index.html`, `static/`, and `assets/` (about 310 MB):

- `assets/demo/`: a 97-second overview video (silent, 1080p) at the top of the page. After a two-second title it states
  the problem ("Current distilled models are not diverse."), zooms into a full-screen 2x2 grid of MiniMax-H3 Turbo clips
  (an airplane, then the paper's Istanbul ferry), introduces ReDiverse and reveals its clips with a before/after slider
  that sweeps across the frame. A Manim animation shows why diversity collapses and how ReDiverse restores it. Then one
  page per student model, each opening on the model's name: MiniMax-H3 (hot air balloon, autumn forest) and Wan 2.1
  lightx2v (dog) full screen, then SDXL DMD2 (dog, violin), SD3 TDM (backpack, bed) and SDXL-Turbo (cat, fork), two
  prompts side by side with every image shown whole. It ends on the paper title, authors and affiliations. Clips play
  whole, at their original speed. Every tile pairs a student sample with the ReDiverse sample of the same seed, except
  the Istanbul grid, which, like the paper's Fig. 7, pairs different clips. The Wan clips are motion-interpolated from
  16 to 32 fps. The SDXL DMD2 violin is the paper's Fig. 21 sample, and the SDXL-Turbo images come from additional runs;
  the other clips and images are the ones in `assets/vid/` and `assets/img/`.
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
`main` / root) at https://rediverse-distillation.github.io/rediverse-distillation/, its only address. Pushing to that
branch republishes the page; the branch is not named `gh-pages`.

The example lists are `VIDS`, `IMGS` and `CMP` near the bottom of `index.html` (`[key, prompt]` per slide). Video Results
and Image Results show each prompt as a student-to-ReDiverse dial: ReDiverse's sample (or clip, played in step) is wiped in
over the student's sample of the same noise. An `IMGS` entry `[key, prompt, { lerp: N }]` replaces the wipe of that
prompt by N interpolation frames `assets/img/<key>/lerp/<tile>_<jj>.jpg` (tile 0..5, jj = 00 for the student to N-1 for
ReDiverse; each frame is sampled with the student plus jj / (N-1) of ReDiverse's change), cross-faded by the dial; no
prompt uses it yet. The Method figures sit side by side.

Local preview: `python3 -m http.server 8000` in this folder, then open http://localhost:8000.
