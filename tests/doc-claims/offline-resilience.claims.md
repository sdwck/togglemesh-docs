# Claims: offline-resilience.mdx

- **[CLAIM-OFR-001]** ToggleMesh Server SDKs maintain a local JSON fallback file on disk.
- **[CLAIM-OFR-002]** .NET SDK registration option for fallback file is `options.UseFallbackFile`.
- **[CLAIM-OFR-003]** Default value for `options.UseFallbackFile` is `true`.
- **[CLAIM-OFR-004]** .NET SDK registration option for file path is `options.FallbackFilePath`.
- **[CLAIM-OFR-005]** Default file path for `options.FallbackFilePath` is `"togglemesh-fallback.json"`.
- **[CLAIM-OFR-006]** On successful sync or SSE update, SDK asynchronously calls `SaveFallbackAsync()` to persist state to disk.
- **[CLAIM-OFR-007]** On failed boot/connection timeout, SDK calls `LoadFallbackAsync()` to read disk cache.
- **[CLAIM-OFR-008]** Fallback file contains both flag states and segment definitions.
- **[CLAIM-OFR-009]** Failed boot triggers background recovery attempts to reconnect to SSE stream using exponential backoff.
- **[CLAIM-OFR-010]** Zero-Network mode allows running SDKs without network access by pre-populating `togglemesh-fallback.json`.
