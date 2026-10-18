# Service Cloud — Entitlements and SLA Assignment

**Status:** Portfolio scenario — design starter

## Business context
A service organization needs eligible cases to receive the correct entitlement or service-level treatment consistently. This scenario documents a declarative approach to assignment logic and validation.

## Requirements to confirm
- Which customers, products, case types, or channels qualify for each service level?
- Which field or related record is the source of truth?
- At what point should entitlement assignment occur?
- What should happen when no matching entitlement is found?
- How should reopened, transferred, or updated cases be handled?
- What permissions and auditability are required?

## Proposed declarative design
1. Define service-level rules with the business owner.
2. Identify required case and entitlement fields and relationships in the target org.
3. Use Flow entry conditions to limit processing to relevant records.
4. Use Decision elements to route cases according to approved criteria.
5. Assign the matching entitlement or route unmatched records to an explicit exception path.
6. Make automation idempotent where appropriate to avoid repeated or unintended updates.
7. Test create and update behavior, including changes to classification fields.

Exact configuration depends on the org's Entitlement Management setup and data model; verify available fields, relationships, and automation constraints before implementation.

## Illustrative decision table

| Condition | Expected outcome |
| --- | --- |
| Case meets an approved service-level rule | Apply the intended entitlement according to the design. |
| Case does not meet any rule | Follow the documented default or exception process. |
| Required matching field is blank | Do not assign arbitrarily; follow defined handling. |
| Classification changes after creation | Re-evaluate only if required by the business rule. |
| Flow encounters an error | Use a fault path and safe operational logging. |

## Acceptance criteria
- Eligible cases are handled according to the documented decision table.
- Ineligible cases do not receive an incorrect entitlement.
- Missing inputs are handled explicitly.
- Updates do not cause duplicate or conflicting processing.
- Test evidence covers rule and exception paths.

## Test plan and evidence
Add a rule-to-test traceability table, fictional cases, screenshots or diagrams from a demo org, and observed outcomes. Include happy paths and negative cases. Label unexecuted tests “planned,” not “passed.”

## Lessons learned
After hands-on validation, capture configuration constraints, maintainability choices, and stakeholder decisions that shaped the solution.
