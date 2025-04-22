# Scenario: 
You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the log_in_attempts table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the login_time column. The success column contains a value of 0 when a login attempt failed; you can use either a value of 0 or FALSE in your query to identify failed login attempts.)

Describe your query and how it works in the Retrieve after hours failed login attempts section of the Apply filters to SQL queries template. 

---
<img width="706" alt="Screenshot 2025-04-18 at 5 26 28 PM" src="https://github.com/user-attachments/assets/0f652049-8f0f-4a1a-bade-aa791320c4f4" />

```sql
SELECT *
FROM log_in_attempts
WHERE login_time >= '18:00' AND success = 0;
```

## Explanation:
1. Filtering Failed Attempts:
The `success` column is set to `0` for failed login attempts. The condition `success = 0` isolates these failed attempts.

2. Time-Based Filtering:
The `login_time >= 18` clause extracts the hour from the `login_time` column and checks if it is 18 (6:00 PM) or later. This ensures only login attempts occurring after business hours (18:00) are included.

## How It Works:
- `success = 0` ensures only failed login attempts are selected.

- `login_time >= 18` filters logins that occurred after 18:00 (6:00 PM).

- The `SELECT *` returns all columns for the identified records, enabling a comprehensive review of after-hours activity.

This query efficiently combines both filters to identify security-relevant events outside normal operational hours.
