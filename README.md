# sfptool-macos

Builds the macOS universal `.app` and `.dmg` for `sfp-tool`. Triggered from the GitLab release pipeline (`build-app-macos` job), which downloads the artifact `macos-universal` and publishes it to S3.

## Setup

Workflow: `.github/workflows/build-macos.yml` (`workflow_dispatch`, inputs `gitlab_sha`, `version`). Must exist on the default branch (`master`).

Repository secrets:

- `GITLAB_TOKEN`: GitLab project access token, `read_repository` scope, on `jonasled/sfp-tool`.
- `TAURI_SIGNING_PRIVATE_KEY`, `TAURI_SIGNING_PRIVATE_KEY_PASSWORD`: updater signing key (same as GitLab).

GitLab side needs CI variables `GITHUB_TOKEN` (fine-grained PAT, Actions read+write on this repo) and `GITHUB_REPO` (`owner/sfptool-macos`).
