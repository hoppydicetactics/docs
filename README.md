# Society documents

Automated PDF generation for Hoppy Dice Tactics statutes and other documents.

## Overview

This repository generates PDF versions of the society statutes (`statutes.md`) and other meeting minutes. Approved changes merged to `main` are published as GitHub Releases, while manual runs produce draft PDFs as workflow artifacts.

## Statutes rendering

**Name:** Render statutes and release

### Automatic trigger

- Runs when a pull request merging changes to `statutes.md` is closed and merged into `main`
- Only runs if the PR was actually merged (not just closed)
- Creates a **GitHub Release** with the rendered PDF

### Manual trigger

- Go to **Actions** tab → select "Render statutes and release" → click **Run workflow**
- Produces a **draft PDF** (marked as "Entwurf") uploaded as a workflow artifact
- No release is created

## Files

| Item | Location | Description |
|------|----------|-------------|
| **Statutes document** | `statutes.md` | Markdown file with statutes. The last line must contain a date in format `dd.mm.yyyy` (e.g., `15.07.2026`) |
| **Logo** | `assets/logo.png` | Society logo for the PDF header |
| **PDF template** | `templates/statutes.yaml` | Pandoc configuration |

## Output

| Trigger | Output | Details |
|---------|--------|---------|
| **PR merged** | GitHub Release | File: `Hoppy Dice Tactics Statuten dd.mm.yyyy.pdf` — Tag: render timestamp (e.g., `20260729-143052`) |
| **Manual run** | Workflow artifact | File: `Hoppy Dice Tactics Statuten Entwurf YYYYMMDD-HHMMSS.pdf` — Retained for 7 days |

### Header text

| Trigger | PDF header (left) |
|---------|-------------------|
| PR merged | `Statuten Hoppy Dice Tactics - YYYYMMDD-HHMMSS` |
| Manual run | `Statuten Hoppy Dice Tactics - Entwurf YYYYMMDD-HHMMSS` |

## Maintaining the Workflow

Updates to the workflow actions are managed automatically via [Dependabot](https://github.com/settings/dependabot).
