# Pull Report Hub

Static HTML report hosting for Pull&Bear ecommerce reports through GitHub Pages.

## Purpose

This repository stores report HTML files that are published through GitHub Pages. The root `index.html` is a manually maintained dashboard that links to the available reports. There is no import form, backend API, database, or access control in this iteration.

## Structure

- `reports/`: committed HTML report files served directly by GitHub Pages.
- `index.html`: manually maintained dashboard with one card per available report.

## Add A Report

1. Copy the report HTML into `reports/`.
2. Use a stable, URL-safe filename, for example `reports/weekly-sales-2026-06-22.html`.
3. Add a matching card to `index.html` with the report title, summary, tags, and link.
4. Commit and push the change.
5. Share either the dashboard URL `https://zalolv.github.io/pull-report-hub/` or the direct report URL `https://zalolv.github.io/pull-report-hub/reports/<filename>.html`.

## Delete A Report

1. Remove the HTML file from `reports/`.
2. Remove its card from `index.html`.
3. Commit and push the change.

## Access

GitHub Pages is public for this repository. Anyone with a report URL can access the HTML file.

Current report URL:

- `https://zalolv.github.io/pull-report-hub/reports/yerem-ai-visual-report.html`
