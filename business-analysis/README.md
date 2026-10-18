# Salesforce Business Analysis — Requirements to UAT

**Status:** Portfolio scenario — documentation template

This project demonstrates how a Salesforce functional professional translates a business problem into clear, testable delivery artifacts. Fill it with a fictional process or a real example that can be shared without confidential information.

## 1. Business problem
Describe who experiences the problem, the current process, its impact, and why a change is needed. Separate confirmed facts from assumptions.

## 2. Stakeholders and discovery
Document stakeholder groups, discovery questions, current-state process, pain points, constraints, and unresolved decisions.

## 3. Scope

**In scope**
- [Add agreed process, users, records, and expected behavior.]

**Out of scope**
- [List exclusions to prevent scope ambiguity.]

**Assumptions and dependencies**
- [Record assumptions, owners, integration dependencies, and decisions awaiting confirmation.]

## 4. Example user story
> As a [user persona], I want to [perform an action], so that [business value].

### Acceptance criteria (Given / When / Then)
- **Given** [initial state and permissions], **when** [the user performs an action], **then** [the observable system behavior].
- **Given** [a missing or invalid input], **when** [the action is attempted], **then** [the system follows agreed validation behavior].
- **Given** [the user does not have access], **when** [the user attempts the action], **then** [restricted data or functionality remains unavailable].

Replace bracketed text with scenario-specific details before treating these as executable criteria.

## 5. Functional solution outline
Describe proposed Salesforce objects, fields, automation, access model, integrations, and user experience. Note decisions requiring technical validation. Avoid prescribing implementation before requirements are understood.

## 6. Requirement traceability

| Requirement ID | Requirement | Solution component | Test case | Status |
| --- | --- | --- | --- | --- |
| REQ-001 | [Business requirement] | [Flow / field / permission / integration] | UAT-001 | Draft |
| REQ-002 | [Business requirement] | [Solution component] | UAT-002 | Draft |

## 7. UAT scenarios

| Test ID | Preconditions | Steps | Expected result | Outcome |
| --- | --- | --- | --- | --- |
| UAT-001 | [Preconditions] | [Steps] | [Expected behavior] | Not run |
| UAT-002 | [Preconditions] | [Steps] | [Expected behavior] | Not run |
| UAT-003 | [Negative-path preconditions] | [Steps] | [Expected restriction or error] | Not run |

Do not mark a test as passed until executed and the evidence is reviewed by the appropriate stakeholder.

## 8. Change and sign-off
Record open questions, decisions, requirement changes, defect triage, business-owner approval, and release dependencies.

## 9. Retrospective
After completion, summarize what changed, what was validated, what remained out of scope, and what you would improve. Do not invent benefits, approval, or production outcomes.
