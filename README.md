# CoreLink TypeScript SDK

The future official TypeScript SDK for Node.js, browser, React and Next.js
applications using CoreLink public APIs.

## Current status

This repository is a scaffold: no package manifest, source code or published
artifact exists yet. It must not be represented as installable or production
ready.

## Planned capabilities

- Typed public API client generated or validated against `api-contracts`.
- Configurable OAuth token acquisition without embedding credentials in client
  bundles.
- Tenant-aware device, provisioning, command, telemetry and event workflows.
- Typed pagination, problem responses, retry guidance and webhook helpers.
- Browser-safe and server-side entry points with clear runtime support.

## Release requirements

Publish a semver version only after the matching public OpenAPI contract is
reviewed and non-empty, integration behavior is tested against the platform,
and the README includes installation, authentication, compatibility and
migration guidance.
