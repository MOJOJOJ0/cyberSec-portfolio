# Scenario
Your team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. Use filters in SQL to create a query which identifies all employees not in the IT department. (The department of the employee is found in the department column, which contains values that include Information Technology.)

Describe your query and how it works in the Retrieve all employees not in IT section of the Apply filters to SQL queries template. 

<img width="707" alt="Screenshot 2025-04-21 at 8 15 38 PM" src="https://github.com/user-attachments/assets/281c4f00-1ed7-422d-b745-617de5db7011" />

To retrieve all employees **not in the IT department** (where the department name includes "Information Technology"), use the following SQL query:  

```sql  
SELECT *  
FROM employees  
WHERE department NOT LIKE '%Information Technology%';  
```  

### Explanation:  
1. **Excluding the IT Department**:  
   The `department` column may contain values like "Information Technology" or "IT Department." The `NOT LIKE` operator ensures **any department name containing "Information Technology"** is excluded.  

2. **Wildcard Usage**:  
   The `%` wildcard before and after `Information Technology` matches **any text** before or after the phrase, covering variations like "Information Technology Team" or "Global Information Technology."  

### How It Works:  
- **`department NOT LIKE '%Information Technology%'`** filters out employees whose department name includes the substring "Information Technology."  
- **`SELECT *`** returns all columns for employees in **all other departments**, ensuring they receive the required update.  

### Key Notes:  
- This query accounts for potential variations in how the IT department might be named in the `department` column.  
- The `%` wildcard ensures flexibility, preventing accidental inclusion of IT-related departments.  

This query isolates employees outside the IT department, streamlining the security update process.
