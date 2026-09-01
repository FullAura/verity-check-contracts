# @verity-check/contracts

Shared, framework-free TypeScript types for the Verity Check API. These mirror the request/response DTOs of `
-api` **without** any `@nestjs/swagger` / `class-validator` runtime dependencies, so the frontend can import them safely.

## Install (private git)

```jsonc
// frontend package.json
{
  "dependencies": {
    "@verity-check/contracts": "git+ssh://git@github.com/<org>/verity-check-contracts.git#v0.0.1"
  }
}
```

Pin to a tag (`#v0.0.1`) or commit SHA so upgrades are explicit. Bump the tag whenever the API contract changes.

## Usage

```ts
import type { ExampleReqest, ExampleResponse } from '@verity-check/contracts';
```

## Keeping in sync

These types are hand-mirrored from `verity-check-api`'s DTOs. When a DTO changes, update the matching type here and publish a new tag. The API's DTO classes should `implements` the corresponding interface from this package so the compiler catches drift.