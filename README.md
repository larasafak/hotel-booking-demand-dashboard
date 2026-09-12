# Hotel Booking Demand and Cancellation Dashboard

## Overview

This project uses Tableau to analyse 119,390 bookings from a city hotel and a resort hotel in Portugal. The dashboard examines booking demand, cancellation behaviour, potential revenue exposure, and the customer and booking characteristics associated with higher cancellation rates.

The analysis is organised as a five-part decision story: the business situation, demand patterns, cancellation risk, estimated financial exposure, and recommended actions for hotel managers.

## Business Questions

- How does booking demand vary by hotel, month, market segment, distribution channel, and guest country?
- Which booking characteristics are associated with higher cancellation rates?
- How much potential booking value is linked to cancelled reservations?
- Which customer segments should hotel managers prioritise when designing cancellation controls?

## Dashboard Structure

| Dashboard | Purpose |
|---|---|
| **The Situation** | Introduces the business context, dataset, methodology, and research questions. |
| **The Demand** | Explores booking volume by month, hotel, market segment, distribution channel, and guest country. |
| **The Risk** | Compares cancellation rates by hotel, lead time, and selectable booking characteristics. |
| **The Cost** | Estimates realised booking value and potential revenue at risk from cancellations. |
| **The Action** | Summarises priority segments, recommendations, limitations, and possible improvements. |

## Key Findings

- The dataset contains **119,390 bookings**, of which **44,224 were cancelled** and **75,166 were completed**.
- The overall cancellation rate was **37.04%**.
- The City Hotel had a higher cancellation rate than the Resort Hotel: **41.73% compared with 27.76%**.
- Cancellation risk increased with lead time. Bookings made more than 180 days in advance had a **57.01%** cancellation rate, compared with **9.63%** for bookings made within seven days of arrival.
- Group bookings had a cancellation rate of **61.06%**, while direct bookings had a rate of **15.34%**.
- Bookings with no special requests had a **47.72%** cancellation rate. Bookings with one or more requests had substantially lower rates.
- The dashboard estimates **16.73 million** in potential booking value at risk and **26.00 million** in realised booking value, measured in the dataset's currency units.

These results describe patterns in the historical data and should not be interpreted as causal effects.

## Business Recommendations

1. Apply stricter confirmation or deposit policies to bookings with long lead times, particularly those made more than 180 days before arrival.
2. Review group-booking terms because this segment combines meaningful booking volume with the highest major-segment cancellation rate.
3. Monitor City Hotel bookings more closely because their cancellation rate is approximately 14 percentage points higher than the Resort Hotel rate.
4. Use special requests and booking engagement as supporting indicators when prioritising reservations for follow-up.
5. Track potential revenue exposure alongside cancellation rates so that operational attention reflects both probability and booking value.

## Data Preparation

The cleaned dataset retains all 119,390 source rows and adds four fields used for validation and analysis:

- `Guest Count Check`: total adults, children, and babies on the booking
- `Arrival Date`: a complete date created from the arrival year, month, and day fields
- `ADR Validity`: classification of valid, invalid, and extreme average daily rates
- `Total Nights Check`: total weekend and weekday nights

The Tableau workbook also contains calculated fields for cancellation bands, lead-time segments, estimated booking value, realised booking value, potential revenue at risk, room assignment changes, family type, and special-request categories.

## Revenue Measure

The financial figures are analytical proxies:

```text
Estimated booking value = ADR x total booked nights
Potential revenue at risk = estimated booking value for cancelled bookings
Realised booking value = estimated booking value for non-cancelled bookings
```

Potential revenue at risk should not be interpreted as confirmed lost revenue. It does not account for deposits, cancellation charges, replacement bookings, refunds, ancillary spending, operating costs, or room inventory recovered after cancellation.

## Repository Structure

```text
hotel-booking-demand-dashboard/
├── README.md
├── hotel_booking_dashboard.twbx
├── dashboard_preview.png              # recommended
└── data/                              # optional
    ├── hotel_bookings_raw_data.csv
    └── hotel_bookings_clean_data.csv
```

The packaged Tableau workbook already contains the cleaned data. The separate CSV files are therefore optional and should only be included when readers need to inspect the data preparation.

## How to View the Dashboard

1. Download `hotel_booking_dashboard.twbx`.
2. Open it using Tableau Desktop or Tableau Reader.
3. Use the dashboard navigation buttons and filters to move between the five analytical views.

A Tableau Public link can also be added here after publication.

## Limitations

- The data covers arrivals between July 2015 and August 2017 and may not represent current hotel demand.
- The two hotels are anonymised, so the findings should not be generalised to every hotel market.
- Missing values are concentrated in the `company`, `agent`, and `country` fields.
- The dataset contains repeated combinations of booking characteristics but does not include a unique booking identifier, so apparently duplicated rows cannot automatically be treated as data errors.
- The dashboard identifies associations rather than causal relationships.
- Revenue measures are proxies rather than audited financial outcomes.

## Tools

Tableau, calculated fields, dashboard actions, parameters, filters, data validation, and exploratory data analysis.

## Data Source and Licence

The project uses the **Hotel Booking Demand** datasets published by Nuno Antonio, Ana de Almeida, and Luis Nunes:

> Antonio, N., de Almeida, A., & Nunes, L. (2019). Hotel booking demand datasets. *Data in Brief, 22*, 41-49. https://doi.org/10.1016/j.dib.2018.11.126

The source article and data are available under the [Creative Commons Attribution 4.0 licence](https://creativecommons.org/licenses/by/4.0/). The original publication states that hotel and customer identification fields were removed.

## Author

Lara Gunseli Safak
