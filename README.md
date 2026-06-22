# Pull Report Hub

Static HTML report hosting for Pull&Bear ecommerce reports.

## Purpose

This repository stores report HTML files that are published through Azure Static Web Apps and protected by corporate SSO. There is no dashboard, import form, backend API, or database in this iteration.

## Structure

- `reports/`: committed HTML report files.
- `staticwebapp.config.json`: Azure Static Web Apps auth routing. Every route requires an authenticated user.

## Add A Report

1. Copy the report HTML into `reports/`.
2. Use a stable, URL-safe filename, for example `reports/weekly-sales-2026-06-22.html`.
3. Commit and push the change.
4. Share the deployed URL: `https://<azure-static-web-app-host>/reports/<filename>.html`.

## Delete A Report

1. Remove the HTML file from `reports/`.
2. Commit and push the change.

## Access

Azure Static Web Apps redirects unauthenticated users to the configured corporate SSO login flow. After login, users can open direct report URLs.
