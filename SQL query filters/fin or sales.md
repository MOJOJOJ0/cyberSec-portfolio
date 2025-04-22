# Scenario

Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments. (The department of the employee is found in the department column, which contains values that include Sales and Finance.)

Describe your query and how it works in the Retrieve employees in Finance or Sales section of the Apply filters to SQL queries template. 

<img width="707" alt="Screenshot 2025-04-21 at 8 06 13 PM" src="https://github.com/user-attachments/assets/219d9ce6-3d38-4eb3-b034-dba6d8c5e1f1" />

```sql  
SELECT *  
FROM employees  
WHERE department LIKE '%Sales%'  
   OR department LIKE '%Finance%';  
```  

### Explanation:  
1. **Filtering by Department**:  
   - The `department` column contains values that include "Sales" and "Finance." The `LIKE` operator with `%` wildcards ensures variations of these department names are captured (e.g., "Sales Team," "Finance Department").  

2. **Using `OR` for Multiple Conditions**:  
   - The `OR` operator allows the query to return rows where the department contains **either** "Sales" **or** "Finance."  

### How It Works:  
- **`LIKE '%Sales%'`** matches any department name containing the substring "Sales."  
- **`LIKE '%Finance%'`** matches any department name containing the substring "Finance."  
- Combining these with `OR` ensures employees from **both departments** are included.  

### Key Notes:  
- The `%` wildcard before and after "Sales" and "Finance" accounts for prefixes or suffixes in department names (e.g., "Regional Sales," "Corporate Finance").  
- This query avoids excluding employees due to minor naming variations in the `department` column.  

This query isolates all employees in Sales or Finance, enabling targeted security updates for their machines.
