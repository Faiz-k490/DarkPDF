# Contributing to DarkPDF

Thanks for your interest! DarkPDF is intentionally tiny — a single `index.html` plus vendored
libraries — so contributing is low-friction.

## Development

There's no build step. Edit `index.html` and reload in your browser.

- **Safari / Firefox:** double-click `index.html`.
- **Chrome:** serve locally (`python3 -m http.server 8000`) because Chrome blocks the local
  pdf.js worker over `file://`.

Please test changes against a few real PDFs — at minimum a text-heavy document and one with
images/figures — before opening a PR.

For export geometry, serve the repository locally and open
`http://localhost:8000/tests/export-geometry.html`. It generates text-heavy and image PDFs,
including a rotated page, and checks the actual exports at every quality setting. The
result should show `"ok": true` for all nine page checks. Raster resolution must change
with quality while PDF page dimensions stay fixed. The check uses the vendored libraries
and does not contact external services.

## Guidelines

- Keep it **dependency-free at runtime**. The whole point is offline, no-tracking, no-build.
- Don't fetch anything from the network in the app code. Libraries stay vendored in `vendor/`.
- Match the existing vanilla-JS style; no frameworks.
- If you bump a vendored library version, update `THIRD_PARTY_LICENSES.md`.

## Reporting bugs

Open an issue with the browser/OS, the kind of PDF, and what went wrong. A small sample PDF that
reproduces the problem is hugely helpful.

## License

By contributing, you agree your contributions are licensed under the [MIT License](LICENSE).
