## SQL Injection using Burp Suite – Determining Number of Columns with UNION Operator  

--- 
**Name:** Adekunle A. Joseph  
**MHandler:** JK_SPINNN 
**Date:** 25th of August, 2025

---

## 🎯 Objective  
The objective of this task is to perform SQL injection testing using Burp Suite in order to determine the number of columns in a database query. This is achieved using the UNION SELECT technique based on the PortSwigger Web Security Academy lab.
![PortSwigger](web-application-security/sql-injection-lab-1/screenshots/1.png)

---

## 🧰 Tools Used  
- Burp Suite  
- Web Browser (Proxy Configured)  
- PortSwigger Web Security Academy  

---

## ⚙️ Methodology  

### Step 1: Configure Burp Suite  
- Launch Burp Suite  
- Configure browser proxy:  
  - **IP Address:** 127.0.0.1  
  - **Port:** 8080  
- Enable **Intercept ON** in Proxy tab  
![Burp Intercept](web-application-security/sql-injection-lab-1/screenshots/2.png)

---

### Step 2: Access Target Application  
- Open the lab environment  
- Identify vulnerable parameter in URL:  

```bash
id=1
```

- Select parameter as injection point  
![PortSwigger Target APP](web-application-security/sql-injection-lab-1/screenshots/3.png)

---

### Step 3: Capture Request  
- Intercept request using Burp Suite  
- Forward request  
- Send to **Repeater** for testing  
![Burp Repeater](web-application-security/sql-injection-lab-1/screenshots/4.png)


---

### Step 4: Test for SQL Injection  
- Inject basic payload:

```sql
'
```
- Application returns error  

✅ **Result:** SQL injection vulnerability confirmed  
![Burp Repeater](web-application-security/sql-injection-lab-1/screenshots/5.png)

---

### Step 5: Determine Number of Columns  

Test payloads with increasing NULL values:

```sql
' UNION SELECT NULL--
```
❌ Error  

```sql
' UNION SELECT NULL,NULL--
```
❌ Error  

```sql
' UNION SELECT NULL,NULL,NULL--
```
✅ Success  
![Basic Payload Injection](web-application-security/sql-injection-lab-1/screenshots/6.png)

---

### ✅ Conclusion  
- The query contains **3 columns**


---

### Step 6: Identify Visible Columns  

Replace NULL with string values:

```sql
' UNION SELECT 'A','B','C'--
```

### 🔍 Observation  
- **A and B** appear in response  
- **C** does not appear  

---

### ✅ Conclusion  
- The application displays **2 columns**  
- These are the **visible output columns**  
![No of Column](web-application-security/sql-injection-lab-1/screenshots/7.png)
---

## 🔬 Technical Analysis  

The UNION SELECT operator allows combining results from multiple queries.  

For successful execution:  
- Column count must match  
- Data types must be compatible  

Using NULL values helps avoid data type conflicts during testing.  

---

## ⚠️ Security Impact  

This vulnerability can allow attackers to:  

- Extract sensitive database information  
- Retrieve user credentials  
- Enumerate database structure  
- Gain unauthorized access  

---

## 🛠️ Mitigation Strategies  

- Use parameterized queries  
- Validate and sanitize all inputs  
- Disable detailed error messages  
- Implement Web Application Firewall (WAF)  
- Apply least privilege principle  

---

## 🧾 Conclusion  

This task demonstrated how SQL injection can be performed using Burp Suite.  

The UNION SELECT technique was used to:  

- Confirm SQL injection vulnerability  
- Identify number of columns (**3**)  
- Detect visible columns in the response  

This emphasizes the importance of secure coding practices in web applications.  

---

