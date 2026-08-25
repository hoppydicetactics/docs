# Society documents

Automated PDF generation for Hoppy Dice Tactics statutes.

## Overview

This repository generates PDF versions of the society statutes (`statutes.md`) and publishes them as GitHub Releases whenever approved changes are merged to `main`.

## Workflow

**Name:** Render statutes and release

### Automatic trigger

- Runs when a pull request merging changes to `statutes.md` or `.github/workflows/render-statutes.yaml` is closed and merged into `main`
- Only runs if the PR was actually merged (not just closed)

### Manual trigger

- Go to **Actions** tab → select "Render statutes and release" → click **Run workflow**
- Optionally enable "Create a new release?" (disabled by default for testing)

## Requirements

| Item | Location | Description |
|------|----------|-------------|
| **Statutes document** | `statutes.md` | Markdown file with statutes. The last line must contain a date in format `dd.mm.yyyy` (e.g., `15.07.2026`) |
| **Logo** | `assets/logo.png` | Company/society logo for the PDF header (right-aligned, 1cm height) |

## Output

| Artifact | Location | Contents |
|----------|----------|----------|
| **PDF file** | GitHub Release | `Hoppy Dice Tactics Statuten dd.mm.yyyy.pdf` |
| **Release** | **Releases** tab | Tagged with render timestamp (e.g., `20260729-143052`), titled `Statuten dd.mm.yyyy` |
| **Temporary artifact** | Actions → Workflow run | PDF retained for 7 days |

## Maintaining the Workflow

Updates to the workflow actions are managed automatically via [Dependabot](https://github.com/settings/dependabot). Review and merge Dependabot PRs periodically to stay current.
