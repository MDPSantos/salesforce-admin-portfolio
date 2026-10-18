# Financial Services Cloud + Actionable Relationship Center (ARC)

**Status:** Portfolio scenario — design starter

## Business context
Advisors and service users need a coherent view of an individual, their household or family relationships, and relevant financial accounts. This scenario explores organizing relationship information with Financial Services Cloud (FSC) concepts and ARC.

## Requirements to clarify
- Which person and household relationships must be visible?
- Which records are authoritative for each relationship?
- What qualifies as a complete relationship view?
- Which user groups may see household or financial-account details?
- What data-quality rules prevent duplicate, stale, or incorrectly linked relationships?
- Which actions should be available from the relationship view?

## Proposed design approach
1. Map business concepts to the FSC data model and features supported by the target org.
2. Document relationships among individuals, household/group records, and relevant financial accounts.
3. Define the ARC view's purpose, entry points, visibility, and required context.
4. Establish criteria for complete and correctly linked records.
5. Validate the experience with representative personas and fictional records.

Confirm object names and relationships in the actual target org; FSC data models and installed features can differ by configuration.

## Illustrative acceptance criteria
- A permitted user can identify the relevant household or group from an individual record.
- The relationship view displays only information that the user is authorized to access.
- Financial accounts appear in the intended context when the underlying relationships exist.
- Missing or inconsistent links can be identified using documented data-quality criteria.
- Similar text values alone do not create or imply a relationship.

## Validation plan

| Test | Expected result |
| --- | --- |
| Individual with complete household and account relationships | Intended relationships are visible in the configured view. |
| Individual with a missing relationship | Missing context is detectable; no false link is shown. |
| User without required access | Restricted information is not exposed. |
| Duplicate or conflicting relationship data | Issue is identified for resolution under documented rules. |
| Individual with no financial account | View remains clear without inventing a relationship. |

## Evidence to add
- Fictional data model or relationship diagram.
- ARC view design notes and rationale.
- Definitions of “complete” and “correctly linked.”
- Sanitized screenshots from a demo org, if available.
- Test scenarios with observed outcomes.

## Results and metrics
Only include metrics after running a defined test or collecting actual measurements. State the sample size, baseline, and calculation. Never present illustrative metrics as production outcomes.

## Lessons learned
Document model constraints, access considerations, and design trade-offs discovered during implementation. Label this a portfolio scenario unless based on a real project that can be shared without confidential information.
