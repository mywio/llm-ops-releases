# llmops releases

This repository distributes signed llmops deployment bundles. The application
source repository, its Git history, internal release notes and release PRs remain
private. Public releases contain the compiled executable and installer payload,
not a copy of the private application checkout.

Download a published stable version from [Releases](https://github.com/mywio/llm-ops-releases/releases).
Each release has five assets:

- Linux amd64 and arm64 deployment archives;
- `release-manifest.json` with the exact version, source identity, architecture
  hashes/sizes and compatibility information;
- `release-manifest.sig`, an Ed25519 signature over the exact manifest bytes;
- `SHA256SUMS`, a convenience checksum file.

Authenticate the signature and selected bundle using an independently trusted
llmops verifier and independently provisioned verification key before extracting
or running the installer. The checksum file alone is not authentication.
Keys in this repository are references for administrator review; downloading a
key does not establish trust or authorize an unattended key change.

Current verification-key ID:
`a734b6ea95104b6a020114e5c75422104760ad623a1ad35b56da6a7c49e2ade4`.

Public tags refer to this distribution repository's metadata. The signed
manifest's `commit` identifies the private source used to build the executable;
it does not refer to the public metadata commit. GitHub's generated source-code
archives contain only this repository's public metadata, not the application.

Updates are administrator opt-in and verify the pinned signing identity. New
builds fetch published stable releases here without a server GitHub credential.
Existing builds which still point at the private source repository first need
a trusted manual upgrade to a build using this public distribution endpoint.
