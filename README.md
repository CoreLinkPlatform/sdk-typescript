# CoreLink TypeScript SDK

[![Maturity: Prerelease Alpha](https://img.shields.io/badge/maturity-prerelease%20alpha-orange)](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)
[![Generated conformance](https://github.com/CoreLinkPlatform/sdk-typescript/actions/workflows/generated-conformance.yml/badge.svg?branch=main)](https://github.com/CoreLinkPlatform/sdk-typescript/actions/workflows/generated-conformance.yml)
[![Package: 0.1.0-draft](https://img.shields.io/badge/package-0.1.0--draft-orange)](package.json)
[![Contract: 1.0.0-draft](https://img.shields.io/badge/contract-1.0.0--draft-blue)](https://github.com/CoreLinkPlatform/api-contracts)
[![TypeScript](https://img.shields.io/badge/TypeScript-SDK-blue)](https://www.typescriptlang.org/)

> **Maturity: Prerelease Alpha**  
> Package metadata: `@corelink/sdk` `0.1.0-draft`  
> Public contract: `corelink-public-v1.yaml` `1.0.0-draft`

Generated TypeScript client for the CoreLink Public API. The client exists and builds from source, but it is not yet a production-supported npm release. Supported publication remains gated by tagged contract provenance and sandbox/runtime conformance.

## What is currently covered

The generated surface follows the current reviewed public contract, whose primary public slice is Device + Command. Broader telemetry/location/partner/event surfaces must not be assumed supported until their contracts and conformance gates are accepted.

## Build from source

```bash
npm ci
npm run build
```

Validate generated output with:

```bash
npm run test:generated
```

This is a source/prerelease workflow, not an instruction to install a published Stable package.

## Authentication and tenant context

The current public API uses Bearer JWT authentication and explicit tenant-scoped resource paths. Applications must obtain credentials through their approved CoreLink environment/onboarding flow; the draft public contract does not define a self-service token issuer.

Keep tokens out of browser storage where a server-side session/BFF can be used, and never retry `403` by changing tenant IDs.

## Devices and commands

Use canonical CoreLink resource identifiers such as `corelink_device_id`; provider IDs are implementation details.

Command creation follows the contract's idempotency semantics. Reuse the same `Idempotency-Key` only when retrying the same logical command. An accepted command response is asynchronous and does not prove physical-device execution succeeded.

The SDK is generated, so exact generated method/type names can change while this package remains prerelease. Use the generated source/types for the exact API of the pinned revision rather than relying on undocumented hand-written wrappers.

## Errors and retries

Follow the OpenAPI problem/error definitions. Do not blindly retry validation/auth/authorization errors. Preserve correlation/request identifiers for diagnosis and avoid logging tokens or sensitive payload data.

## Contract provenance

Current generation provenance is recorded in `.corelink-contract.json` and `CODEGEN.md`. Existing prerelease metadata references a development source revision; supported releases must move to immutable/tagged contract provenance.

## Regeneration

Do not hand-edit generated files under `src/`. Change the normative contract in [`CoreLinkPlatform/api-contracts`](https://github.com/CoreLinkPlatform/api-contracts), then regenerate according to [CODEGEN.md](CODEGEN.md) and review the generated diff.

## Release gates

Before a supported package release:

- contract revision/tag is immutable and version-identifiable;
- generation is reproducible;
- authentication/tenant/error/idempotency behavior matches the contract;
- compatibility passes against an accepted mock/sandbox/runtime revision;
- package provenance/signing/release policy is satisfied;
- docs/release notes identify exact compatibility and maturity.

Backlog: [TS-01](https://github.com/CoreLinkPlatform/sdk-typescript/issues/3), [TS-02](https://github.com/CoreLinkPlatform/sdk-typescript/issues/4), [TS-03](https://github.com/CoreLinkPlatform/sdk-typescript/issues/5).

## Documentation

- [CoreLink developer docs](https://github.com/CoreLinkPlatform/developer-docs)
- [API contracts](https://github.com/CoreLinkPlatform/api-contracts)
- [Repository maturity](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)
