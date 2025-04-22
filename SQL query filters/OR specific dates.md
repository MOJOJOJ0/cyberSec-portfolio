# Scenario:
A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of the login attempt is found in the login_date column.)

Describe your query and how it works in the Retrieve login attempts on specific dates section of the Apply filters to SQL queries template. 

---
<img width="713" alt="Screenshot 2025-04-18 at 5 34 57 PM" src="https://github.com/user-attachments/assets/60c4c3bf-73d9-46d2-87d0-21897c828e66" />

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```

## Explanation:
1. Filtering by Dates:
The `OR` operator checks if `login_date` matches either `2022-05-08` or `2022-05-09`.

2. Explicit Conditions:
Each date is specified as a separate condition (`login_date = '2022-05-08'` and `login_date = '2022-05-09'`), linked by `OR` to include rows that satisfy either condition.

## How It Works:
- The query returns all login attempts where the date is exactly `2022-05-08` or `2022-05-09`.

- Using `OR` achieves the same result as the `IN` operator but explicitly lists each date.

## Key Difference from `IN`:
- `OR` is more flexible if you need to add additional conditions (e.g., combining dates with other filters), while `IN` is more concise for checking multiple values in a single column. Both approaches are valid here.

This query ensures all login activity during the two-day window is captured for further investigation.
