#🎯Day 02 Task: Phishing Email Sample Analysis
Date: 22 October 2025

# The Tasks Brief
This task involved performing a forensic-style analysis on a suspicious email impersonating a trusted organisation (UC Berkeley). The objective was to methodically
Identify and document all indicators of compromise (IOCs) and classic phishing tactics to understand the mechanism of a credential harvest attack performed by 
hackers.

#🔧 Tools and Methodology
* Sample: Internal Phishing Email (Credential Harvest Pretext).
* Analysis: Domain Deconstruction, Visual Inspection, and Logical Threat Assessment. We focus on checking whether the sender name and origin link are true or not
  at the destination.

#🎣 Phishing Indicators: Deconstructing the Attack

The email is designed to attract user trust and use details to steal login credentials. The attacker relies on mixing legitimate university details with malicious 
One's infrastructure to prove it's real.

| Indicator                | Phishing Tactic         | Finding & Technical Evidence                                                                                      |
|
| 1. Domain Spoofing       | Impersonation/Deception | Sender: `pattersje@gosiloam.com` FAILED. The email uses the malicious domain `gosiloam.com` instead of the
                                                       official `@berkeley.edu`. This proves the email did not originate from the university's authorised servers. |
| 2. Deceptive URL Payload | Credential Harvesting   | Link: `hxxps://its.fasoonline.com/.../adfs/` MALICIOUS. The URL links to `fasoonline.com`(a non-Berkeley
                                                       domain). The attacker added `/adfs/` to the path to fool the victim into thinking they are logging into the 
                                                       legitimate ADFS login page to steal their credentials and gain user privilege. |
| 3. Pretext & Urgency     | Compliance Pressure     | Body: "We are upgrading our email security... accept the new terms and conditions." This creates a false sense  
                                                       of mandatory compliance that pressures the victim to click the malicious link immediately before reading the
                                                       sender's domain.                                                                                            |
| 4. Structural Deception  | Brand Abuse             | Signature: The email uses the official "University of California, Berkeley" footer. This structural consistency 
                                                       is designed to build false trust, distracting the user from checking the suspicious sender address. |

-----> #(Reference: See the "proof/" folder for screenshots of the email structure and the sender address,| and "raw-data/" for the full message source.) <----
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
#❔Interview Questions:

#Learning of the Task:
The most significant learning from this task is that an attacker’s success relies on bypassing the human element. The email failed to pass two primary checks: 
"The Sender Check" (domain was incorrect) and "The Link Check" (the real URL did not match the trusted brand).

Q1. What is phishing?
Phishing is a cyber attack where criminals trick people into giving up sensitive information (like passwords or bank details). They do this by impersonating a 
trusted company (like a bank or IT support) through emails, texts, or calls to fool the victim and gain their false trust.

Q2. How to identify a phishing email?
Look for Red Flags like:
1. Mismatched Sender: The sender's email domain is wrong (e.g., `@amazon.net` instead of `@amazon.com`).
2. Urgency/Threat: The message creates panic (e.g., "Your account is suspended—click now!").
3. Bad Grammar: Obvious spelling or grammar mistakes.
4. Suspicious Links: The link text does not match the actual website URL when you hover over it.

Q3. What is email spoofing?
Email spoofing means faking the sender's address to make the email look like it came from someone you trust (like your CEO or a well-known company). An attacker uses
a different email server to hide their true identity, creating a false sense of security to fool the user.

Q4. Why are phishing emails dangerous?
They are dangerous because they can lead to credential theft (stealing your login details), financial fraud, malware installation, or unauthorized access. Phishing 
It is the easiest way for criminals to breach an organisation's network by tricking an authorised employee.

Q5. How can you verify the sender’s authenticity?
1. Check the Domain: Look closely at the (full email address) to ensure the domain name is the correct official one.
2. Contact Directly: If you're suspicious, (call the company) using a known, official phone number (not the one in the email).
3. Check Headers: Analyse the (email header) for (SPF or DKIM failures), which prove the sender is unauthorised.

Q6. What tools can analyse email headers?
The most common and easy-to-use tools for analysing headers are free, web-based analysers, such as the Google Admin Toolbox Messageheader tool or various online 
email security analysis websites.

Q7. What actions should be taken on suspected phishing emails?
1. Do Not Click: Never click on any links or download attachments.
2. Report: Immediately report the email to your organisation's IT or security team.
3. Delete: Delete the email from your inbox and spam folder.

Q8. How do attackers use social engineering in phishing?
Attackers use social engineering to exploit human psychology. They create emotional triggers like fear ("Account Compromised"), greed ("You've Won a Prize"), or
curiosity (a fake invoice) to manipulate the victim into ignoring their better judgment and taking immediate, irrational action that disappoints them later.
