# Validation Framework

The validation framework checks the data before it is used in the dashboard.

## Checks Included
1. Required columns exist in the reporting view.
2. Month numbers fall between 1 and 12.
3. Percentage fields are between 0 and 100.
4. Flight operation counts are non-negative.
5. Delay, cancellation, and diversion counts are non-negative.
6. At least one record is returned from the reporting view.

## Failure Handling
Validation errors are logged to `logs/pipeline.log`. Critical failures should stop dashboard refresh until data is corrected.

## Production Recommendation
In production, validation should run after every ETL load and before dashboard refresh. A failed validation should trigger an alert to the data owner and keep the prior validated reporting table available for users.
