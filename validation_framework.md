# Architecture Overview

```text
Raw flight + weather inputs
        |
        v
ETL pipeline: extract, clean, transform, validate
        |
        v
PostgreSQL database
        |
        +--> Dimension tables: airport, date_month
        +--> Fact table: flight_monthly_performance
        +--> Weather table: weather_daily
        |
        v
Reporting view: vw_monthly_flight_weather_summary
        |
        v
Dash analytics application
        |
        v
Executive insights: KPIs, trend charts, weather relationship, data table
```

## Design Decisions
- PostgreSQL is used as the durable storage layer.
- SQL views simplify dashboard queries and keep visualization logic separate from data modeling.
- Dash/Plotly provides interactive filtering, KPI cards, and tabbed dashboard sections.
- Validation scripts run before dashboard use so incorrect percentages, null keys, or missing reporting columns can be caught early.
