# Bike-Sharing Demand Analysis — Portfolio Case Study

## Project summary

This project examines how bike-sharing demand changed across years, user segments, day types, hours, and weather conditions. It combines data-quality review, exploratory analysis, time-series regression, diagnostic testing, and management reporting.

The final analysis uses 731 daily observations and 17,379 hourly observations covering January 2011 through December 2012.

## Business problem

Bike-sharing demand is not distributed evenly across the calendar or the day. A single operating schedule can miss important differences between registered and casual users, working and non-working days, and favorable and adverse weather conditions.

The analysis was designed to answer five practical questions:

1. How did demand change between 2011 and 2012?
2. Which user segment contributed most to the increase?
3. When did casual and registered users generate their highest demand?
4. How did demand differ across day types and weather conditions?
5. Which operating priorities were supported by the evidence?

## What I did

- Audited the daily and hourly datasets for missing values, duplicates, invalid categories, inconsistent counts, date coverage, and cross-file agreement
- Preserved the original source files and created separate validated clean datasets
- Investigated annual, monthly, weekday, hourly, user-segment, day-type, and weather patterns
- Reproduced the total-demand OLS baseline in Python after estimating it in JMP
- Tested daily and weekly autoregressive error structures
- Selected separate preferred models for total, casual-user, and registered-user demand
- Reviewed residual autocorrelation using Durbin–Watson and Ljung–Box diagnostics
- Created six management-focused figures and a 48-page management report

## Main findings

- Average daily rentals were **64.4% higher in 2012** than in 2011.
- Registered users accounted for **84.5% of the observed increase**.
- Registered-user demand was concentrated around **08:00 and 17:00**.
- Casual-user demand followed a broader daytime pattern and peaked at **14:00**.
- Average weekend casual demand was **124.3% higher** than the Monday-to-Friday average.
- Registered users represented **86.8% of working-day rentals**.
- Average demand under light rain or snow was approximately **63.0% lower** than under clear or partly cloudy conditions, although the adverse-weather sample was limited.

## Management implications

The analysis supports different operating templates for:

- Working and non-working days
- Registered and casual users
- Morning, midday, and evening demand windows
- Favorable and adverse weather conditions

The results identify when operating attention is most important, but they do not determine how many bicycles should be moved or which stations require intervention. Those decisions would require station-level inventory, dock availability, origin-destination, stockout, cost, and unmet-demand data.

## Data-quality decisions

Two issues were formally documented:

- 165 expected date-hour combinations were absent across 76 dates
- Humidity was recorded as zero on March 10, 2011

The original records were retained rather than imputed. Sensitivity checks showed that the main casual, registered, and total peak hours were unchanged when the hourly analysis was restricted to complete 24-hour dates.

## Tools

- Python
- Jupyter Notebook
- pandas
- NumPy
- statsmodels
- matplotlib
- JMP Pro 17
- Microsoft Word

## Selected outputs

### Annual demand growth and user-segment contribution

![Annual demand growth and segment contribution](../04_outputs/figures/presentation/01_annual_growth_and_segment_contribution.png)

### Hourly demand profiles

![Hourly demand profiles](../04_outputs/figures/presentation/03_hourly_segment_profiles.png)

### Demand by weather condition

![Demand by weather condition](../04_outputs/figures/presentation/06_demand_by_weather_condition.png)

## Project deliverables

- [Management report — PDF](../05_reports/bike_sharing_management_report.pdf)
- [Management report — DOCX](../05_reports/bike_sharing_management_report.docx)
- [Project README](../README.md)
- Python notebooks
- JMP reports
- Structured CSV outputs
- Data-quality and model diagnostics

## Limitations

The data cover only two years and are observational. The models estimate adjusted historical associations, not causal effects or validated forecasts. The available records are aggregated at the system level and do not contain the station-level information needed for routing, rebalancing quantities, or investment decisions.

## Author

**Fatemeh Kamrani**
