# GitHub Pages Static Reports Design

## Goal

Publish manually added HTML reports through GitHub Pages, with no dashboard, backend, import form, database, report-management UI, or access control.

## Architecture

The repository will be deployed through GitHub Pages from the `main` branch and repository root. Report URLs are public and can be shared directly.

Reports are plain static `.html` files stored in the repository under `reports/`. Sharing a report means sharing its GitHub Pages URL directly.

## Structure

- `reports/`: committed HTML report files.
- `README.md`: manual operating instructions for adding, deleting, and sharing reports.

## Access Model

GitHub Pages access is public. Anyone with a report URL can open the HTML file.

## Operations

To add a report, copy its HTML file into `reports/`, commit, and push. To delete a report, remove the HTML file, commit, and push. The URL is derived from `https://zalolv.github.io/pull-report-hub/reports/<filename>.html`.

## Non-Goals

- No dashboard or index page.
- No logo or custom visual design.
- No import form.
- No API or server-side code.
- No JSON database.
- No ratings, feedback, or deletion UI.
