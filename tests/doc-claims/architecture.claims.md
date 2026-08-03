# Claims: architecture.mdx

- **[CLAIM-ARC-001]** Core Stack consists of .NET 8 Web API, PostgreSQL 18, and Redis 7.
- **[CLAIM-ARC-002]** Enterprise Stack adds ClickHouse for columnar analytics and Apache Kafka for event streaming.
- **[CLAIM-ARC-003]** Initial SDK sync uses single REST call `SyncStateWithApiAsync` to fetch all flags and segments in one HTTP roundtrip.
- **[CLAIM-ARC-004]** Redis acts as Pub/Sub backplane for SSE broadcasting across multiple stateless API nodes.
- **[CLAIM-ARC-005]** Telemetry buffer in SDKs flushes metrics asynchronously to prevent I/O blocking on hot evaluation paths.
