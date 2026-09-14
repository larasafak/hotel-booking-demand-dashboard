# KPIs Risks and Implementation Plan

## Purpose

This document defines the proposed measurement framework, risk register and phased implementation approach for the simulated reservation-monitoring pilot.

The historical dataset provides baseline information for some cancellation measures. Operational targets would need to be agreed with stakeholders after validating current performance and implementation feasibility.

## KPI Framework

| ID | KPI | Definition | Purpose | Historical Baseline | Proposed Pilot Use |
|---|---|---|---|---:|---|
| KPI-01 | Cancellation rate | Cancelled bookings divided by total bookings | Measure the overall frequency of cancellation | 37.04% | Compare pilot bookings with an appropriate baseline or comparison group |
| KPI-02 | City Hotel cancellation rate | Cancelled City Hotel bookings divided by total City Hotel bookings | Monitor the historically higher-cancellation hotel | 41.73% | Track whether the selected intervention group changes relative to baseline |
| KPI-03 | Resort Hotel cancellation rate | Cancelled Resort Hotel bookings divided by total Resort Hotel bookings | Provide hotel-level comparison | 27.76% | Monitor separately if included in the pilot |
| KPI-04 | Long-lead cancellation rate | Cancelled bookings made more than 180 days before arrival divided by all bookings in that category | Monitor a historically high-cancellation category | 57.01% | Evaluate additional confirmation checkpoints |
| KPI-05 | Group-market-segment cancellation rate | Cancelled bookings in the Groups market segment divided by all bookings in that segment | Monitor group-booking exposure | 61.06% | Evaluate a group-specific confirmation process |
| KPI-06 | Potential booking value at risk | ADR multiplied by total booked nights for cancelled bookings | Estimate historical booking-value exposure | 16.73 million currency units | Monitor as a proxy, not confirmed financial loss |
| KPI-07 | Review completion rate | Completed staff reviews divided by bookings assigned for review | Measure operational adoption | Not available | Agree target before pilot |
| KPI-08 | Confirmation response rate | Customers responding to confirmation activity divided by customers contacted | Measure customer engagement | Not available | Establish during pilot |
| KPI-09 | Confirmation-to-completion rate | Confirmed bookings subsequently completed divided by confirmed bookings | Assess whether confirmation indicates booking stability | Not available | Establish during pilot |
| KPI-10 | Average review time | Total staff time spent on reviews divided by completed reviews | Measure staff workload and process efficiency | Not available | Compare with an agreed operational limit |
| KPI-11 | Exception rate | Bookings entering the data exception queue divided by processed bookings | Monitor data quality | Not available | Identify recurring missing or invalid information |
| KPI-12 | Customer complaint rate | Pilot-related complaints divided by customers receiving an intervention | Monitor unintended customer effects | Not available | Compare with the normal complaint rate |
| KPI-13 | False-positive review rate | Reviewed bookings that would have completed without additional action divided by all reviewed bookings | Assess unnecessary intervention | Not available | Use cautiously because the counterfactual may not be directly observable |
| KPI-14 | Forecast accuracy | Difference between forecast and realised occupancy using an agreed error measure | Assess planning value | Not available | Compare before and during the pilot |

## Measurement Principles

- Cancellation outcomes should be compared using equivalent booking periods and customer groups.
- A reduction in cancellation rate should not automatically be attributed to the pilot.
- Potential booking value at risk should not be presented as confirmed lost revenue.
- Operational, customer and financial measures should be considered together.
- A successful pilot should not reduce cancellation at the expense of unacceptable customer complaints or staff workload.
- KPI definitions, data sources, owners and reporting frequency should be approved before implementation.

## Proposed Pilot Success Criteria

The final numerical targets would be agreed during stakeholder validation. The pilot should demonstrate:

- A measurable and operationally meaningful improvement in the selected cancellation outcome.
- A high proportion of assigned reviews completed within the agreed timeframe.
- An acceptable level of additional staff workload.
- No material increase in customer complaints.
- Reliable reconciliation between the operational dashboard and source data.
- Sufficient cancellation-reason information to improve future analysis.
- Evidence that the monitoring rules are proportionate and useful.

## Risk Register

| ID | Risk | Likelihood | Impact | Mitigation | Proposed Owner |
|---|---|---|---|---|---|
| R-01 | Historical patterns may not represent current customer behaviour | High | High | Recalculate baselines using current data before implementation | Revenue Manager |
| R-02 | Correlations may be treated as confirmed causes | Medium | High | Label assumptions clearly and validate them through research and a controlled pilot | Business Analyst |
| R-03 | High-category bookings may include customers who would not cancel | High | Medium | Use human review, monitor unnecessary interventions and refine the rules | Reservations Manager |
| R-04 | Additional reminders may frustrate customers | Medium | High | Test approved communication, limit contact frequency and monitor complaints | Marketing Manager |
| R-05 | New review activities may create excessive staff workload | Medium | High | Limit pilot scope, monitor review time and set queue-volume thresholds | Reservations Manager |
| R-06 | Stricter confirmation or deposit policies may reduce booking conversion | Medium | High | Keep policy changes outside the initial pilot and test separately if approved | General Manager |
| R-07 | Booking information may be incomplete or inconsistent across channels | High | Medium | Introduce validation rules and an exception-management process | IT or System Provider |
| R-08 | Potential revenue exposure may be mistaken for financial loss | Medium | High | Use approved definitions and display the measure as a proxy | Finance Team |
| R-09 | Customer-level data may be used inappropriately | Low | High | Apply access controls, data minimisation, retention rules and compliance review | Compliance Representative |
| R-10 | Staff may not adopt the new process consistently | Medium | Medium | Involve users in design, provide training and monitor completion rates | Reservations Manager |
| R-11 | Monitoring rules may become outdated | Medium | Medium | Establish periodic rule review and version control | Revenue Manager |
| R-12 | External booking channels may not support the required data flow | Medium | Medium | Assess integration feasibility and begin with a compatible channel | IT or System Provider |
| R-13 | Dashboard figures may not reconcile with operational reports | Medium | High | Agree definitions, conduct reconciliation testing and maintain data lineage | Data or BI Owner |
| R-14 | Pilot results may be affected by seasonality or customer mix | High | Medium | Use comparable periods, segment results and document confounding factors | Business Analyst |

## Risk Scoring Approach

A live project could score each risk using:

```text
Risk score = Likelihood score × Impact score
