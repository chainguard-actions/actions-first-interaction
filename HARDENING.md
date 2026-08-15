<!-- markdownlint-disable -->

# Hardening Report: actions--first-interaction/v3.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **actions--first-interaction/v3.0.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All `uses:` references across workflow files are pinned to mutable tags or branch names rather than immutable 40-character SHA commit hashes. This exposes the action to supply-chain attacks where a compromised upstream action tag could silently execute malicious code. Failing references:

**check-dist.yml**: `actions/checkout@v4`, `actions/setup-node@v4`, `actions/upload-artifact@v4`
**codeql-analysis.yml**: `actions/checkout@v4`, `github/codeql-action/init@v3`, `github/codeql-action/autobuild@v3`, `github/codeql-action/analyze@v3`
**continuous-integration.yml**: `actions/checkout@v4`, `actions/setup-node@v4`
**first-interaction.yml**: `actions/first-interaction@main` (branch ref — especially dangerous)
**licensed.yml**: `actions/checkout@v4`, `actions/setup-node@v4`, `ruby/setup-ruby@v1`, `licensee/setup-licensed@v1.3.2`
**linter.yml**: `actions/checkout@v4`, `actions/setup-node@v4`, `super-linter/super-linter/slim@v8`
**release.yml**: `actions/checkout@v4`, `issue-ops/semver@v2`, `issue-ops/releaser@v2`

All should be replaced with full SHA pins, e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`.

Locations:

- `.github/workflows/check-dist.yml:29`
- `.github/workflows/check-dist.yml:35`
- `.github/workflows/check-dist.yml:62`
- `.github/workflows/codeql-analysis.yml:27`
- `.github/workflows/codeql-analysis.yml:32`
- `.github/workflows/codeql-analysis.yml:38`
- `.github/workflows/codeql-analysis.yml:43`
- `.github/workflows/continuous-integration.yml:18`
- `.github/workflows/continuous-integration.yml:24`
- `.github/workflows/first-interaction.yml:19`
- `.github/workflows/licensed.yml:24`
- `.github/workflows/licensed.yml:30`
- `.github/workflows/licensed.yml:38`
- `.github/workflows/licensed.yml:44`
- `.github/workflows/linter.yml:19`
- `.github/workflows/linter.yml:25`
- `.github/workflows/linter.yml:34`
- `.github/workflows/release.yml:14`
- `.github/workflows/release.yml:20`
- `.github/workflows/release.yml:27`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 20 unpinned `uses:` references across 7 workflow files to their full 40-character SHA commit hashes:

- **check-dist.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020, actions/upload-artifact@v4 → @ea165f8d65b6e75b540449e92b4886f43607fa02
- **codeql-analysis.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, github/codeql-action/init@v3 → @08d09a53f0f5d694f253bd25732e4429c9e9337f, github/codeql-action/autobuild@v3 → @08d09a53f0f5d694f253bd25732e4429c9e9337f, github/codeql-action/analyze@v3 → @08d09a53f0f5d694f253bd25732e4429c9e9337f
- **continuous-integration.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020
- **first-interaction.yml**: actions/first-interaction@main (branch ref) → @a1db7729b356323c7988c20ed6f0d33fe31297be
- **licensed.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020, ruby/setup-ruby@v1 → @a30dfa457ad68707b8b910ac3a244714b61c0626, licensee/setup-licensed@v1.3.2 → @0d52e575b3258417672be0dff2f115d7db8771d8
- **linter.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020, super-linter/super-linter/slim@v8 → @4ce20838b8ab83717e78138c5b3a1407148e0918
- **release.yml**: actions/checkout@v4 → @11d5960a326750d5838078e36cf38b85af677262, issue-ops/semver@v2 → @5b8bb084b6834d03ddb5c7c96c683a588a2072ca, issue-ops/releaser@v2 → @e6768024642153d17c157995e2684a3ebcae14e7

All original tag names preserved as inline comments for readability.

