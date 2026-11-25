# bridge-artifacts

Public release artifacts for the bridge ACP adapters.

Binaries/bundles here are built from source in the (private) `bridge` repo.
Each release is a single adapter artifact, downloadable without auth so the
Colab runtime can fetch it via the colab-lab artifact manifest
(`harness/artifacts-colab.json`).

## Artifacts

| Release | Contents | Built from |
| --- | --- | --- |
| `pi-acp-pkg-v0.0.35-mcp1` | `pi-acp-pkg.mjs` — single-file ESM bundle of the MCP-patched pi-acp adapter (npm `pi-acp@0.0.35`) | `bridge/scripts/build-pi-acp-pkg.sh` |

## Verifying a download

```sh
curl -fsSLO https://github.com/stickland1101/bridge-artifacts/releases/download/<tag>/pi-acp-pkg.mjs
sha256sum pi-acp-pkg.mjs   # compare with the sha256 in artifacts-colab.json
node --check pi-acp-pkg.mjs
```
