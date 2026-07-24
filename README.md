# CoreLink TypeScript SDK

Generated prerelease client for the CoreLink Public API. The package is not
published or production-supported until the linked public contract and runtime
PRs are merged and sandbox compatibility tests pass.

## Contract provenance

- Contract: `corelink-public-v1.yaml`, version `1.0.0-draft`
- Source branch: `agent/p3-1-contracts`
- Source commit: `701e693`
- Generator: OpenAPI Generator `7.12.0`, `typescript-fetch`

The public client exposes canonical CoreLink identifiers only. Connector
selection and integration-provider identifiers remain server-side concerns.

## Local verification

```sh
npm install
npm run test:generated
```

Regeneration is documented in [CODEGEN.md](CODEGEN.md). Do not edit files under
`src/` by hand; change the public contract and regenerate instead.

## Release gate

Before publishing, require a merged versioned contract, runtime compatibility
tests against the sandbox tenant, a clean generated diff, package build, and
release notes that identify the contract commit.
