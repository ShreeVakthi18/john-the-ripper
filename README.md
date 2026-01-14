# Offline Password Risk Assessment

## Overview
This repository documents an **offline password security assessment** performed using John the Ripper in a controlled Linux environment.  
The objective is to evaluate the **risk introduced by weak password policies and fast hashing algorithms** when password hashes are exposed, simulating realistic post-breach conditions.

The focus of this project is **risk analysis and defensive insight**, not exploitation.

---

## Scope & Ethical Notice
- All password hashes used in this assessment were **self-generated**
- No real user credentials or production systems were involved
- The activity was conducted strictly for educational and defensive learning purposes
- The assessment models attacker behavior **after credential store exposure**

---

## Environment & Tools
- **Operating System:** Ubuntu Linux (WSL)
- **Primary Tool:** John the Ripper
- **Assessment Method:** Offline wordlist-based hash evaluation
- **Wordlist:** rockyou.txt

---

## Hash Information
- **Hash Type:** MD5 (md5crypt)
- **Hash Source:** Locally generated credential
- **Purpose:** Demonstrate reduced resistance of fast hashing algorithms during offline attacks

---

## Methodology
1. Generated a local password hash to simulate leaked credentials  
2. Verified hash format and integrity  
3. Performed baseline testing using incremental mode  
4. Executed an offline wordlist-based evaluation  
5. Observed recovery feasibility and attack effectiveness  

This methodology reflects real-world scenarios where attackers operate **without rate limits or authentication controls**.

---

## Results
- The plaintext password was successfully recovered from the hash
- The assessment confirmed that **weak passwords combined with fast hashing algorithms** significantly lower resistance to offline attacks

---

## Risk Impact Analysis
The successful recovery of the plaintext password demonstrates that password security must be evaluated **under the assumption of hash exposure**.

Common real-world sources of hash exposure include:
- Database breaches
- Backup leaks
- Misconfigured file permissions
- Insider threats

Once hashes are obtained, attackers can perform unrestricted offline attacks, increasing the likelihood of **credential reuse and lateral movement**.

