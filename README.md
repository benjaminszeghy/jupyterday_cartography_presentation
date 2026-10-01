# JupyterDay Cartography Presentation

reveal.js deck written in Markdown.

- `index.html`: reveal.js setup (loaded from CDN)
- `slides.md`: slide content (`---` = new slide, `--` = vertical slide, `Note:` = speaker notes)
- `media/`: images, data, video used by the slides

## Run

The Markdown file is loaded via fetch, so serve over HTTP:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. Press `s` for speaker view, `?` for help.
