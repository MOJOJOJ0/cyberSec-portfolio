# Scenario

Your team wants to perform security updates on specific employee machines in the Marketing department. You’re responsible for getting information on these employee machines and will need to query the employees table. Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.

Describe your query and how it works in the Retrieve employees in Marketing section of the Apply filters to SQL queries template. 

<img width="649" alt="Screenshot 2025-04-21 at 7 47 13 PM" src="https://github.com/user-attachments/assets/d23f9bbf-9ffe-4e3c-a657-bbce3f7ea7d6" />

```sql
SELECT *  
FROM employees  
WHERE department LIKE '%Marketing%'  
  AND office LIKE 'East-%';
```

### Explanation:  
1. **Filtering by Department**:  
   The `department` column may contain variations of "Marketing" (e.g., "Marketing Team"). The `LIKE '%Marketing%'` clause matches **any department name containing "Marketing"**, ensuring all relevant sub-departments are included.  

2. **Filtering by Office Location**:  
   The `office` column includes values like `East-170` or `East-320`. The `LIKE 'East-%'` clause uses the `%` wildcard to match **any office starting with "East-"**, ensuring all offices in the East building are included.  

### How It Works:  
- **`department LIKE '%Marketing%'`** selects employees in **any Marketing-related department**.  
- **`office LIKE 'East-%'`** narrows results to employees located in the **East building**.  
- The `AND` operator ensures **both conditions must be met** for a row to be included.  

### Key Notes:  
- The `%` wildcard before and after "Marketing" accounts for potential prefixes or suffixes in department names (e.g., "Digital Marketing").  
- The `East-%` pattern explicitly targets offices in the East building, avoiding confusion with other buildings (e.g., "East" vs. "Northeast").  

This query isolates employees in the Marketing department within the East building, enabling targeted security updates.
