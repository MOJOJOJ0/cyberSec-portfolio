# Scenario
There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico.

<img width="705" alt="Screenshot 2025-04-21 at 5 47 22 PM" src="https://github.com/user-attachments/assets/462bd32e-9eab-48a4-a723-28ea015dfb9f" />

To retrieve login attempts that occurred **outside of Mexico** from the `log_in_attempts` table, use the following SQL query:  

```sql  
SELECT *  
FROM log_in_attempts  
WHERE country NOT LIKE 'MEX%';  
```  

### Explanation:  
1. **Filtering Non-Mexico Entries**:  
   The `country` column may contain values like `MEX` or `MEXICO`. To exclude **all entries related to Mexico**, the `NOT LIKE` operator is used with the wildcard `%` to match any country starting with `MEX`.  

2. **Wildcard Usage**:  
   The pattern `'MEX%'` captures any value beginning with `MEX` (e.g., `MEX`, `MEXICO`, `MEX123`). The `NOT LIKE` clause ensures these values are **excluded** from the results.  

### How It Works:  
- **`country NOT LIKE 'MEX%'`** filters out all rows where the country name starts with `MEX`, effectively excluding Mexico-related entries.  
- **`SELECT *`** returns all columns for the remaining rows, which represent login attempts **originating outside Mexico**.  

### Key Notes:  
- This query accounts for variations in how Mexico might be represented (e.g., `MEX` vs. `MEXICO`).  
- The `%` wildcard ensures flexibility in matching any suffix after `MEX`.  

This query isolates login attempts of interest, helping the team focus on activity unrelated to Mexico.
