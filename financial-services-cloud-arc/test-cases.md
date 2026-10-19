# Test Cases — FSC 360° Client Relationship Management

**Status legend:** Planned = not run; Pass/Fail = executed with evidence. Do not mark any scenario as passed before actually testing it.

| Test ID | Scenario | Preconditions / data | Steps | Expected result | Status |
| --- | --- | --- | --- | --- | --- |
| FSC-T01 | Client with complete relationships | Fictional client has the required household/group and financial-account links | Open client record and configured ARC view | Intended relationships appear and match the modeled links | Planned |
| FSC-T02 | Missing required relationship | Fictional client lacks one relationship defined as required | Open view and perform data-quality review | Missing relationship can be identified for remediation | Planned |
| FSC-T03 | Similar names without relationship link | Two fictional client records have similar names but no modeled link | Open relationship view | No relationship is inferred from names alone | Planned |
| FSC-T04 | Conflicting household association | Fictional sample intentionally violates an agreed relationship rule | Review the records and relationship view | Conflict can be identified and is not silently treated as valid | Planned |
| FSC-T05 | Authorized advisor | Test user has approved access to the client and related records | Open the client and navigate through the relationship view | Only authorized information is available and navigation works | Planned |
| FSC-T06 | Restricted financial account | Test user lacks access to a related account or restricted field | Attempt to view or navigate to the restricted information | Restricted information is not exposed | Planned |
| FSC-T07 | No financial account linked | Fictional client has no account relationship | Open the relationship view | The view does not display a fabricated relationship and remains understandable | Planned |
| FSC-T08 | Incorrect link correction | Test data is intentionally linked incorrectly; correction owner/process is defined | Follow documented correction process and re-check the view | Corrected relationship is reflected after the supported update process | Planned |
| FSC-T09 | Relationship-view usability timing | Defined relationship question and comparable before/after runs | Record task start and completion using the same method | Raw timings, sample size, and calculation are recorded | Planned |
| FSC-T10 | Configuration dependency | Test org's available FSC features are documented | Confirm the intended ARC feature and data model | Build proceeds only with supported features; limitations are recorded | Planned |

## Evidence template

For each executed test, record:

- **Test ID:**
- **Execution date:**
- **Org type / relevant feature availability:**
- **Tester persona:**
- **Test data:** fictional identifiers only
- **Actual steps performed:**
- **Expected result:**
- **Observed result:**
- **Status:** Pass / Fail / Blocked
- **Evidence link or screenshot:**
- **Defect / follow-up:**

## Measurement method

For task-time measurement:
1. Define one repeatable task, such as identifying all configured household and financial-account relationships for a fictional client.
2. Use the same instructions and comparable test data for the current-state and proposed-state runs.
3. Record start and end time consistently.
4. Document sample size and any conditions that could affect the comparison.
5. Calculate the average duration for each state and report the observed difference.
6. Label small or simulated samples as demonstration evidence, not production impact.

Formula:

Average task duration = total duration across completed runs ÷ number of completed runs

If a percentage reduction is calculated:

Reduction (%) = (baseline average − new average) ÷ baseline average × 100

Do not report a percentage unless both measurements were collected and the method is documented.
