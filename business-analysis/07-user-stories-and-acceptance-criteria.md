# User Stories and Acceptance Criteria

## Purpose

These simulated user stories translate the requirements catalogue into testable delivery items for the proposed reservation-monitoring pilot.

The stories have not been validated by real hotel stakeholders. In a live project, they would be refined with users, estimated by the delivery team and agreed before development.

## US-01 Validate Booking Information

**User story**

As a reservations agent, I want the system to check whether the required booking information is available so that I do not make decisions using incomplete records.

**Related requirements:** FR-01, FR-02, NFR-04

**Priority:** Must Have

### Acceptance criteria

```gherkin
Scenario: Booking contains all required information
  Given a new booking has entered the reservation system
  And all required fields contain valid information
  When the booking is processed
  Then it is eligible for the approved monitoring rules
  And it is not placed in the exception queue

Scenario: Booking is missing required information
  Given a new booking has entered the reservation system
  And one or more required fields are missing
  When the booking is processed
  Then it is placed in the exception queue
  And the missing fields are identified for the reservations agent

Scenario: Missing information is corrected
  Given a booking is in the exception queue
  And an authorised user adds the required information
  When the booking is resubmitted
  Then the booking is removed from the exception queue
  And the approved monitoring rules are applied
```

## US-02 Categorise Bookings for Operational Review

**User story**

As a reservations manager, I want eligible bookings to be categorised using approved and transparent rules so that the team can apply a consistent review process.

**Related requirements:** FR-03, FR-04, FR-14, NFR-03

**Priority:** Must Have

### Acceptance criteria

```gherkin
Scenario: Eligible booking is categorised
  Given a booking contains all required information
  And the pilot monitoring rules are active
  When the booking is assessed
  Then it is assigned a low, medium or high operational review category
  And the contributing rule or rules are recorded

Scenario: Staff member reviews the reason
  Given a booking has been assigned an operational review category
  When an authorised staff member opens the booking
  Then the staff member can view the rules that contributed to the category

Scenario: High-category booking is not automatically cancelled
  Given a booking has been assigned a high operational review category
  When the assessment is completed
  Then the booking remains active
  And it is sent for human review
```

## US-03 Manage the Prioritised Work Queue

**User story**

As a reservations agent, I want to see bookings requiring attention in a prioritised work queue so that I can focus on the appropriate customer follow-ups.

**Related requirements:** FR-05, NFR-04, NFR-07

**Priority:** Must Have

### Acceptance criteria

```gherkin
Scenario: High-category booking enters the queue
  Given a booking has been assigned a high operational review category
  When processing is completed
  Then the booking appears in the staff work queue
  And its required action and review deadline are displayed

Scenario: Agent filters the queue
  Given the reservations agent is viewing the work queue
  When the agent filters by hotel, category or required action date
  Then only bookings matching the selected conditions are displayed

Scenario: Completed item leaves the active queue
  Given a booking is in the work queue
  And an authorised agent records the required review outcome
  When the item is marked as completed
  Then it is removed from the active queue
  And its activity history remains available
```

## US-04 Send and Record Confirmation Reminders

**User story**

As a reservations agent, I want eligible customers to receive an appropriately timed confirmation reminder so that booking intentions can be clarified before arrival.

**Related requirements:** FR-06, FR-07, NFR-08

**Priority:** Should Have

### Acceptance criteria

```gherkin
Scenario: Booking reaches a confirmation checkpoint
  Given a booking meets an approved reminder rule
  And the booking remains active
  When the configured confirmation date is reached
  Then an approved reminder is scheduled
  And the reminder activity is recorded

Scenario: Customer confirms the booking
  Given a confirmation reminder has been sent
  When the customer confirms the reservation
  Then the response is recorded
  And the booking status remains active

Scenario: Reminder is not duplicated
  Given a reminder has already been successfully sent for the same checkpoint
  When the reminder process runs again
  Then a duplicate reminder is not sent

Scenario: Customer communication uses approved wording
  Given a reminder is ready to be sent
  When the communication is generated
  Then it uses the template approved by marketing and compliance
  And it does not disclose the internal operational category
```

## US-05 Reassess Modified Bookings

**User story**

As a reservations agent, I want materially modified bookings to be reassessed so that the required action reflects the latest booking information.

