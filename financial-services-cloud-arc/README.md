# Financial Services Cloud — 360° Client Relationship Management

**Focus:** Financial Services Cloud (FSC) • Actionable Relationship Center (ARC) • Relationship Data Quality • Access Control  
**Status:** Portfolio scenario — requirements and design documented; hands-on implementation and measurements are not yet claimed.

## 1. Business context

A fictional financial institution serves individual clients who may be connected through family or household relationships and may have multiple financial accounts. Relationship information is spread across client, household/group, and financial-account records. During meetings and service interactions, advisors can spend time navigating between records to understand the client's wider relationship context.

The goal is to make relevant, authorized relationship context easier to understand from Salesforce using Financial Services Cloud (FSC) and the Actionable Relationship Center (ARC).

## 2. Personas

- **Financial Advisor:** needs to understand relevant client, household, and financial-account relationships before a meeting or follow-up.
- **Relationship Manager:** needs a consistent view of connected clients and a way to identify incomplete or conflicting relationship data.
- **Salesforce Administrator:** configures the experience, validates the data model, manages access, and supports data quality and maintainability.

## 3. Problem statement

Today, a user may need to open several records and manually piece together how a client is connected to a household or group and to relevant financial accounts. Incomplete or conflicting relationships can make this task less reliable.

Potential business impacts:
- Additional time spent finding relationship context.
- Inconsistent understanding of a client's household relationships.
- Reduced confidence when relationship data is missing or outdated.
- Risk of exposing data to users who should not be able to see it if access is not properly designed.

These are problem hypotheses for this fictional scenario and should be validated with stakeholders before implementation.

## 4. User story

> **As a Financial Advisor, I want to view a client's relevant household and financial-account relationships in one relationship view, so that I can understand the client's context more efficiently before a meeting or service interaction.**

### Supporting user stories

- **As a Relationship Manager**, I want incomplete or inconsistent relationship information to be identifiable, so that data issues can be resolved.
- **As a Salesforce Administrator**, I want access to relationship and financial-account information to follow the agreed security model, so that users see only the data they are authorized to access.

## 5. Proposed Salesforce solution

1. Confirm the available FSC features, licensed data model, and relationship objects in the target org.
2. Map the client, household/group, and financial-account relationships using the data model available in that org.
3. Configure an ARC experience to present the relationships needed by the advisor persona.
4. Define data-quality rules for complete and correctly linked records.
5. Review object, field, and record-level access for each persona.
6. Validate the relationship view with fictional client records, including missing and conflicting relationship cases.
7. Document user guidance and an operational process for correcting data-quality issues.

The design is configuration-dependent. Object names and relationships must be confirmed in the actual FSC org; this repository does not imply that a licensed FSC environment is available or that the configuration has already been implemented.

## 6. Acceptance criteria overview

- An authorized advisor can reach the configured relationship view from the intended client context.
- The view presents the relationship types agreed during requirements discovery.
- Related records appear only when the underlying relationship is present and valid.
- Missing or conflicting links can be identified using documented data-quality criteria.
- Users without appropriate access cannot see restricted records or fields.
- The solution is tested with positive, negative, incomplete-data, and access-control scenarios.

Detailed criteria and test scenarios are maintained in [acceptance-criteria.md](./acceptance-criteria.md) and [test-cases.md](./test-cases.md).

## 7. Expected business outcomes

Expected outcomes to validate:
- Less time spent navigating between records to understand relationship context.
- More consistent visibility into household and financial-account relationships.
- Better identification of incomplete relationship data.
- Appropriate protection of restricted financial information.

### Proposed measurement plan

| Measure | How it will be measured |
| --- | --- |
| Time to understand relationship context | Time a participant needs to answer a defined relationship question, measured before and after the proposed experience. |
| Relationship data completeness | Percentage of sampled records meeting the agreed completeness rules. |
| Relationship accuracy | Percentage of sampled links verified against the fictional scenario's source-of-truth rules. |
| Access-control test results | Count of pass/fail cases for authorized and unauthorized access scenarios. |

**No measured improvements are claimed yet.** Establish the baseline, sample size, and targets with stakeholders before testing. Record actual observations only after running the tests.

## 8. Project files

- [Business requirements and user stories](./business-requirements.md)
- [Solution design](./solution-design.md)
- [Acceptance criteria](./acceptance-criteria.md)
- [Test cases](./test-cases.md)

## 9. Evidence to add after implementation

- Fictional client/household relationship diagram.
- Sanitized screenshots of the configured ARC view in a suitable demo org.
- Relationship completeness rules and a sample data-quality review.
- Test evidence for relationship display and permission boundaries.
- Measurement notes showing test sample, baseline, and actual results.

## 10. Scope and confidentiality

This is a fictional portfolio scenario. Do not include client information, real account details, credentials, session identifiers, internal URLs, or confidential configuration. Distinguish proposed design from features actually configured and tested. Do not describe expected outcomes as measured production results.
