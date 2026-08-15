<!-- markdownlint-disable -->

# Hardening Report: actions--first-interaction/v3.1.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **actions--first-interaction/v3.1.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All workflow files use mutable tag, branch, or version refs instead of full 40-character SHA commit hashes, making the action vulnerable to supply-chain attacks if a referenced action is compromised or a tag is moved.

check-dist.yml: actions/checkout@v5, actions/setup-node@v5, actions/upload-artifact@v4
codeql-analysis.yml: actions/checkout@v5, github/codeql-action/init@v3, github/codeql-action/autobuild@v3, github/codeql-action/analyze@v3
continuous-integration.yml: actions/checkout@v5, actions/setup-node@v5
first-interaction.yml: actions/first-interaction@main
licensed.yml: actions/checkout@v5, actions/setup-node@v5, ruby/setup-ruby@v1, licensee/setup-licensed@v1.3.2
linter.yml: actions/checkout@v5, actions/setup-node@v5, super-linter/super-linter/slim@v8
release.yml: actions/checkout@v5, issue-ops/semver@v2, issue-ops/releaser@v2

Locations:

- `.github/workflows/check-dist.yml:28`
- `.github/workflows/check-dist.yml:34`
- `.github/workflows/check-dist.yml:64`
- `.github/workflows/codeql-analysis.yml:27`
- `.github/workflows/codeql-analysis.yml:33`
- `.github/workflows/codeql-analysis.yml:38`
- `.github/workflows/codeql-analysis.yml:43`
- `.github/workflows/continuous-integration.yml:18`
- `.github/workflows/continuous-integration.yml:24`
- `.github/workflows/first-interaction.yml:20`
- `.github/workflows/licensed.yml:26`
- `.github/workflows/licensed.yml:32`
- `.github/workflows/licensed.yml:38`
- `.github/workflows/licensed.yml:44`
- `.github/workflows/linter.yml:22`
- `.github/workflows/linter.yml:28`
- `.github/workflows/linter.yml:37`
- `.github/workflows/release.yml:16`
- `.github/workflows/release.yml:22`
- `.github/workflows/release.yml:28`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 20 unpinned action references across 7 workflow files to full SHA commit hashes:
- check-dist.yml: actions/checkout@v5 → fbc6f39, actions/setup-node@v5 → a0853c2, actions/upload-artifact@v4 → ea165f8
- codeql-analysis.yml: actions/checkout@v5 → fbc6f39, github/codeql-action/init@v3 → 4187e74, github/codeql-action/autobuild@v3 → 4187e74, github/codeql-action/analyze@v3 → 4187e74
- continuous-integration.yml: actions/checkout@v5 → fbc6f39, actions/setup-node@v5 → a0853c2
- first-interaction.yml: actions/first-interaction@main → a1db772
- licensed.yml: actions/checkout@v5 → fbc6f39, actions/setup-node@v5 → a0853c2, ruby/setup-ruby@v1 → 95ef2b0, licensee/setup-licensed@v1.3.2 → 0d52e57
- linter.yml: actions/checkout@v5 → fbc6f39, actions/setup-node@v5 → a0853c2, super-linter/super-linter/slim@v8 → 4ce2083
- release.yml: actions/checkout@v5 → fbc6f39, issue-ops/semver@v2 → 5b8bb08, issue-ops/releaser@v2 → e676802
All original tags/branches preserved as inline comments.

