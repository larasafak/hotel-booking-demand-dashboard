# User Acceptance Testing Plan

## Purpose

This simulated UAT plan defines how representative hotel users would confirm that the proposed reservation-monitoring process meets the agreed business requirements.

The tests have not been performed on a working system. They demonstrate how acceptance testing would be planned before a pilot implementation.

## UAT Objectives

The UAT process would confirm that:

- Complete bookings are processed correctly.
- Incomplete bookings enter the exception queue.
- Monitoring rules assign the expected review category.
- High-category bookings receive human review.
- Staff can manage the prioritised work queue.
- Confirmation activity is recorded correctly.
- Modified bookings are reassessed where required.
- Dashboard figures reconcile with source information.
- Unauthorised users cannot access customer-level information.
- The proposed process is understandable and usable for reservations staff.

## Entry Criteria

UAT should begin only when:

- Requirements have been reviewed and approved.
- Monitoring rules have been agreed.
- A functioning prototype is available.
- Test data has been prepared.
- User roles and access permissions have been configured.
- Critical system-testing defects have been resolved.
- UAT participants have received process guidance.
- Expected results have been agreed.

## Test Roles

| Role | Responsibility |
|---|---|
| UAT Owner | Approves the UAT scope and final outcome |
| Business Analyst | Prepares scenarios, supports users and records findings |
| Reservations Staff | Complete operational test scenarios |
| Reservations Manager | Validates workflow and business suitability |
| Revenue Manager | Validates dashboard measures and reporting |
| IT Team | Investigates and resolves technical defects |
| Compliance Representative | Reviews access, privacy and customer communication controls |

## UAT Scenarios

| Test ID | Scenario | Preconditions | Test Steps | Expected Result | Related Requirements | Priority |
|---|---|---|---|---|---|---|
| UAT-01 | Process a complete booking | Test booking contains all required information | Submit the booking for processing | Booking bypasses the exception queue and receives an operational review category | FR-01, FR-03, FR-04 | High |
| UAT-02 | Process a booking with missing information | A required field is blank | Submit the booking for processing | Booking enters the exception queue and the missing field is identified | FR-01, FR-02 | High |
| UAT-03 | Correct an incomplete booking | Booking is already in the exception queue | Add the missing information and resubmit | Booking leaves the exception queue and monitoring rules are applied | FR-01, FR-02 | High |
| UAT-04 | Review a high-category booking | Booking meets an approved high-category rule | Process and open the booking | Booking appears in the work queue and the contributing rule is visible | FR-03, FR-04, FR-05, NFR-03 | High |
| UAT-05 | Confirm no automatic cancellation | Booking receives a high operational category | Complete the assessment | Booking remains active and requires human review | FR-14 | High |
| UAT-06 | Record a staff follow-up | Booking appears in the work queue | Record a contact attempt and outcome | Activity, user, time and outcome are saved in the booking history | FR-07, FR-12, NFR-06 | High |
| UAT-07 | Prevent a duplicate reminder | A reminder has already been issued for the booking checkpoint | Run the reminder process again | A second reminder is not sent for the same checkpoint | FR-06 | Medium |
| UAT-08 | Reassess a modified booking | Active booking has an existing category | Change a material booking field and save | Rules are reapplied and the latest category is recorded | FR-08, FR-12 | Medium |
| UAT-09 | Record an unknown cancellation reason | A booking has been cancelled without a stated reason | Record the cancellation outcome | User can select Unknown or Not Provided without inventing information | FR-09 | Medium |
| UAT-10 | Filter the operational dashboard | Pilot data is available | Filter by hotel, lead time, market segment and channel | Measures update according to the selected filters | FR-10, FR-11 | High |
| UAT-11 | Reconcile dashboard totals | Approved pilot source data is available | Compare booking and cancellation totals with the dashboard | Figures match within the agreed tolerance | NFR-05 | High |
| UAT-12 | Block unauthorised access | User does not have an approved operational role | Attempt to open customer-level booking information | Access is denied | NFR-01 | High |
| UAT-13 | Review approved customer wording | An eligible booking reaches a reminder checkpoint | Generate the confirmation communication | Approved neutral wording is used and the internal category is not disclosed | NFR-08 | High |
| UAT-14 | Complete an item in the work queue | Booking has received the required staff action | Mark the review as completed | Booking leaves the active queue and remains available in the activity history | FR-05, FR-07, FR-12 | Medium |

## Test Result Recording

Each executed test would record:

| Field | Description |
|---|---|
| Test ID | Unique UAT scenario identifier |
| Tester | Person completing the test |
| Test date | Date the scenario was executed |
| Actual result | What happened during the test |
| Status | Pass, Fail or Blocked |
| Defect ID | Related defect where applicable |
| Evidence | Screenshot, report or system record |
| Comments | Relevant observations or follow-up actions |

## Defect Priorities

| Severity | Definition | Expected Response |
|---|---|---|
| Critical | Prevents a core process from operating or creates a serious security or customer risk | Resolve before pilot approval |
| High | Core requirement does not work and no acceptable workaround exists | Resolve before pilot approval |
| Medium | Requirement works partially or has an acceptable temporary workaround | Review before pilot and agree treatment |
| Low | Minor usability or presentation issue | Record and prioritise for a later release |

## UAT Exit Criteria

UAT may be considered complete when:

- All high-priority scenarios have been executed.
- All critical and high-severity defects have been resolved and retested.
- Dashboard figures reconcile with approved source data.
- Access-control tests pass.
- Reservations users confirm that the core workflow is understandable.
- Remaining medium and low defects have agreed owners and actions.
- The UAT Owner approves or rejects progression to the pilot.

## Requirements Traceability

| Business Need | Requirement | User Story | UAT Coverage |
|---|---|---|---|
| Consistent booking assessment | BR-01, FR-01 to FR-04 | US-01, US-02 | UAT-01 to UAT-05 |
| Prioritised staff activity | BR-06, FR-05 to FR-07 | US-03, US-04 | UAT-04, UAT-06, UAT-07, UAT-14 |
| Reassessment after changes | FR-08 | US-05 | UAT-08 |
| Improved cancellation information | BR-05, FR-09 | US-06 | UAT-09 |
| Operational reporting | BR-02, BR-03, FR-10, FR-11 | US-07 | UAT-10, UAT-11 |
| Security and traceability | FR-12, NFR-01, NFR-06 | US-08 | UAT-06, UAT-12, UAT-14 |
| Fair customer treatment | BR-04, FR-14, NFR-08 | US-02, US-04 | UAT-05, UAT-13 |

## Status

This UAT plan has the status **Draft simulated deliverable**. Test execution would require an implemented prototype, approved requirements and representative users.
