# Business Requirements — FSC 360° Client Relationship Management

**Document status:** Draft for a fictional portfolio scenario  
**Business domain:** Financial services / client relationship management

## 1. Objective

Improve how financial advisors understand an individual client's relevant household and financial-account relationships by using an appropriately configured Financial Services Cloud (FSC) relationship model and Actionable Relationship Center (ARC).

## 2. Stakeholders and personas

| Persona | Need | Concern |
| --- | --- | --- |
| Financial Advisor | Understand client relationships before a meeting or service interaction | Time spent navigating records; incomplete context |
| Relationship Manager | Maintain a consistent view of connected clients and identify data issues | Conflicting, missing, or stale relationship data |
| Salesforce Administrator | Configure ARC, validate the underlying data model, and maintain access rules | License/configuration dependencies, security, and maintainability |
| Data/Operations Owner (supporting stakeholder) | Define authoritative sources and rules for correcting relationship records | Data ownership and remediation workflow |

## 3. Current-state problem

In the fictional current state, users may navigate between individual client records, household/group records, and financial-account records to assemble the relevant context manually. Some relationship links may be missing or inconsistent.

This is a hypothesis to validate during discovery, not a claim about a real institution.

### Discovery questions

- Which relationship types do advisors need to see during a client interaction?
- What is the authoritative source for household/group membership and financial-account relationships?
- Which relationships are required versus optional?
- How should joint accounts or multiple household associations be represented?
- Who owns correction of missing, stale, or conflicting relationship data?
- Which roles can see each relationship type and financial-account detail?
- Where should the ARC view be accessible, and what actions should be available?
- What baseline task time and data-quality measures can be collected?

## 4. Scope

### In scope
- Review of the FSC data model and available features in the target org.
- Relationship mapping for fictional individual, household/group, and financial-account records.
- ARC view design for advisor use.
- Relationship data-quality rules.
- Persona-based access validation.
- Acceptance criteria, test cases, and a proposed measurement plan.

### Out of scope for the initial portfolio scenario
- Real customer or banking data.
- Production deployment or integration with a real core banking system.
- Financial advice, credit decisions, eligibility decisions, or product recommendations.
- Claims of measured productivity gains before testing.
- Any FSC feature that is not available in the selected org or its license.

## 5. User stories

### US-01 — View relationship context
**As a Financial Advisor,** I want to view a client's relevant household and financial-account relationships in one relationship view, **so that** I can understand the client's context more efficiently before a meeting or service interaction.

### US-02 — Identify relationship data issues
**As a Relationship Manager,** I want missing or inconsistent relationship information to be identifiable using agreed data-quality rules, **so that** incorrect or incomplete links can be reviewed and corrected.

### US-03 — Protect sensitive information
**As a Salesforce Administrator,** I want relationship views to respect the org's object, field, and record access model, **so that** users only see information they are authorized to access.

## 6. Business requirements

| ID | Requirement | Priority | Notes |
| --- | --- | --- | --- |
| BR-01 | The advisor can navigate from the intended client record to the configured relationship view. | Must | Confirm entry point in the actual org. |
| BR-02 | The view displays the agreed relationship types for the selected client. | Must | Relationship types are to be confirmed during discovery. |
| BR-03 | A relationship appears only when the underlying records and link are present and valid. | Must | No relationship should be inferred from similar names alone. |
| BR-04 | Missing or conflicting relationships can be identified using documented rules. | Should | Detection may be a review process or configured indicator, depending on features. |
| BR-05 | Access to relationship and financial-account information follows the agreed security model. | Must | Test object, field, and record-level access. |
| BR-06 | The design is maintainable and documented for administrators. | Should | Include configuration dependencies and support notes. |
| BR-07 | The team can measure relationship-context task time and data completeness during testing. | Should | Establish baseline and targets before the comparison. |

## 7. Assumptions and dependencies

- An appropriate FSC-enabled demo org is available for hands-on ARC configuration.
- The selected org's data model and licenses support the required relationship view.
- Fictional records can be created for testing.
- Stakeholders agree on relationship definitions and data-quality rules.
- Security behavior is validated in the target org rather than assumed from this document.

## 8. Expected business outcomes

- Reduce effort needed to assemble relationship context.
- Increase consistency in how advisors view client relationships.
- Make relationship data-quality problems easier to identify.
- Maintain appropriate confidentiality of financial information.

Outcomes are expected, not yet observed. Confirm measurable targets after collecting baseline data.

## 9. Open questions

- Which FSC relationship model and object configuration will the demo org use?
- Which relationship types should the ARC view show?
- Which data-quality rule defines a complete relationship record?
- Who is responsible for remediation?
- What roles and permission configurations will be used for access testing?
