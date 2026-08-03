# Claims: flag-management.mdx

- **[CLAIM-FM-001]** All feature flags in ToggleMesh are Multivariate by default.
- **[CLAIM-FM-002]** Flag Types include Boolean, String, and JSON.
- **[CLAIM-FM-003]** Variations define potential return values for a flag.
- **[CLAIM-FM-004]** Approvals are configured at Environment level.
- **[CLAIM-FM-005]** Setting **Require Approvals** enables approval governance for flag changes in that environment.
- **[CLAIM-FM-006]** Environment configuration includes **Required Approvals Count**.
- **[CLAIM-FM-007]** Changes requiring approval enter status `PendingReview`.
- **[CLAIM-FM-008]** Pending changes generate a JSON diff of the flag state.
- **[CLAIM-FM-009]** Merged approved changes are broadcasted in real-time via SSE.
- **[CLAIM-FM-010]** Scheduled Rollouts specify an `ExecuteAt` timestamp.
- **[CLAIM-FM-011]** Scheduled changes enter state `Scheduled`.
- **[CLAIM-FM-012]** Approvals and Scheduled Rollouts can be combined (e.g. approved on Friday, executed on Sunday).
