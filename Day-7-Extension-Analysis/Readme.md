# 🎯Task 07: Identify and Remove Suspicious Browser Extensions

## Date: 30 October 2025

### The Objective:
The goal was to perform a security audit of installed browser extensions to identify and remove potentially harmful software, enhancing browser security awareness.

## Tools:
| Detail | Value | Notes |
| :--- | :--- | :--- |
| Tool | Chrome Web Browser | Used to access extension details and permissions. |
| Audit Method | Permission Analysis | Focused on checking the access level requested by each extension. |
| Action Taken | Removal/Documentation | One suspicious/unused extension was removed, and the permissions of one high-risk extension were documented. |

---

## 🚩 Findings:

### 1. Analysis and Action
The audit identified 22 extensions. We executed action based on the following:

* **Target A (Risk Documentation):** The extension **Magical: Text Expander** was flagged for **Critical Permissions** (Read and change all your data on all websites & Read data you copy and paste). This demonstrates the potential for
  credential theft.
* **Target B (Action Taken):** The unused extension **AIPRM for ChatGPT** was safely **uninstalled** to reduce the overall attack surface and potential supply-chain risk.

### 2. Security Summary
Browser extensions pose a significant risk because their code runs with high privileges. Removing unused or redundant extensions is essential to maintaining a secure and high-performance browsing environment.

*(Reference: See the **(proof/)** folder for screenshots of the Critical Permissions, and the **(raw-data/)** folder for the full extension analysis log.)*

## ❓Interview Questions: Browser Security Best Practices

#### 1. How can browser extensions pose security risks?
Browser extensions pose risks by having access to highly sensitive data. They can **log keystrokes**, **inject malicious ads** or links into websites, **read your browsing history**, and **steal session cookies or passwords** if they are
poorly coded or malicious.

#### 2. What permissions should raise suspicion?
Permissions that grant access to data across **"all websites"** (read and change all data) should immediately raise suspicion, especially if the extension's function (Ex - a simple calculator) does not logically require such broad access.
Access to **"Read data you copy and paste"** is also a major red flag.

#### 3. How to safely install browser extensions?
Safely install extensions by:
1.  **Limiting Installation:** Only install extensions from the **official browser stores** (Chrome Web Store).
2.  **Checking Reviews:** Review the extension's **user reviews, ratings,** and the **developer’s reputation**.
3.  **Reviewing Permissions:** Carefully check the permissions requested and only install if they are absolutely necessary for the extension's function.

#### 4. What is extension sandboxing?
**Sandboxing** is a security measure that isolates an extension's code from the rest of the computer system and other browser tabs. This limits the damage an extension can do if it becomes compromised or malicious, as it prevents the code
from accessing unauthorized resources.

#### 5. Can extensions steal passwords?
**Yes, absolutely.** Extensions can steal passwords, either by:
1.  **Reading Form Data:** Using the **"read and change all your data"** permission to grab credentials as you type them.
2.  **Keylogging:** Recording keystrokes on login pages.

#### 6. How to update extensions securely?
Extensions should be configured to **update automatically** via the official browser store. This ensures that any security vulnerabilities found in the extension's code are patched immediately by the developer.

#### 7. Difference between extensions and plugins?
* **Extensions (Modern):** They modify the **browser's user interface and functionality** (like Ad Blockers or Grammarly). They run in a confined, modern environment (sandboxed).
* **Plugins (Old/Legacy):** They handled content the browser couldn't natively display (like Flash or Java applets). **Plugins are now mostly deprecated** due to significant security risks.

#### 8. How to report malicious extensions?
Malicious extensions should be reported immediately to the **official browser store** (Ex - Google Chrome Web Store or Firefox Add-ons site). The platform will review the extension and remove it globally if it violates security policies.

---
