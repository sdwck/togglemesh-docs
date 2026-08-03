# Claims: troubleshooting.mdx

- **[CLAIM-TS-001]** Reverse proxies terminating idle connections cause SSE stream disconnects every 30-60 seconds.
- **[CLAIM-TS-002]** Nginx SSE location block requires `proxy_http_version 1.1`.
- **[CLAIM-TS-003]** Nginx SSE location block requires `proxy_set_header Connection ''`.
- **[CLAIM-TS-004]** Nginx SSE location block requires `proxy_buffering off`.
- **[CLAIM-TS-005]** Nginx SSE location block requires `proxy_cache off`.
- **[CLAIM-TS-006]** Nginx SSE location block requires `proxy_read_timeout 86400s`.
- **[CLAIM-TS-007]** Nginx SSE location block requires `proxy_send_timeout 86400s`.
- **[CLAIM-TS-008]** Enterprise Stack consumer worker is named `KafkaAnalyticsConsumerWorker`.
- **[CLAIM-TS-009]** Kafka analytics topic name is `togglemesh-events`.
- **[CLAIM-TS-010]** Kafka connection environment variable is `Analytics__Kafka__BootstrapServers`.
- **[CLAIM-TS-011]** ClickHouse connection environment variable is `Analytics__ClickHouse__ConnectionString`.
- **[CLAIM-TS-012]** Database user requires DDL privileges to execute `CREATE TABLE` for monthly `AuditLogs` partitions.
- **[CLAIM-TS-013]** Partition worker is named `PartitioningWorker`.
- **[CLAIM-TS-014]** `PartitioningWorker` attempts to create partitions one month in advance.
- **[CLAIM-TS-015]** Redis is a mandatory requirement for Control Plane.
- **[CLAIM-TS-016]** Redis is required for Pub/Sub flag update broadcasting.
- **[CLAIM-TS-017]** Redis is required for Caching API keys and environment metadata.
- **[CLAIM-TS-018]** Control Plane API targets response latency under `<10ms`.
