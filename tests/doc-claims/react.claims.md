# Claims: react.mdx

- **[CLAIM-SDK-REACT-001]** Package name is `togglemesh-js` with subpath export `togglemesh-js/react`.
- **[CLAIM-SDK-REACT-002]** Client constructor uses `clientKey` (starts with `tm_client_`) for Remote Evaluation.
- **[CLAIM-SDK-REACT-003]** Initial identification uses `tmClient.identify(identity, context)`.
- **[CLAIM-SDK-REACT-004]** Provider component is `<ToggleMeshProvider client={tmClient}>`.
- **[CLAIM-SDK-REACT-005]** Hooks include: `useFeatureFlag(flagKey, default)` and `useFeatureFlagVariation(flagKey, default)`.
