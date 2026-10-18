<!--
SPDX-FileCopyrightText: HyperVOB contributors
SPDX-License-Identifier: CC-BY-4.0
-->
# HyperVOB/.github

The HyperVOB organisation's public profile (`profile/README.md`). Later also the default
community health files for the organisation's repositories.

`main`'s ruleset (`.github/rulesets/main.json`, applied by the HyperVOB repository's
`scripts/harden-github.sh`) asks for signed commits and a linear history and forbids
force-pushes and deletion.

Checks, as in the HyperVOB repository: `pre-commit install` once per clone runs
`.pre-commit-config.yaml`'s hooks before each commit and push (REUSE, spelling, the SVGs
well-formed, secrets, the workflows with zizmor and actionlint, which needs Docker
running when a workflow changes, and Conventional Commits). CI
(`.github/workflows/checks.yml`) runs the same hooks, gitleaks aside (GitHub's secret
scanning covers a public repository), and lychee over the READMEs' links
(`.github/lychee.toml`), on pushes, pull requests and weekly. They report; the ruleset
requires none of them. `.github/ci-tools.*` and `.github/uv.toml` pin the tools CI
installs pre-commit with and the hooks' 7-day cooldown, `.github/dependabot.yml` updates
the hook revs and Actions monthly, and `.gitattributes` keeps every checkout's line
endings LF.

The text and the HyperVOB marks are licensed [CC BY 4.0](LICENSES/CC-BY-4.0.txt); credit
"HyperVOB contributors". The marks' source and guidelines live in the HyperVOB
repository's `brand/` folder. The files follow [REUSE](https://reuse.software).
