# Acceptance Criteria — FSC 360° Client Relationship Management

Acceptance criteria are proposed for a fictional portfolio scenario. Confirm them with the business owner and adjust them to the actual data model and FSC capabilities.

## AC-01 — Open the relationship view

**Given** an authorized Financial Advisor is viewing a client record  
**When** the advisor opens the configured ARC experience  
**Then** the intended relationship view is available and provides context for that client.

## AC-02 — Display configured relationships

**Given** the fictional client has valid, configured relationships to a household/group and a financial account  
**When** the advisor opens the relationship view  
**Then** the view displays the agreed relationship types and allows navigation to records the advisor can access.

## AC-03 — Do not show unsupported links

**Given** two records have similar names but no configured relationship link  
**When** the advisor views the relationship context  
**Then** the system does not imply that the records are related solely because their names are similar.

## AC-04 — Identify missing relationship information

**Given** a record is missing a relationship that the business rules define as required  
**When** the data-quality review is performed  
**Then** the missing relationship can be identified and routed to the agreed remediation owner.

## AC-05 — Handle conflicting relationship data

**Given** fictional relationship records conflict with a documented business rule  
**When** the records are reviewed  
**Then** the conflict is identifiable and is not silently represented as confirmed truth.

## AC-06 — Enforce access restrictions

**Given** a user does not have permission to view a related financial record or field  
**When** that user attempts to access the relationship information or navigate to the record  
**Then** Salesforce does not expose the restricted information, consistent with the configured security model.

## AC-07 — Validate relationship accuracy

**Given** a sample of fictional relationship links has been prepared with known expected relationships  
**When** the test sample is compared with the configured relationship view  
**Then** each displayed link matches the expected relationship rules or is documented as a defect.

## AC-08 — Measure task time consistently

**Given** a defined task and test participants or repeatable test runs are available  
**When** task duration is recorded before and after the new relationship view is configured  
**Then** the measurement notes include the task definition, sample size, baseline, and observed durations.

## AC-09 — Keep test evidence truthful

**Given** the project documentation describes configuration or test results  
**When** a reader reviews the evidence  
**Then** proposed design, planned tests, executed tests, and measured results are clearly distinguished.

## Definition of Done

- [ ] Requirements and relationship types have been reviewed.
- [ ] Data model and FSC feature availability have been confirmed in the target org.
- [ ] ARC experience is configured, if supported by the available org.
- [ ] Security behavior is validated with representative users.
- [ ] Positive, negative, incomplete-data, and access-control tests are documented.
- [ ] Screenshots use fictional data and contain no sensitive details.
- [ ] Results distinguish expected outcomes from observed measurements.
