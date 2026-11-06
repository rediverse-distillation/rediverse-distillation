# ReDiverse project page

Static site for *Restoring Diversity in Distilled Image and Video Generators by Probing Activations*, built on the
[Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template). No build step:
`index.html`, the template's stylesheets in `static/css/`, and `assets/` (about 240 MB):

- `assets/demo/`: an animated 55-second overview video (silent, 1080p) at the top of the page.
- `assets/img/`: prompts of the qualitative benchmark, nine noises per prompt at native 1024 px (the first nine whose student and ReDiverse samples passed an artifact check).
- `assets/vid/`: up to five seed-matched clips per prompt at native resolution (Wan 2.1 832x480, MiniMax-H3 1344x768).
- `assets/fig/`: figures from the paper.

This folder is the `website` branch of `H-furkan/rediverse`. To publish it (once the repo is public): Settings ->
Pages -> Deploy from a branch -> `website` / root. The page is then served at https://h-furkan.github.io/rediverse/.
The branch is deliberately not named `gh-pages`, because GitHub publishes a `gh-pages` branch automatically and
publicly, even from a private repository.

Local preview: `python3 -m http.server 8000` in this folder, then open http://localhost:8000.
