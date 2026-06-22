# GitHub Pages Static Reports Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Configure the repository as a minimal GitHub Pages static report host with public direct report URLs.

**Architecture:** The site serves committed HTML files from `reports/` using GitHub Pages from `main` and the repository root. There is no frontend app, backend API, database, dashboard, access control, or report-management UI.

**Tech Stack:** GitHub Pages static hosting, plain HTML report files.

## Global Constraints

- Keep changes minimal and focused.
- Do not introduce a package manager, frontend framework, backend, CI, or dependency tree.
- Store reports as committed `.html` files under `reports/`.
- Publish reports through GitHub Pages from `main` and `/`.
- GitHub Pages access is public; anyone with a report URL can access the HTML.
- Do not create test or temporary reports.

---

### Task 1: GitHub Pages Static Reports Hosting

**Files:**
- Create: `reports/.gitkeep`
- Delete: `staticwebapp.config.json`
- Modify: `README.md`

**Interfaces:**
- Consumes: none.
- Produces: a static report folder and GitHub Pages publishing instructions.

- [ ] **Step 1: Create the reports folder placeholder**

Create `reports/.gitkeep` as an empty file so the empty report directory is committed without adding sample reports.

- [ ] **Step 2: Remove Azure Static Web Apps auth routing**

Delete `staticwebapp.config.json` because GitHub Pages does not use Azure Static Web Apps authentication config.

- [ ] **Step 3: Update README operations**

Replace `README.md` with instructions describing the purpose, the `reports/` folder, direct GitHub Pages URL sharing, deletion, and public access behavior.

- [ ] **Step 4: Enable GitHub Pages**

Run: `env -u GITHUB_TOKEN gh api repos/zalolv/pull-report-hub/pages -X POST -f source.branch=main -f source.path=/`

Expected: GitHub Pages is configured from branch `main` and path `/`.

- [ ] **Step 5: Inspect git status**

Run: `git status --short`

Expected: changed files are limited to `README.md`, `staticwebapp.config.json` deletion, and the superpowers docs if present.
