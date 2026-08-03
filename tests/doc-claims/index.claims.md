# Claims: index.mdx

- **[CLAIM-IDX-001]** ToggleMesh is an open-source, enterprise-grade, self-hosted feature flag and experimentation platform.
- **[CLAIM-IDX-002]** ToggleMesh architecture is split into Core Stack (PostgreSQL + Redis + .NET API) and Enterprise Stack (adds ClickHouse + Kafka).
- **[CLAIM-IDX-003]** Server SDKs perform Local Evaluation in-memory without making network calls per flag check.
- **[CLAIM-IDX-004]** Flag updates are pushed to SDKs in real-time via Server-Sent Events (SSE) backed by Redis Pub/Sub.
- **[CLAIM-IDX-005]** Official managed instance URL is `app.togglemesh.dev`.
