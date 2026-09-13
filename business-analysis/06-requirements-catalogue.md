# Requirements Catalogue

## Purpose

This catalogue defines the simulated requirements for a reservation-monitoring pilot. The requirements are based on the verified data findings, business hypotheses, gap analysis and proposed TO-BE process.

They have not been elicited from or approved by real hotel stakeholders. In a live project, each requirement would be reviewed, refined and formally validated with the relevant stakeholder.

## Requirement Types

- **Business requirements** describe the outcomes the organisation wants to achieve.
- **Functional requirements** describe what the proposed solution must do.
- **Non-functional requirements** describe how the solution must perform and the constraints it must meet.

Priority is assigned using MoSCoW:

- **Must Have:** essential for the pilot to operate safely and provide value
- **Should Have:** important but not essential for the first pilot
- **Could Have:** beneficial if time and resources permit
- **Won't Have:** excluded from the initial pilot

## Business Requirements

| ID | Requirement | Rationale | Priority | Related Gap |
|---|---|---|---|---|
| BR-01 | The organisation must establish a consistent process for identifying reservations that may require confirmation or review. | Staff need a common approach rather than relying only on individual judgement. | Must Have | GA01, GA02 |
| BR-02 | The organisation must improve operational visibility of booking cancellations and potential booking-value exposure. | Management needs timely information to support reservation and occupancy decisions. | Must Have | GA06, GA07 |
| BR-03 | The pilot must measure whether confirmation and review activities improve booking outcomes. | The organisation needs evidence before expanding or changing the process. | Must Have | GA09, GA10 |
| BR-04 | The organisation must maintain fair and proportionate treatment of customers. | Cancellation controls should not create unnecessary inconvenience or discrimination. | Must Have | GA11 |
| BR-05 | The organisation should improve the collection of cancellation reasons. | Better reason data is required to validate root-cause hypotheses. | Should Have | GA08 |
| BR-06 | The organisation should reduce avoidable manual monitoring by reservations staff. | The proposed process should improve prioritisation without creating excessive workload. | Should Have | GA02 |
| BR-07 | The organisation must establish ownership and accountability for the reservation-monitoring process. | Reservations, revenue management, finance and IT require clear responsibilities. | Must Have | GA12 |

## Functional Requirements

| ID | Requirement | Rationale | Priority | Related Business Requirement |
|---|---|---|---|---|
| FR-01 | The solution shall validate that the required booking information is available before applying monitoring rules. | Incomplete data may produce unreliable operational decisions. | Must Have | BR-01 |
| FR-02 | The solution shall route bookings with missing required information to an exception queue. | Staff need a controlled method for reviewing incomplete records. | Must Have | BR-01 |
| FR-03 | The solution shall apply stakeholder-approved monitoring rules to eligible bookings. | Bookings must be assessed consistently during the pilot. | Must Have | BR-01 |
| FR-04 | The solution shall assign each eligible booking to a low, medium or high operational review category. | Different bookings may require different levels of confirmation activity. | Must Have | BR-01 |
| FR-05 | The solution shall display bookings requiring staff review in a prioritised work queue. | Reservations staff need a clear and manageable list of required actions. | Must Have | BR-06 |
| FR-06 | The solution shall schedule confirmation reminders for bookings meeting approved conditions. | Appropriate confirmation checkpoints may identify changes before cancellation. | Should Have | BR-01 |
| FR-07 | Authorised staff shall be able to record contact attempts, customer responses and review outcomes. | Pilot interventions must be traceable and measurable. | Must Have | BR-03 |
| FR-08 | The solution shall reassess a booking after a material modification. | Changes to the booking may affect the required operational action. | Should Have | BR-01 |
| FR-09 | The solution shall allow staff to record a structured cancellation reason where available. | Root-cause analysis requires better cancellation-reason information. | Should Have | BR-05 |
| FR-10 | The solution shall provide a dashboard showing agreed cancellation, intervention and booking-value measures. | Managers need timely operational visibility. | Must Have | BR-02, BR-03 |
| FR-11 | The dashboard shall allow authorised users to filter results by hotel, lead-time category, market segment and distribution channel. | Stakeholders need to investigate differences across relevant booking groups. | Should Have | BR-02 |
| FR-12 | The solution shall maintain an audit record of rule category, staff action and booking outcome. | The pilot requires traceability and evaluation. | Must Have | BR-03 |
| FR-13 | Authorised managers should be able to update configurable monitoring rules without modifying historical records. | Rules may need revision following pilot evidence. | Could Have | BR-03 |
| FR-14 | The solution shall not automatically cancel or reject a customer booking. | A human-reviewed and proportionate process is required for the pilot. | Must Have | BR-04 |

