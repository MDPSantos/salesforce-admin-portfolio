# Solution Design — FSC 360° Client Relationship Management

**Status:** Proposed design; validate against the actual FSC-enabled org before implementation.

## 1. Design goals

- Help an advisor understand relevant client relationships from a focused relationship view.
- Make relationship completeness and data-quality expectations explicit.
- Respect access restrictions for sensitive customer and financial-account information.
- Keep the implementation declarative where practical and document org-specific dependencies.

## 2. High-level process

1. Advisor opens the intended client record.
2. Advisor opens the configured Actionable Relationship Center (ARC) view.
3. ARC presents the supported, configured relationships relevant to that client.
4. Advisor reviews the relationships and navigates to records they are authorized to access.
5. If a missing or inconsistent relationship is noticed, the issue is routed through the agreed data-quality remediation process.
6. Administrator or authorized operations user corrects the source relationship according to the established ownership rules.

## 3. Conceptual data model

The scenario contains these business concepts:

- **Individual client:** the person whose relationship context is being reviewed.
- **Household or group:** a household/group association that connects relevant people when the business model supports it.
- **Financial account:** an account related to one or more clients according to the bank's modeled relationships.
- **Relationship link:** the underlying association that explains why one record is connected to another.

The exact Salesforce object names, relationship objects, and supported relationship paths depend on the FSC data model and features enabled in the target org. Inspect the actual org before mapping these concepts to objects; do not assume all orgs use identical configurations.

## 4. ARC design considerations

- Define the intended user persona and question the view is meant to answer.
- Choose a client-record entry point suitable for the org's configured ARC experience.
- Include only relationship types needed for the agreed use cases.
- Use clear labels and avoid displaying irrelevant relationship branches.
- Confirm that navigation to related records behaves as expected.
- Validate display and record access independently; hiding a link in a diagram is not a substitute for Salesforce security.

## 5. Data quality design

Agree on explicit definitions before building indicators or operational reports.

Possible rules to validate:
- Required relationship links are present for the selected scenario.
- The linked records exist and are of the expected type.
- Conflicting household associations are reviewed under an agreed business rule.
- A financial-account relationship is supported by an actual configured link, not a text/name match.
- Data correction has an identified owner and audit process.

Whether each rule is enforced through fields, reports, Flow, validation, or a manual review depends on the data model and target-org capabilities. Do not add automation until the business owner confirms the rule and exception behavior.

## 6. Security design

Test access using representative users or test personas. Validate:
- Object-level permissions.
- Field-level security for sensitive fields.
- Record-level access and sharing.
- Navigation from ARC to a related record.
- Behavior when a user lacks access to a related record or field.

Follow the organization's approved security model and least-privilege principle. Do not use admin access alone to validate end-user behavior.

## 7. Implementation stages

### Stage 1 — Discover
- Confirm FSC availability, licenses, data model, and current configuration.
- Interview or simulate stakeholder discovery using the questions in the business-requirements document.
- Agree on relationship types and completeness rules.

### Stage 2 — Model and configure
- Create fictional client, household/group, and financial-account data using supported objects.
- Establish the required relationship links.
- Configure the ARC experience supported by the org.
- Apply and validate access settings.

### Stage 3 — Validate
- Execute all cases in test-cases.md.
- Capture screenshots with synthetic data only.
- Record planned versus executed tests accurately.
- Measure baseline and task time using a consistent task and sample.

### Stage 4 — Document
- Add a conceptual relationship diagram and sanitized screenshots.
- Record the exact configuration dependencies and observed limitations.
- Summarize results without presenting targets as measured improvements.

## 8. Proposed demo data

Use fictional names such as:
- Jordan Taylor — individual client.
- Morgan Taylor — related household member.
- Taylor Household — household/group label.
- Everyday Checking — fictional financial-account label.

These labels are examples only. Use fields and relationships supported by the actual org. Do not use real customer data or account numbers.

## 9. Risks and mitigations

| Risk | Mitigation |
| --- | --- |
| ARC or required FSC features are unavailable in the demo org | Confirm licenses/features before committing to the build; document the limitation and adjust the scope if needed. |
| Data model differs from assumptions | Inspect the org's object model and relationship configuration before mapping fields. |
| Incomplete data makes the view misleading | Define quality rules and include missing-link test scenarios. |
| Sensitive information is exposed | Test with least-privilege personas and fictional data. |
| Expected metrics are reported as actual | Clearly label targets, baseline, sample, and observed results separately. |
