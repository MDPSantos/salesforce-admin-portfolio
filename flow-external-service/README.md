# Flow Builder + External Service

**Status:** Portfolio scenario — documentation starter

## Business context
A service team needs to retrieve information from an external verification service while keeping the user process inside Salesforce. The provider, endpoint, response fields, and business rules in this example are fictional placeholders.

## Business requirements
- Allow an authorized user to initiate a verification from a Salesforce record.
- Validate required inputs before sending a request.
- Call an API operation exposed through Salesforce External Services.
- Handle successful responses, negative business results, and technical failures distinctly.
- Store only response data needed for the process.
- Avoid exposing secrets or sensitive payloads in screens, logs, or documentation.

## Proposed solution design
1. Confirm the use case, API contract, authentication, and data classification with the relevant owners.
2. Register the API schema so Salesforce can expose the operation as an External Service action.
3. Build a Screen Flow or record-triggered Flow, depending on the process entry point.
4. Validate inputs and use Decision elements to route success, negative business results, and errors.
5. Map required response fields to Salesforce fields or a related custom record.
6. Add fault paths and user-friendly messages; never show credentials or unrestricted raw responses.

## Illustrative flow outline
`Start → Validate Inputs → Call External Service → Evaluate Response → Save Relevant Data → Display Outcome`

Fault path: `External Service Fault → Capture Safe Diagnostic Context → Display Recoverable Error`

This is a proposed design, not a claim that a live endpoint or Flow is deployed.

## Configuration checklist
- [ ] Confirm business owner, requirements, and data classification.
- [ ] Define the request/response schema and required fields.
- [ ] Confirm Named Credential / External Credential setup with the integration owner.
- [ ] Configure and test the External Service registration.
- [ ] Build input validation and response-handling branches.
- [ ] Add fault handling and safe diagnostics.
- [ ] Validate CRUD, field-level security, and record-sharing behavior.
- [ ] Document deployment dependencies and rollback considerations.

## Test plan

| Scenario | Expected behavior |
| --- | --- |
| Required input is missing | Request is not sent; user receives validation guidance. |
| External service returns success | Relevant fields are mapped and the success path completes. |
| Service returns a negative business result | The business result is distinguished from a technical failure. |
| Service is unavailable or times out | A fault path gives a safe, understandable message. |
| Response is incomplete or unexpected | Missing values are handled without misleading the user. |
| User lacks record or field access | Unauthorized data is not exposed. |

## Evidence to add
- Sanitized Flow or architecture diagram.
- Example request/response using fictional data.
- Mapping table from response properties to Salesforce fields.
- Executed test cases and documented assumptions.
- Optional screenshots from a personal developer org, with sensitive details removed.

## Lessons learned
After completing a hands-on build, record design trade-offs, issues encountered, and improvements. Do not invent results or represent this portfolio scenario as a production implementation.
