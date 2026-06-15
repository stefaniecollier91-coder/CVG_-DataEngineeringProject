# Data Source Plan

## Source 1: Flight Performance Data
- Source type: Monthly aviation performance dataset
- Grain: One row per airport-month
- Key fields: airport code, month, on-time arrivals, arrival delays, cancellations, diversions, total operations
- Purpose: Measures monthly operational performance at CVG

## Source 2: Weather Observations
- Source type: Weather observation dataset / API output
- Grain: Daily weather observations aggregated to month
- Key fields: temperature, precipitation, snowfall, wind speed, severe weather days
- Purpose: Adds context for possible weather-related disruption patterns

## Integration Plan
Flight and weather data are connected through the date/month dimension. The reporting view joins airport, date, flight performance, and weather data into `vw_monthly_flight_weather_summary`, which powers the Dash app.

## Data Quality Checks
- Required keys are present: airport code, year, month
- Percent fields are within 0–100
- Operational counts are non-negative
- Month numbers are 1–12
- Reporting view returns expected columns
