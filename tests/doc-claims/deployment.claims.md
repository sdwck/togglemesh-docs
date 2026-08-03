# Claims: deployment.mdx

- **[CLAIM-DEP-001]** Official managed ToggleMesh Cloud URL is `app.togglemesh.dev`.
- **[CLAIM-DEP-002]** ToggleMesh Cloud uses Enterprise Stack (Kafka + ClickHouse).
- **[CLAIM-DEP-003]** Core Stack components: ToggleMesh API (Control Plane), Admin UI (Dashboard), PostgreSQL, Redis.
- **[CLAIM-DEP-004]** Core Stack compose file is `docker-compose.yml`.
- **[CLAIM-DEP-005]** Enterprise Stack adds Apache Kafka and ClickHouse.
- **[CLAIM-DEP-006]** Enterprise Stack compose file is `docker-compose.enterprise.yml`.
- **[CLAIM-DEP-007]** Kafka acts as a buffer for incoming analytics events (Exposures and Tracks).
- **[CLAIM-DEP-008]** ClickHouse acts as columnar database for analytics queries and MAB calculations.
- **[CLAIM-DEP-009]** ToggleMesh API automatically detects Kafka/ClickHouse connection strings in environment variables to enable Enterprise routing.
