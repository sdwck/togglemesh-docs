# Claims: realtime-sync.mdx

- **[CLAIM-RTS-001]** ToggleMesh uses Server-Sent Events (SSE) instead of HTTP polling.
- **[CLAIM-RTS-002]** Flag updates commit first to PostgreSQL.
- **[CLAIM-RTS-003]** After committing to PostgreSQL, the API publishes an invalidation event to Redis topic `togglemesh-sse-updates`.
- **[CLAIM-RTS-004]** Redis Pub/Sub payload contains event name and `EnvironmentId`.
- **[CLAIM-RTS-005]** API nodes subscribe to `togglemesh-sse-updates` Redis topic.
- **[CLAIM-RTS-006]** API fan-out pushes flag updates down SSE connections filtered by `EnvironmentId`.
- **[CLAIM-RTS-007]** SDK atomically updates its in-memory dictionary upon receiving SSE payload.
- **[CLAIM-RTS-008]** SSE was chosen over WebSockets because feature flag sync is strictly unidirectional (Server -> Client).
- **[CLAIM-RTS-009]** SSE operates over standard HTTP/HTTPS (port 443).
- **[CLAIM-RTS-010]** SSE streams reconnect natively using browser/HTTP client built-in reconnection mechanisms.
- **[CLAIM-RTS-011]** API nodes scale horizontally behind load balancers using Redis Pub/Sub backplane.