## Non-Functional Requirements

| ID | Requirement | Rationale | Priority | Proposed Measure |
|---|---|---|---|---|
| NFR-01 | Only authorised users shall be able to view customer-level booking information. | Customer information must be protected. | Must Have | Role-based access tests pass during UAT |
| NFR-02 | The solution shall use only information approved as necessary for the pilot. | The process should follow data-minimisation principles. | Must Have | Compliance review confirms approved fields |
| NFR-03 | The reason for an operational review category shall be understandable to reservations staff. | Staff must be able to interpret and act on the result. | Must Have | UAT users can identify the contributing rules |
| NFR-04 | New and materially modified bookings shall appear in the appropriate queue within an agreed operational time. | Delayed information could prevent timely action. | Must Have | Target response time agreed before UAT |
| NFR-05 | The dashboard shall display agreed operational measures without material reconciliation differences. | Management decisions require consistent reporting. | Must Have | Dashboard totals reconcile with the pilot source data |
| NFR-06 | The process shall maintain a record of relevant rule, action and outcome changes. | Pilot evaluation requires traceability. | Must Have | Audit records are available for sampled bookings |
| NFR-07 | The work queue shall be usable by reservations staff with limited additional training. | The process should not create unnecessary complexity. | Should Have | Staff complete agreed UAT tasks successfully |
| NFR-08 | Customer communications shall use clear and neutral language. | Reminders should not imply wrongdoing or disclose internal classifications. | Must Have | Marketing and compliance review approve the templates |
| NFR-09 | The solution should remain available during agreed reservation operating hours. | Staff require access when handling reservations. | Should Have | Availability target agreed with IT |
| NFR-10 | Personal information shall be retained only for an approved period. | The pilot requires clear information-retention controls. | Must Have | Retention schedule approved before implementation |

## Business Rules Requiring Validation

| ID | Proposed Rule | Status | Required Approval |
|---|---|---|---|
| RULE-01 | Bookings made more than 180 days before arrival may receive an additional confirmation checkpoint. | Proposed for pilot discussion | Reservations Manager, Revenue Manager and Compliance |
| RULE-02 | Group bookings may follow a separate review and confirmation path. | Proposed for pilot discussion | Reservations Manager and Sales or Group Bookings Owner |
| RULE-03 | Materially modified bookings may be reassessed under the monitoring rules. | Proposed for pilot discussion | Reservations Manager and IT |
| RULE-04 | Bookings with incomplete required information may enter an exception queue. | Proposed for pilot discussion | Reservations Manager and IT |
| RULE-05 | High-category bookings may require human review but shall not be cancelled automatically. | Proposed for pilot discussion | General Manager, Reservations Manager and Compliance |

## Requirements Excluded from the Initial Pilot

The initial pilot will not include:

- Automatic booking cancellation or rejection
- Automatic changes to deposits or cancellation fees
- Dynamic customer pricing
- A production machine-learning prediction model
- Replacement of the property-management system
- Fully automated customer decision-making
- Use of sensitive personal information
- Organisation-wide deployment before pilot evaluation

## Requirements Validation Approach

In a live project, the requirements would be validated through:

1. A review workshop with the General Manager and Reservations Manager.
2. Operational review with reservations staff.
3. KPI and financial-definition review with revenue management and finance.
4. Technical feasibility assessment with IT or the system provider.
5. Privacy and customer-communication review with compliance and marketing.
6. Final prioritisation and scope approval by the project sponsor.

## Requirements Status

All requirements in this catalogue have the status **Draft for simulated stakeholder validation**.
