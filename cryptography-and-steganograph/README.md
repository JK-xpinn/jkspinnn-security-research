## Password Attacks, Complexity, and Steganography Technical Report  

---

## 👤 Researcher Details  
**Name:** Adekunle A. Joseph 
**Handler:** JK_SPINN
**Date:** September 17, 2025

---

## 🎯 Objective  
This task explains authentication-based attacks including password spraying and brute force attacks, evaluates the role of password complexity, and demonstrates steganography using Kali Linux to hide sensitive data inside image files.

---

# 🔐 PART 1: PASSWORD ATTACKS AND COMPLEXITY  

---

## 1️⃣ Short Definitions  

### Password Spraying  
An attack where a small number of common passwords are tested across many user accounts to avoid detection and account lockouts.

---

### Brute Force Attack  
An attack where many password combinations are tested rapidly against one or a few accounts until the correct password is found.

---

### Password Complexity  
Security rules that require strong passwords using combinations of uppercase, lowercase, numbers, and symbols to make guessing difficult.

---

## 2️⃣ Attack Methodologies  

### 🔹 Password Spraying Workflow  
1. Attacker gathers list of usernames  
2. Uses common passwords (e.g., Password123)  
3. Tries one password across all accounts  
4. Waits or rotates IP to avoid detection  
5. Repeats with another password  

**Flow:**  
Accounts → Password A → Wait → Password B → Compromised Accounts  

---

### 🔹 Brute Force Workflow  
1. Target a specific account  
2. Use automated tools to generate guesses  
3. Rapidly submit login attempts  
4. Continue until success or blocked  

**Flow:**  
Target Account → Many Password Attempts → Success or Block  

---

## 3️⃣ Key Differences  

| Aspect | Password Spraying | Brute Force |
|------|------------------|------------|
| Scope | Many accounts | Few accounts |
| Attempts | Few per account | Many per account |
| Detection | Low per account | High |
| Goal | Find weak passwords | Crack specific password |

---

## 4️⃣ Role of Password Complexity  

### How It Helps  
- Increases password guessing difficulty  
- Expands possible combinations  
- Reduces effectiveness of common password lists  
- Makes dictionary attacks harder  

---

### Limitations  
- Users may reuse passwords  
- Predictable patterns still occur  
- Does not stop phishing attacks  
- Can reduce usability  

---

## 5️⃣ Security Controls  

- Enforce minimum password length (12–16 characters)  
- Use multi-factor authentication (MFA)  
- Implement rate limiting  
- Monitor login behavior  
- Block breached passwords  
- Use secure password hashing (bcrypt or Argon2)  

---

# 🕵️ PART 2: STEGANOGRAPHY  

---

## 6️⃣ Definition of Steganography  

Steganography is the practice of hiding secret information inside a normal file such as an image, audio, or video so that the presence of the hidden data is not noticeable.

---

### Key Concepts  
- Hides existence of data  
- Uses carrier files (images, audio, etc.)  
- Requires key or method for extraction  

---

### Difference from Cryptography  

| Feature | Cryptography | Steganography |
|--------|-------------|--------------|
| Purpose | Hide content | Hide existence |
| Visibility | Visible but unreadable | Invisible |
| Detection | Obvious | Hard to detect |

---

# 💻 PART 3: PRACTICAL – STEGANOGRAPHY USING KALI LINUX  

---

## 7️⃣ Objective  

To embed sensitive information into three different images using Steghide and verify successful extraction.

---

## 8️⃣ Tools and Environment  

- Operating System: Kali Linux  
- Tool: Steghide  
- File Type: JPEG Images  
- Payload: Text files  

---

## 9️⃣ Step-by-Step Implementation  
![Paylod File](cryptography-and-steganograph/screenshots/1.png)

---

### Step 1: Create Payload Files  

```bash
echo "my atm password is 4567" > atm.txt
echo "my ssn is 123456789" > ssn.txt
echo "my bvn is 22413378123" > bvn.txt
```

---

### Step 2: Embed Data into Images  

```bash
steghide embed -cf image1.jpg -ef atm.txt -p pass1
steghide embed -cf image2.jpg -ef ssn.txt -p pass2
steghide embed -cf image3.jpg -ef bvn.txt -p pass3
```
![Embed](cryptography-and-steganograph/screenshots/2.png)

---

### Step 3: Verify Embedded Data  

```bash
steghide info image1.jpg
steghide info image2.jpg
steghide info image3.jpg
```

---

### Step 4: Extract Hidden Data  

```bash
steghide extract -sf image1.jpg -p pass1 -xf recovered_atm.txt
steghide extract -sf image2.jpg -p pass2 -xf recovered_ssn.txt
steghide extract -sf image3.jpg -p pass3 -xf recovered_bvn.txt
```
![Extract Embed](cryptography-and-steganograph/screenshots/3.png)

---

### Step 5: Validate Extracted Data  

```bash
cat recovered_atm.txt
cat recovered_ssn.txt
cat recovered_bvn.txt
```
![Display](cryptography-and-steganograph/screenshots/4.png)

---

## 🔍 Results and Observations  

- All data was successfully embedded into images  
- Images showed no visible changes  
- Extraction returned original data correctly  
- Passphrases ensured secure access  

---

## ⚠️ Security Implications  

### Legitimate Use  
- Digital watermarking  
- Secure communication  
- Data protection  

---

### Malicious Use  
- Hiding malware  
- Data exfiltration  
- Covert communication  

---

## 🧾 Conclusion  

This task demonstrated both theoretical and practical aspects of cybersecurity.

- Password spraying and brute force attacks exploit weak authentication systems  
- Password complexity improves security but must be combined with MFA  
- Steganography allows hidden communication within normal files  

The practical exercise using Steghide confirmed that sensitive data can be securely embedded and extracted from images without detection.

---


## 🧠 Key Takeaways  

- Weak passwords are a major security risk  
- Attackers use different strategies to bypass defenses  
- Strong authentication requires multiple layers  
- Hidden data techniques can be both useful and dangerous  