**Related requirements:** FR-08, FR-12

**Priority:** Should Have

### Acceptance criteria

```gherkin
Scenario: Material booking modification occurs
  Given an active booking has already been categorised
  And a defined material field is changed
  When the modification is saved
  Then the monitoring rules are reapplied
  And the latest category is recorded

Scenario: Category changes after modification
  Given a modified booking receives a different category
  When reassessment is completed
  Then the active work queue is updated
  And the previous category remains available in the audit history

Scenario: Non-material field is changed
  Given an active booking has already been categorised
  When a field not defined as material is changed
  Then reassessment is not triggered
```

## US-06 Record Cancellation Reasons

**User story**

As a revenue manager, I want cancellation reasons to be recorded consistently so that the organisation can investigate why customers cancel and improve future decisions.

**Related requirements:** FR-09, BR-05

**Priority:** Should Have

### Acceptance criteria

```gherkin
Scenario: Cancellation reason is available
  Given a booking has been cancelled
  When an authorised user records the cancellation
  Then the user can select an approved cancellation-reason category
  And the reason is linked to the booking record

Scenario: Cancellation reason is unknown
  Given a booking has been cancelled
  And the customer has not provided a reason
  When the cancellation is recorded
  Then the user can select Unknown or Not Provided
  And personal information is not invented

Scenario: Manager reviews cancellation reasons
  Given cancellation reasons have been recorded
  When an authorised manager opens the dashboard
  Then the manager can review aggregated cancellation counts by reason
```

## US-07 Monitor Pilot Performance

**User story**

As a general manager, I want a dashboard showing booking, cancellation and intervention outcomes so that I can evaluate whether the pilot should be refined, expanded or discontinued.

**Related requirements:** FR-10, FR-11, BR-02, BR-03, NFR-05

**Priority:** Must Have

### Acceptance criteria

```gherkin
Scenario: Manager opens the dashboard
  Given the manager is authorised to access pilot reporting
  When the dashboard is opened
  Then the agreed pilot KPIs are displayed
  And the reporting period is clearly stated

Scenario: Manager filters the results
  Given the manager is viewing the dashboard
  When a hotel, lead-time category, market segment or distribution channel is selected
  Then the displayed measures update to reflect the selection

Scenario: Dashboard figures are reconciled
  Given pilot data has been loaded
  When dashboard totals are compared with the approved source data
  Then the totals match within the agreed reconciliation tolerance

Scenario: No confirmed financial loss is available
  Given potential booking-value exposure is displayed
  When the manager reviews the measure
  Then it is labelled as a proxy
  And it is not labelled as confirmed lost revenue
```

## US-08 Control Access and Maintain Traceability

**User story**

As a compliance representative, I want access to customer-level information to be restricted and relevant activities to be recorded so that the pilot operates with appropriate accountability.

**Related requirements:** FR-12, NFR-01, NFR-02, NFR-06, NFR-10

**Priority:** Must Have

### Acceptance criteria

```gherkin
Scenario: Authorised user accesses customer-level information
  Given a user has an approved reservations role
  When the user opens an assigned booking
  Then the user can view the information required for the review

Scenario: Unauthorised user attempts access
  Given a user does not have an approved role
  When the user attempts to open customer-level booking information
  Then access is denied
  And the attempt is handled according to the approved security process

Scenario: Activity is recorded
  Given an authorised user changes a review outcome
  When the change is saved
  Then the user, time and change are recorded in the audit history

Scenario: Retention period ends
  Given information has reached the end of its approved retention period
  When the retention process runs
  Then the information is deleted or anonymised according to the approved policy
```

## Story Quality Review

The user stories should be reviewed against the INVEST principles:

| Principle | Application |
|---|---|
| Independent | Stories should be deliverable with limited unnecessary dependency where practical |
| Negotiable | Details can be refined during stakeholder and delivery-team discussions |
| Valuable | Each story connects to a defined business requirement |
| Estimable | The delivery team should be able to estimate the story after technical refinement |
| Small | Large stories may be divided further before development |
| Testable | Each story includes observable acceptance criteria |

## Status

All stories and acceptance criteria have the status **Draft for simulated stakeholder and delivery-team validation**.
