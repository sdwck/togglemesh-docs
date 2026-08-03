# Claims: database-partitioning.mdx

- **[CLAIM-DBP-001]** Data lifecycle is managed by `PartitioningWorker`.
- **[CLAIM-DBP-002]** `PartitioningWorker` is orchestrated via Quartz inside ToggleMesh API.
- **[CLAIM-DBP-003]** `PartitioningWorker` uses C# attribute `[DisallowConcurrentExecution]`.
- **[CLAIM-DBP-004]** `[DisallowConcurrentExecution]` ensures only one API node performs partition cleanup at a time.
- **[CLAIM-DBP-005]** Audit Log retention environment variable is `AuditLogs__RetentionDays`.
- **[CLAIM-DBP-006]** Analytics retention environment variable is `Analytics__RetentionDays`.
- **[CLAIM-DBP-007]** On PostgreSQL, `PartitioningWorker` uses `ExecuteDeleteAsync` for analytics cleanup.
- **[CLAIM-DBP-008]** On ClickHouse (Enterprise Stack), `PartitioningWorker` executes `ALTER TABLE ... DELETE`.
- **[CLAIM-DBP-009]** PostgreSQL Audit Logs table uses monthly table partitioning.
- **[CLAIM-DBP-010]** Partitioning worker creates monthly partition tables using SQL `CREATE TABLE IF NOT EXISTS "AuditLogs_YYYY_MM" PARTITION OF "AuditLogs" FOR VALUES FROM ('YYYY-MM-01') TO ('YYYY-MM+1-01')`.
