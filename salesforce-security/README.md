# Salesforce Security & Access Management

**Status:** Portfolio scenario — security-design starter

## Business context
An organization needs users to have the access required for their jobs without granting unnecessary permissions. This scenario presents a structured way to reason about Salesforce access and validate the result.

## Design principles
- Apply least privilege: grant only access required for the role.
- Separate baseline access from job-specific permissions.
- Consider object permissions, field-level security, record access, and app/tab visibility as distinct layers.
- Review profiles, permission sets, permission-set groups, roles, sharing rules, teams, and organization-wide defaults as applicable.
- Avoid granting broad administrative access as a shortcut to resolve access issues.
- Use fictional personas and metadata in public examples.

## Example persona matrix

| Persona | Example access intent | Validation focus |
| --- | --- | --- |
| Service agent | Work assigned service records and permitted customer data | Object/field access and record sharing |
| Team lead | View team workload and perform approved supervisory actions | Role hierarchy, sharing, and report access |
| Read-only analyst | Review approved reporting data without editing source records | Read-only permissions and field restrictions |
| Salesforce administrator | Configure platform settings within assigned responsibilities | Elevated access review and separation of duties |

This is an illustrative matrix, not a universal permission recommendation. Tailor it to actual responsibilities and policy.

## Review workflow
1. Gather job responsibilities and required data access.
2. Inventory current permissions and sharing behavior.
3. Identify excessive access and gaps.
4. Design the smallest set of changes that meets requirements.
5. Test both permitted and denied actions with representative users.
6. Obtain owner approval and document the change.
7. Re-test after deployment and schedule periodic reviews.

## Test cases

| Test | Expected result |
| --- | --- |
| Persona opens an authorized record | Record is accessible. |
| Persona attempts to open a restricted record | Access is denied unless an explicit sharing path grants access. |
| Persona attempts an unauthorized field edit | The field cannot be edited. |
| Persona attempts an unauthorized object action | The action is unavailable or rejected. |
| Permission is removed | Access does not remain through an unintended permission path. |
| Temporary access is required | Approval, scope, and removal date are documented. |

## Deliverables to add
- Sanitized persona access matrix.
- Diagram of organization-wide defaults and sharing layers.
- Fictional or safely anonymized permission inventory.
- Positive and negative test evidence.
- Change-review checklist.

## Security notes
Never publish credentials, access tokens, session IDs, customer data, internal org URLs, or confidential screenshots. Do not use production information in a public portfolio. Describe any real-world example only to the extent permitted by confidentiality obligations.
