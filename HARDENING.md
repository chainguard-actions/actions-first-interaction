<!-- markdownlint-disable -->

# Hardening Report: actions--first-interaction/v2.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **actions--first-interaction/v2.0.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All workflow files use mutable tag, version, or branch references instead of pinned 40-character SHA digests, making the action vulnerable to supply-chain attacks if the referenced action is compromised or its tag is moved.

Failing references:
- check-dist.yml: actions/checkout@v4, actions/setup-node@v4, actions/upload-artifact@v4
- codeql-analysis.yml: actions/checkout@v4, github/codeql-action/init@v3, github/codeql-action/autobuild@v3, github/codeql-action/analyze@v3
- continuous-integration.yml: actions/checkout@v4, actions/setup-node@v4
- first-interaction.yml: actions/first-interaction@main (branch ref — especially risky)
- licensed.yml: actions/checkout@v4, actions/setup-node@v4, ruby/setup-ruby@v1, licensee/setup-licensed@v1.3.2
- linter.yml: actions/checkout@v4, actions/setup-node@v4, super-linter/super-linter/slim@v7
- release.yml: actions/checkout@v4, issue-ops/semver@v2, issue-ops/releaser@v2

Locations:

- `.github/workflows/check-dist.yml:29`
- `.github/workflows/check-dist.yml:35`
- `.github/workflows/check-dist.yml:60`
- `.github/workflows/codeql-analysis.yml:24`
- `.github/workflows/codeql-analysis.yml:29`
- `.github/workflows/codeql-analysis.yml:35`
- `.github/workflows/codeql-analysis.yml:39`
- `.github/workflows/continuous-integration.yml:18`
- `.github/workflows/continuous-integration.yml:24`
- `.github/workflows/first-interaction.yml:19`
- `.github/workflows/licensed.yml:25`
- `.github/workflows/licensed.yml:31`
- `.github/workflows/licensed.yml:39`
- `.github/workflows/licensed.yml:44`
- `.github/workflows/linter.yml:18`
- `.github/workflows/linter.yml:24`
- `.github/workflows/linter.yml:34`
- `.github/workflows/release.yml:14`
- `.github/workflows/release.yml:20`
- `.github/workflows/release.yml:27`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 20 unpinned action references across 7 workflow files:
- check-dist.yml: actions/checkout@v4 → @11d5960a, actions/setup-node@v4 → @49933ea5, actions/upload-artifact@v4 → @ea165f8d
- codeql-analysis.yml: actions/checkout@v4 → @11d5960a, github/codeql-action/init@v3 → @e60ea984, github/codeql-action/autobuild@v3 → @e60ea984, github/codeql-action/analyze@v3 → @e60ea984
- continuous-integration.yml: actions/checkout@v4 → @11d5960a, actions/setup-node@v4 → @49933ea5
- first-interaction.yml: actions/first-interaction@main → @a1db7729 (branch ref, especially risky)
- licensed.yml: actions/checkout@v4 → @11d5960a, actions/setup-node@v4 → @49933ea5, ruby/setup-ruby@v1 → @95ef2b04, licensee/setup-licensed@v1.3.2 → @0d52e575
- linter.yml: actions/checkout@v4 → @11d5960a, actions/setup-node@v4 → @49933ea5, super-linter/super-linter/slim@v7 → @12150456
- release.yml: actions/checkout@v4 → @11d5960a, issue-ops/semver@v2 → @5b8bb084, issue-ops/releaser@v2 → @e6768024
All original tags preserved as inline comments for readability.

