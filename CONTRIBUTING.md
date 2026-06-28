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
