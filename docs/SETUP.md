# Repository Setup

This repository powers the special GitHub Profile for **Mohammad Huzaifa** (`GuruMachanica`). 
It uses GitHub Actions to automate metrics generation and contribution snake generation.

## 🔑 Secrets Required

To ensure all GitHub Actions run successfully, you need to configure the following repository secrets:

### 1. `METRICS_TOKEN`

Used by the **GitHub Metrics** workflow to fetch detailed analytics about your GitHub account.

**How to generate and add:**
1. Go to your GitHub [Personal Access Tokens (classic)](https://github.com/settings/tokens).
2. Click **Generate new token (classic)**.
3. Note: Name it something like `Profile Metrics Token`.
4. Select the following scopes:
   - `public_repo`
   - `read:org`
   - `read:user`
   - `read:packages`
5. Click **Generate token** and copy the value.
6. Go to this repository's **Settings** > **Secrets and variables** > **Actions**.
7. Click **New repository secret**.
8. Name: `METRICS_TOKEN`
9. Value: Paste the token you generated.
10. Save.

### 2. `GITHUB_TOKEN`
This is automatically provided by GitHub Actions for the **Generate Snake** workflow to push to the `output` branch. No manual setup is needed, but ensure your repository allows workflows to have **Read and write permissions**.
- Go to **Settings** > **Actions** > **General**.
- Under **Workflow permissions**, select **Read and write permissions**.

---

## 🚀 Workflows Explained

- **GitHub Metrics (`metrics.yml`)**: Runs every 12 hours. Fetches comprehensive stats (languages, habits, activity, lines of code) using `lowlighter/metrics` and commits them.
- **Generate Snake (`snake.yml`)**: Runs every 12 hours. Generates an SVG animation of your contribution graph and pushes it to an isolated `output` branch to keep the main branch clean.

---

## 🎨 Design System

- **Assets:** Custom SVGs (hero banner, project cards, dividers) are located in the `assets/` directory. 
- **Modifying SVGs:** The SVGs are heavily optimized. If you need to change text (e.g., updating a project description), open the SVG in a code editor and modify the text within the `<text>` nodes.
