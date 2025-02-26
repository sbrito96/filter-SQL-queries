# Applying Filters to SQL Queries

## 📌 Project Description

An organization is working to enhance its security system. As part of my role, I must investigate potential security incidents and extract relevant data using SQL queries with filters. This project demonstrates how I used SQL queries to analyze login attempts and employee information while applying different filtering techniques.

---

## 🔍 Retrieve After-Hours Failed Login Attempts

A potential security incident occurred after business hours (after 18:00). To investigate, I filtered for failed login attempts that happened after 18:00.

### **SQL Query:**
```sql
SELECT * FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
```

![image](https://github.com/user-attachments/assets/8d98f24e-7558-4431-91f5-0470533414e6)

### **Explanation:**
- `login_time > '18:00'` → Filters for login attempts after 18:00.
- `success = FALSE` → Filters for failed login attempts.

---

## 🔍 Retrieve Login Attempts on Specific Dates

A suspicious event occurred on **2022-05-09**. I needed to retrieve login attempts on this date and the day before.

### **SQL Query:**
```sql
SELECT * FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```
![image](https://github.com/user-attachments/assets/6122d2bd-d8ff-42a0-b29f-ff6a4e71f8e9)

### **Explanation:**
- `login_date = '2022-05-09'` → Retrieves logins on May 9, 2022.
- `OR login_date = '2022-05-08'` → Also retrieves logins on May 8, 2022.

---

## 🔍 Retrieve Login Attempts Outside of Mexico

After investigating login data, I identified a potential security risk in login attempts outside of Mexico.

### **SQL Query:**
```sql
SELECT * FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```
![image](https://github.com/user-attachments/assets/d229fac7-49be-4e9c-ac33-cb0f0df2fd1d)

### **Explanation:**
- `NOT LIKE 'MEX%'` → Filters for countries other than Mexico (`MEX` or `MEXICO`).
- `%` is a wildcard that matches any additional characters.

---

## 🔍 Retrieve Employees in Marketing

To update employee computers, I needed information on employees in the **Marketing department** working in the **East building**.

### **SQL Query:**
```sql
SELECT * FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```
![image](https://github.com/user-attachments/assets/451db236-53f2-46ea-b37f-6bb5643a8846)

### **Explanation:**
- `department = 'Marketing'` → Filters for employees in Marketing.
- `office LIKE 'East%'` → Filters for employees in offices labeled "East".

---

## 🔍 Retrieve Employees in Finance or Sales

For a different security update, I needed details on employees in **Finance or Sales** departments.

### **SQL Query:**
```sql
SELECT * FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
![image](https://github.com/user-attachments/assets/5baa6811-1919-4a87-b742-54c1e9d41864)

### **Explanation:**
- `department = 'Finance'` → Retrieves Finance employees.
- `OR department = 'Sales'` → Retrieves Sales employees.

---

## 🔍 Retrieve Employees Not in IT

The final security update was for employees **not in the Information Technology (IT) department**.

### **SQL Query:**
```sql
SELECT * FROM employees
WHERE department NOT LIKE 'Information Technology';
```
![image](https://github.com/user-attachments/assets/ad6f5a15-ab22-4c26-8560-5c59b4eae7c8)

### **Explanation:**
- `NOT LIKE 'Information Technology'` → Excludes employees from IT.

---

## 📝 **Summary**

Through these SQL queries, I effectively extracted relevant data from two tables (`log_in_attempts` and `employees`). I applied:

- **AND, OR, and NOT operators** to filter results.
- **LIKE and % wildcard** for pattern matching.

This approach enhanced security monitoring and facilitated system updates, ensuring a robust security posture within the organization.







