# Project Proposal: CVG Flight Delays & Weather Analytics

## Business Problem
Cincinnati/Northern Kentucky International Airport (CVG) operations teams need a repeatable way to understand how monthly flight performance changes over time and whether weather conditions align with delay, cancellation, and diversion patterns. Manual review of BTS flight tables and weather observations is slow, hard to reproduce, and difficult to communicate to non-technical stakeholders.

## Project Objective
Build an end-to-end data engineering pipeline that loads flight performance and weather data into PostgreSQL, validates core metrics, and serves an executive dashboard through Plotly Dash.

## Business Questions
1. Which months have the lowest on-time arrival rates?
2. Which months have the highest arrival delay percentages?
3. How do delays, cancellations, and diversions vary by month and season?
4. Do precipitation and severe weather indicators align with increased disruptions?
5. What operational KPIs summarize performance for a selected period?

## Expected Value
The project creates one reusable source of truth for CVG flight and weather performance, reduces manual reporting effort, and gives stakeholders an interactive dashboard for identifying seasonal disruption patterns and operational risk.
