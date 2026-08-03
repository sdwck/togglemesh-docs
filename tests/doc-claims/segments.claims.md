# Claims: segments.mdx

- **[CLAIM-SEG-001]** Segments are reusable targeting rule groups defining specific user cohorts.
- **[CLAIM-SEG-002]** Segments are created and managed at the Environment level.
- **[CLAIM-SEG-003]** Segment rules use the same `RuleEngine` interface as Feature Flags.
- **[CLAIM-SEG-004]** Feature Flags reference Segments via the `InSegment` operator.
- **[CLAIM-SEG-005]** Feature Flags reference Segments via the `NotInSegment` operator.
- **[CLAIM-SEG-006]** Updating a Segment automatically cascades updates to all Feature Flags referencing it.
- **[CLAIM-SEG-007]** Updated Segment definitions are pushed to SDKs via SSE stream in `<30ms`.
- **[CLAIM-SEG-008]** ToggleMesh SDKs sync Segments alongside Flags during initialization.
- **[CLAIM-SEG-009]** Evaluation of `InSegment` operator occurs locally in-memory inside the SDK with zero network latency.
