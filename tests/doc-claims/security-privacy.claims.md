# Claims: security-privacy.mdx

- **[CLAIM-SEC-001]** ToggleMesh supports 100% Virtual Private Cloud (VPC) isolation.
- **[CLAIM-SEC-002]** Local Evaluation ensures zero PII ever leaves your network.
- **[CLAIM-SEC-003]** Role-Based Access Control (RBAC) permissions are assignable at Project or Environment level.
- **[CLAIM-SEC-004]** Role `Viewer` permits viewing flags and analytics, but prevents changes.
- **[CLAIM-SEC-005]** Role `Editor` permits creating and updating flags, but prevents modifying Environment settings.
- **[CLAIM-SEC-006]** Role `Admin` grants full control over Project and Environments.
- **[CLAIM-SEC-007]** GDPR/CCPA identity purging is executed via endpoint `/projects/{projectId}/privacy/purge-identity`.
- **[CLAIM-SEC-008]** Purge Identity API method is `POST`.
- **[CLAIM-SEC-009]** Purge Identity API accepts user `Identity`.
- **[CLAIM-SEC-010]** Purge Identity locates `AnalyticsExposures` and `AnalyticsTracks` matching the identity hash.
- **[CLAIM-SEC-011]** Purge Identity issues coordinated `DELETE` commands across all Project Environments.
- **[CLAIM-SEC-012]** Purge Identity on Enterprise Stack executes `ALTER TABLE ... DELETE` in ClickHouse.
