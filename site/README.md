# Altorabi Design Guide — static site

The Design Guide from the Claude Design handoff (`project/Altorabi Design Guide.dc.html`),
rebuilt as plain HTML/CSS. No build step: open `index.html` or serve the folder.

```
python3 -m http.server -d site 8000   # then http://localhost:8000
```

- `css/tokens.css` — the §13 token block verbatim, plus a `[data-theme="dark"]` set. Any element
  with `data-theme="dark"` re-resolves every token, so components work on both grounds.
- `css/base.css` — STC `@font-face`, body, links, RTL rules, focus ring, reduced motion.
- `css/components.css` — type roles (`t-h1`/`t-h2`/`t-h3`, `eyebrow`, `label`, `lede`…), surfaces
  (`card`, `panel`, `fill`), tables, buttons, pills, fields and 4px-grid spacing utilities.
- `fonts/` — STC Light/Regular/Bold. Confirm the licence covers web embedding before publishing.
- `assets/` — logo artwork (raster screenshots from the brand guideline; swap for vector exports).

Verified pixel-identical to the original design at 1280, 820 and 390px widths.
