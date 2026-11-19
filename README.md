# sfptool-macos

Builds the macOS universal `.app` and `.dmg` for `sfp-tool`. Triggered from the Forgejo release pipeline (`build-app-macos` job), which downloads the artifact `macos-universal` and publishes it to S3.

## Setup

Workflow: `.github/workflows/build-macos.yml` (`workflow_dispatch`, inputs `forgejo_sha`, `version`). Must exist on the default branch (`master`).

Repository secrets:

- `TAURI_SIGNING_PRIVATE_KEY`, `TAURI_SIGNING_PRIVATE_KEY_PASSWORD`: updater signing key (same as Forgejo).

Forgejo side needs secrets `GH_TOKEN` (fine-grained PAT, Actions read+write on this repo) and `GH_REPO` (`owner/sfptool-macos`).
