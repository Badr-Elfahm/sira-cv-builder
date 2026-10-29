# Development verification guide

This is a manual verification checklist, not an automated test report.

## Run locally

Open `index.html` in a recent Edge or Chrome browser. No installation or build step is required. Use demonstration content when reporting bugs or sharing screenshots.

## Before publishing a change

- Switch between Arabic, French and English; inspect both interface labels and CV headings.
- In Arabic, check RTL alignment, mixed Arabic/Latin text and long names.
- Add, reorder and remove entries; check undo after a deletion.
- Change templates, accent colors and compact spacing; inspect one-page and multi-page CVs.
- Reload to check local saving, then export a JSON backup and restore it in a separate browser profile.
- Check photo upload and confirm that the preview and exported file preserve the intended layout.
- Export PDF and PNG; inspect page breaks, clipped content and right-to-left text.
- Use the browser print route when checking text-selectable PDF output; disable browser headers and footers.
- Navigate with a keyboard and inspect the layout at narrow mobile and desktop widths.
- Repeat offline after downloading the complete application.

Record browser/version, viewport, template, language, reproduction steps, expected behavior and actual behavior with each issue. Browser print and export results can differ.

## Architecture and tradeoffs

The standalone application uses browser APIs for local storage, image handling, downloads and printing. Keeping it browser-only supports offline use without an account or backend. Browser storage is tied to its browser and origin, so backups remain important.

Direct PDF export uses rasterized pages. That route preserves the visual layout but does not produce selectable text. Browser printing provides an alternative when text selection matters. Interface language changes do not translate user-entered content.

[Back to the project](README.md)
