# Hotel Booking Cancellation Process Improvement

## Business Analysis Portfolio Case Study

This independent case study extends the accompanying Hotel Booking Demand and Cancellation Dashboard into an end-to-end business analysis exercise.

Historical analysis of 119,390 bookings identified an overall cancellation rate of 37.04%, with substantial differences across hotel types, booking lead times and market segments. The case study uses these findings to explore how a hypothetical hotel organisation could introduce a more structured reservation-monitoring process.

The numerical findings are derived from the public dataset and Tableau workbook. The stakeholder needs, current-state process, business hypotheses, requirements and proposed future-state process are simulated for portfolio purposes.

## Business Problem

The simulated organisation needs to improve its understanding and management of booking cancellations. It may lack a consistent method for identifying reservations that require confirmation, prioritising staff activity and measuring the results of interventions.

The proposed response is a limited, human-reviewed pilot using transparent monitoring rules. It does not automatically cancel bookings, impose charges or make customer-level decisions.

## Approach

The case study follows this business analysis process:

1. Define the business problem, objectives and scope.
2. Identify stakeholders and plan discovery activities.
3. Develop and validate an assumed current-state process.
4. Connect historical data findings to root-cause hypotheses.
5. Compare current and required capabilities through gap analysis.
6. Design a proposed future-state process.
7. Define and prioritise business and system requirements.
8. Translate requirements into user stories and acceptance criteria.
9. Establish KPIs, risks and an implementation plan.
10. Develop UAT scenarios and requirements traceability.

## Key Historical Findings

- The dataset contains 119,390 booking records.
- The overall cancellation rate was 37.04%.
- City Hotel cancellation rate was 41.73%, compared with 27.76% for Resort Hotel.
- Bookings made more than 180 days before arrival had a cancellation rate of 57.01%.
- Bookings in the Groups market segment had a cancellation rate of 61.06%.
- Bookings in the Direct market segment had a cancellation rate of 15.34%.
- Bookings with no special requests had a cancellation rate of 47.72%.
- Potential booking value at risk was estimated at 16.73 million currency units.

These results describe historical associations and should not be interpreted as causal effects.

## Proposed Future State

The simulated future process introduces:

- Validation of required booking information
- Transparent operational review categories
- A prioritised staff work queue
- Scheduled confirmation checkpoints
- Human review of selected reservations
- Structured cancellation-reason capture
- Operational KPI reporting
- Access control and activity traceability
- A controlled pilot before wider implementation

## Portfolio Deliverables

| Deliverable | BA Skills Demonstrated |
|---|---|
| [Project brief](01-project-brief.md) | Problem definition, objectives, scope, assumptions and constraints |
| [Stakeholder analysis](02-stakeholder-analysis.md) | Stakeholder mapping, engagement planning and conflict identification |
| [AS-IS process](03-as-is-process.md) | Current-state modelling, pain-point identification and discovery questions |
| [Findings and root-cause analysis](04-findings-and-root-cause-analysis.md) | Evidence assessment, root-cause hypotheses and assumption management |
| [Gap analysis and TO-BE process](05-gap-analysis-and-to-be-process.md) | Gap analysis, future-state modelling and solution evaluation |
| [Requirements catalogue](06-requirements-catalogue.md) | Business, functional and non-functional requirements and MoSCoW prioritisation |
| [User stories and acceptance criteria](07-user-stories-and-acceptance-criteria.md) | Agile requirements, Gherkin scenarios and requirement linkage |
| [KPIs risks and implementation](08-kpis-risks-and-implementation.md) | Performance measurement, risk management, RACI and phased delivery |
| [UAT plan](09-uat-plan.md) | Acceptance testing, defect prioritisation and requirements traceability |

## Tools and Techniques

- Tableau
- Exploratory data analysis
- Stakeholder analysis
- Power-interest assessment
- Process mapping
- Root-cause analysis
- Five Whys
- Gap analysis
- Business and system requirements
- MoSCoW prioritisation
- User stories
- Gherkin acceptance criteria
- KPI definition
- Risk register
- RACI
- UAT planning
- Requirements traceability

## Evidence Classification

The portfolio separates its content into:

- **Verified data findings:** calculated from the historical booking dataset and checked against the Tableau workbook.
- **Business hypotheses:** possible causes and pain points requiring stakeholder validation.
- **Simulated BA deliverables:** process maps, requirements, user stories, implementation proposals and UAT scenarios created to demonstrate a structured BA approach.

## Limitations

- The data covers arrivals from July 2015 to August 2017.
- No real stakeholder interviews or process observations were conducted.
- The AS-IS process is assumed rather than verified.
- The proposed solution has not been implemented or tested.
- Cancellation patterns do not establish causal effects.
- Potential booking value at risk is not confirmed financial loss.
- All requirements remain drafts for simulated stakeholder validation.

## Supporting Dashboard

The main repository contains the Tableau workbook and historical booking data supporting this case study:

- `hotel_booking_dashboard.twbx`
- `hotel_bookings_clean_data.csv`
- `hotel_bookings_raw_data.csv`

## Author

Lara Gunseli Safak
