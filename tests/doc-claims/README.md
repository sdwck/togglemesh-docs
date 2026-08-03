# ToggleMesh Documentation Fact Claims Suite

This directory contains atomic, machine-verifiable technical claims extracted from the ToggleMesh documentation (`content/docs/*.mdx`).

## Purpose

These `.claims.md` files serve as an automated or manual assertion suite for testing AI documentation accuracy. When core code, database schemas, or SDK interfaces change in `ToggleMesh`, running checks against these claims ensures that documentation never hallucinates or falls out of sync.

## Structure

Each file maps 1:1 to a documentation page in `content/docs/`:
- `content/docs/quickstart.mdx` -> `tests/doc-claims/quickstart.claims.md`
- `content/docs/database-partitioning.mdx` -> `tests/doc-claims/database-partitioning.claims.md`
- etc.

## Claim Format

Each claim is stated as an atomic invariant:
- `[CLAIM-ID]` Description of technical invariant (verifiable against source code / runtime).
