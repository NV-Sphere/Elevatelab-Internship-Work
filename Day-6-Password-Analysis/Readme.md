# 🎯Task 06: Password Strength Analysis and Best Practices
## Date: 27 October 2025

### The Objective:
The goal was to understand what constitutes a strong password and demonstrate the principles of security by testing passwords of varying complexity against a password strength tool **(passwordmeter.com).**

## Tools:
| Detail | Value | Notes |
| :--- | :--- | :--- |
| Tool | **passwordmeter.com** | Used to calculate a numerical score (0-100) for compliance. |
| Test Method | Comparative Analysis | Three passwords (Weak, Medium, Strong) were tested to show the impact of character inclusion and length on the overall score. |
| Proof | Screenshots (3 total) | Visual evidence of the score difference for all three passwords. |

---

## Password Analysis:

### 1. Score Comparison (Focus on Impact)
This analysis shows the clear security impact of length and complexity on a password's strength score:

| Password | Type | Score | Complexity | Key Security Flaw |
| :--- | :--- | :--- | :--- | :--- |
| **A** (`password123`) | Weak | 43% | Good | **Vulnerable to Dictionary Attacks** due to simple structure. |
| **B** (`@PassWord1`) | Medium | 74% | Strong | Lacks sufficient **Length**, despite using symbols. |
| **C** (`#P@sSwOrD123`) | Strong | 100% | Very Strong | **High Entropy** achieved by mixing characters and long length. |

### 2. Best Practices Learned (Summary)
* **Length is King:** Password length is the single most important factor against brute force attacks.
* **Avoid Patterns:** Never use sequential numbers, repeated characters, or dictionary words, as tools instantly affect them.
* **Passphrases:** Use a unique, memorable, and long phrase that includes symbols and numbers to create high entropy.

*(Reference: See the **(proof/)** folder for screenshots of the score results and the **(raw-data/)** folder for the complete analytical scores and deductions.)*

---

## ❓Interview Questions:

#### 1. What makes a password strong?
A strong password is long (ideally 12+ characters) and unique, using a good mix of uppercase letters, lowercase letters, numbers, and symbols. Most importantly, it should not contain dictionary words or easily guessable personal 
information.

#### 2. What are common password attacks?
The two most common attacks are:
1.  **Brute Force:** Trying every possible combination of characters until the correct one is found.
2.  **Dictionary Attack:** Using lists of common words, phrases, and previously breached passwords to guess the target password.

#### 3. Why is password length important?
Password length is the most critical factor because it exponentially increases the number of possible combinations (the search space). This makes **brute force attacks** more complicated, requiring millions of years to crack, even for
powerful machines.

#### 4. What is a dictionary attack?
A dictionary attack is a non-random attack where the hacker attempts to guess a password by using an automated program to input words, phrases, and common patterns (like adding "123" or "!"). It succeeds when users choose predictable
passwords.

#### 5. What is multi-factor authentication?
Multi-factor authentication (MFA) is a security method that requires a user to provide **two or more verification factors** to gain access. These factors fall into three categories: something you **know** (password), something you **have**
(phone no.), and something you **are** (fingerprint/face).

#### 6. How do password managers help?
Password managers help by securely **storing and encrypting** complex passwords. They also **generate highly random and strong passwords** that are unique for every site, meaning you only have to remember one master password.

#### 7. What are passphrases?
Passphrases are **long, memorable sequences of words** (ex - "Correct!Horse!Battery!Stapler") that are easy for the user to remember but extremely difficult for a machine to guess due to their length and complexity.

#### 8. What are common mistakes in password creation?
Common mistakes include using **short passwords**, using the **same password** across multiple accounts, using personal information (names, birthdays), and using **predictable patterns** (like keyboard sequences or dictionary words).

---
