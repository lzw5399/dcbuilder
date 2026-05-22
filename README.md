# dcbuilder

Public GitHub Actions runner for desktop package builds.

The source repository uploads a short-lived, minimal source bundle to COS and
dispatches this repository. Each matrix job downloads only its own source bundle,
verifies it, extracts it locally, deletes the COS source object, and then builds
the installer for that platform.

Required secrets or variables:

- `TENCENT_COS_SECRET_ID`
- `TENCENT_COS_SECRET_KEY`
- `TENCENT_COS_SECURITY_TOKEN` optional
- `TENCENT_COS_BUCKET`
- `TENCENT_COS_REGION`
- `DESKTOP_RELEASE_RELAY_WEBHOOK_URL`
- `DESKTOP_RELEASE_RELAY_TOKEN`
- `APP_SERVER_URL_TEST`
- `APP_SERVER_URL_PROD`

This repository should not enable pull request triggers for package builds.
