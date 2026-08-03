# Claims: core-concepts.mdx

- **[CLAIM-CC-001]** ToggleMesh hierarchy follows Organization -> Project -> Environment -> Feature Flags.
- **[CLAIM-CC-002]** Feature Flags belong to a Project, but their targeting state and values are managed independently per Environment.
- **[CLAIM-CC-003]** Server API Keys are bound to a specific Environment.
- **[CLAIM-CC-004]** All flags in ToggleMesh are Multivariate by design (supporting Boolean, String, and JSON variations).
- **[CLAIM-CC-005]** Rule engine processes rules top-to-bottom; the first matching rule dictates the variation served.
- **[CLAIM-CC-006]** Rollout buckets use MurmurHash3 algorithm on `Identity + FlagKey` for deterministic hashing.
