# Greenlight releases

This repository is the release feed for [Greenlight](https://greenlightbyshift.com). It holds
**releases only** — tags, release notes, and downloadable assets. There is no source code here.

Every release is publicly downloadable. Installing or updating Greenlight never requires a
credential from Shift to discover, download, or verify a release.

## What each release contains

| Asset | What it is |
| --- | --- |
| `release-manifest.json` | Describes the release: the component image digests, the packaged chart, and one installer archive per cloud, each with its SHA-256. Start here — every other asset is named and digest-pinned by this file. |
| `greenlight-azure.zip` | Azure installer: the deployment template, the install script, and the control-plane chart. |
| `greenlight-gcp.zip` | Google Cloud installer. |
| `greenlight-aws.zip` | AWS installer. |
| `greenlight-<version>.tgz` | The packaged control-plane Helm chart. |

Container images are pulled anonymously from Docker Hub at the digests the manifest records.

## Downloading

The newest release resolves at a stable URL, so a link never needs updating:

```
https://github.com/ShiftEngineering/greenlight-releases/releases/latest/download/greenlight-azure.zip
https://github.com/ShiftEngineering/greenlight-releases/releases/latest/download/release-manifest.json
```

Verify an archive against the digest its manifest records before running it:

```
shasum -a 256 greenlight-azure.zip
```

Releases marked **pre-release** are Shift's own internal validation builds. Production
installations track the latest full release, which `releases/latest` already resolves to.

## Documentation

Installation, upgrades, and administration: <https://greenlightbyshift.com/docs>
