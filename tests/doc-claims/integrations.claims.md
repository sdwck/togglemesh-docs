# Claims: integrations.mdx

- **[CLAIM-INT-001]** Slack provider formats payloads as color-coded blocks sent to a Slack Incoming Webhook URL.
- **[CLAIM-INT-002]** Discord provider formats payloads as embedded cards sent to a Discord Webhook URL.
- **[CLAIM-INT-003]** Generic Webhook provider sends raw HTTP POST payloads containing JSON Audit Events.
- **[CLAIM-INT-004]** Integrations are configured at Project level.
- **[CLAIM-INT-005]** A Project-level integration receives events across all Environments within that Project.
- **[CLAIM-INT-006]** Creating an integration triggers a test ping to verify connectivity.
- **[CLAIM-INT-007]** Generic Webhook HTTP method is `POST`.
- **[CLAIM-INT-008]** Generic Webhook JSON schema contains `eventId` of type string UUID.
- **[CLAIM-INT-009]** Generic Webhook JSON schema contains `timestamp` of type ISO 8601 DateTime.
- **[CLAIM-INT-010]** Generic Webhook JSON schema contains `action` string.
- **[CLAIM-INT-011]** Generic Webhook JSON schema contains `projectId` string UUID.
- **[CLAIM-INT-012]** Generic Webhook JSON schema contains `environmentId` string UUID.
- **[CLAIM-INT-013]** Generic Webhook JSON schema contains `actor` string (e.g. Email).
- **[CLAIM-INT-014]** Generic Webhook JSON schema contains `targetId` string.
- **[CLAIM-INT-015]** Generic Webhook JSON schema contains `diff` array of JSON Patch objects (`op`, `path`, `value`).
- **[CLAIM-INT-016]** Webhooks are dispatched asynchronously by background worker `WebhookDispatcherService`.
