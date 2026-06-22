# SSO Static Reports Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Configure the repository as a minimal Azure Static Web Apps static report host protected by corporate SSO.

**Architecture:** The site serves committed HTML files from `reports/`. Azure Static Web Apps routing requires the `authenticated` role for every route. There is no frontend app, backend API, database, dashboard, or report-management UI.

**Tech Stack:** Azure Static Web Apps static hosting, plain HTML report files, JSON configuration.

## Global Constraints

- Keep changes minimal and focused.
- Do not introduce a package manager, frontend framework, backend, CI, or dependency tree.
- Store reports as committed `.html` files under `reports/`.
- Protect all routes with Azure Static Web Apps authentication.
- Do not create test or temporary reports.

---

### Task 1: Static Reports Hosting Structure

**Files:**
- Create: `reports/.gitkeep`
- Create: `staticwebapp.config.json`
- Modify: `README.md`

**Interfaces:**
- Consumes: none.
- Produces: a static report folder and Azure SWA auth configuration.

- [ ] **Step 1: Create the reports folder placeholder**

Create `reports/.gitkeep` as an empty file so the empty report directory is committed without adding sample reports.

- [ ] **Step 2: Add Azure Static Web Apps auth routing**

Create `staticwebapp.config.json` with this content:

```json
{
  "routes": [
    {
      "route": "/*",
      "allowedRoles": ["authenticated"]
    }
  ],
  "responseOverrides": {
    "401": {
      "redirect": "/.auth/login/aad",
      "statusCode": 302
    }
  }
}
```

- [ ] **Step 3: Update README operations**

Replace `README.md` with instructions describing the purpose, the `reports/` folder, direct URL sharing, deletion, and Azure SWA SSO behavior.

- [ ] **Step 4: Validate JSON syntax**

Run: `node -e "JSON.parse(require('fs').readFileSync('staticwebapp.config.json','utf8')); console.log('staticwebapp.config.json is valid JSON')"`

Expected: `staticwebapp.config.json is valid JSON`

- [ ] **Step 5: Inspect git status**

Run: `git status --short`

Expected: changed files are limited to `README.md`, `staticwebapp.config.json`, `reports/.gitkeep`, and the superpowers docs if present.
