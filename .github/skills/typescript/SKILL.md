---
name: typescript
description: Write, fix, or review clear and reliable TypeScript for front-end applications without unnecessary type complexity.
---

# TypeScript

Apply these instructions whenever a task introduces or changes typed application code, public contracts, external data, or compiler configuration.

## Principles

- Follow the repository's compiler settings and preserve strictness.
- Prefer inference for obvious local values and explicit types at public boundaries.
- Model domain concepts with precise names and the smallest useful shape.
- Use unions to represent finite states and make invalid states difficult to express.
- Narrow `unknown` data through validation before using it.
- Keep types close to the code they describe unless they are genuinely shared.
- Use readonly contracts when callers should not mutate a value.
- Make absence explicit instead of hiding it behind broad optional properties.

## Type Design

- Prefer interfaces for extensible object contracts and type aliases for unions, mapped types, and compositions.
- Use discriminated unions for state machines and mutually exclusive variants.
- Derive types from existing sources when this prevents duplicated contracts.
- Use generics only when they preserve a meaningful relationship between inputs and outputs.
- Exhaustively handle closed unions and make missing cases visible to the compiler.
- Use type guards or schema validation at runtime boundaries.

## Avoid

- `any`, broad type assertions, and non-null assertions used to silence an error.
- Casting external data directly to a trusted application type.
- Enums when a simple literal union provides a clearer contract.
- Deep generic abstractions for a single concrete use case.
- Duplicating a type already exported by the owning module or dependency.
- Weakening compiler options to accommodate one implementation.

## Verification

- Run the project's type checker independently of the development server.
- Test runtime validation separately from compile-time typing.
- Check that public types remain compatible unless a breaking change is intentional.
- Confirm all union variants and nullable paths are handled.
