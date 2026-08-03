# Claims: custom-operators.mdx

- **[CLAIM-OP-001]** Rule Engine implements `IRuleOperator` interface in C# API and matching implementations in SDKs.
- **[CLAIM-OP-002]** Supported operators include: Equals, NotEquals, Contains, StartsWith, EndsWith, InList, MatchesRegex, GreaterThan, LessThan, SemVerGreaterThan, SemVerLessThan, InSegment.
- **[CLAIM-OP-003]** SemVer evaluation parses semantic versions according to SemVer 2.0 specs.
- **[CLAIM-OP-004]** Unknown/unsupported operators evaluate to `false` without crashing the Rule Engine.
