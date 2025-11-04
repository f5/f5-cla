[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/f5/f5-cla/badge)](https://securityscorecards.dev/viewer/?uri=github.com/f5/f5-cla)
[![Community Support](https://badgen.net/badge/support/community/cyan?icon=awesome)](/SUPPORT.md)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](/CODE_OF_CONDUCT.md)

# F5 Contributor License Agreement (CLA) Documentation & Workflow

This repository is intended to serve as the consolidated documentation and GitHub Actions workflow for automating the F5 Contributor License Agreement (CLA) process. The respective signatures from contributors towards F5 affiliated Open Source Software (OSS) projects are stored separately.

## Documentation

The F5 CLA agreement can be found in the [/docs/f5_cla.md](/docs/f5_cla.md) subdirectory.

## Sample GitHub Actions Workflow

You can find a fully functional CLA GitHub Action workflow in [`.github/workflows/f5_cla.yml`](/.github/workflows/f5_cla.yml). This workflow uses the [CLA Assistant GitHub Action](https://github.com/contributor-assistant/github-action) to write and read data to/from F5's data storage. We encourage you use this workflow in any F5 OSS project you maintain. (**Note:** You might need/want to edit both the `branch` and `allowlist` parameters in the workflow.)

### GitHub Actions Workflow Overview

Upon a pull request (PR) submission, the F5 CLA GitHub Action workflow is triggered and a signature check for the author is done against F5's data storage.

If a previous signature from the authors of the PR is not found within this F5's data storage, the [CLA Assistant GitHub Action](https://github.com/contributor-assistant/github-action) prompts the PR author to read the [F5 CLA](/docs/f5_cla.md), and agree to the [F5 CLA](/docs/f5_cla.md) terms by leaving a phrase with the comment: "I have hereby read the F5 CLA and agree to its terms".

Upon detection of the specified phrase by the author in a PR comment, the action is retriggered and the authors information is collected and committed to F5's data storage.

**Note:** The workflow automatically normalizes comments by trimming whitespace and removing trailing punctuation (`.`, `!`, `?`, `;`, `,`), so users can naturally add punctuation to the end of their CLA agreement statement without causing the approval to fail.

### Status Check Integrations

This action integrates directly with GitHub's Status Check feature. If the action determines that signatures are still required from the pull request's author(s), it will show a failing status and vice-versa.

![status-checks](/media/status-checks.png)

# License

[Apache License, Version 2.0](/LICENSE)

&copy; [F5, Inc.](https://www.f5.com/) 2025
