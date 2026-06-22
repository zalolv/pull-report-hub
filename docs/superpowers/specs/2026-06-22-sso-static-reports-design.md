# SSO Static Reports Design

## Goal

Publish manually added HTML reports behind corporate SSO, with no dashboard, backend, import form, database, or report-management UI.

## Architecture

The repository will be deployed as an Azure Static Web Apps site. Azure Static Web Apps authentication will protect every route, so users must authenticate with the configured corporate SSO provider before accessing any report URL.

Reports are plain static `.html` files stored in the repository under `reports/`. Sharing a report means sharing its deployed URL directly.

## Structure

- `reports/`: committed HTML report files.
- `staticwebapp.config.json`: Azure Static Web Apps routing configuration that requires authentication for all routes.
- `README.md`: manual operating instructions for adding, deleting, and sharing reports.

## Access Model

All paths require the built-in `authenticated` role. Unauthenticated users are redirected to the Azure Static Web Apps login flow configured for corporate SSO.

## Operations

To add a report, copy its HTML file into `reports/`, commit, and push. To delete a report, remove the HTML file, commit, and push. The URL is derived from the deployed Azure Static Web Apps hostname plus `/reports/<filename>.html`.

## Non-Goals

- No dashboard or index page.
- No logo or custom visual design.
- No import form.
- No API or server-side code.
- No JSON database.
- No ratings, feedback, or deletion UI.
