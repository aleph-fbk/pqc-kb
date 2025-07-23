---
date: '2025-07-10T15:53:25+02:00'
draft: true
title: 'Management Process'
math: true
weight: 500
---


# Introduction

The transition to post-quantum cryptography (PQC) is not solely a technical upgrade, but an organizational transformation that intersects compliance obligations, governance structures, resource allocation, and technological design. 


> _Having trouble navigating your PQC migration_? 
>   
> **You're not alone**.


Here are some common challenges organizations are reporting:
 
❓ You're not sure whether your encryption is “compliant” or “state-of-the-art”

🧩 Your cryptographic tools are embedded in legacy systems and hard to locate

🛠️ There's no dedicated team responsible for crypto decisions

📉 PQC is not budgeted, nor prioritized in procurement

🔗 You’re waiting for clearer national guidance (that doesn’t exist yet)

---

## 1. Compliance Requirements

Organizations, particularly those in regulated or critical sectors, face increasing legal obligations regarding cryptographic security. The GDPR (Article 32) requires encryption “appropriate to the risk”, while the NIS2 Directive (Art. 21) mandates state-of-the-art cybersecurity measures, including encryption, for essential and important entities.

Italy transposed NIS2 through Legislative Decree 138/2024, but no national implementation roadmap or algorithm-specific guidelines have yet been issued. As a result, many entities struggle to identify what constitutes “compliant” post-quantum migration timing or method.

---

## 2. Governance Fragmentation

The EU has not yet provided high-level coordination, Italy lacks a dedicated body to lead PQC implementation.

Multiple actors (such as ACN, AgID, CSIRT, Banca d’Italia) hold partial responsibility, but no central authority provides structured support or monitoring. This multilevel fragmentation contributes to uncertainty and inaction.

---
## 3. Organizational Resource Gaps

Even when legal awareness exists, organizations face internal barriers:

- Absence of cryptographic inventory systems
- Lack of internal cryptography expertise
- PQC not included in budgeting or procurement
- Fragmented decision-making between IT, legal, security, and compliance units

SMEs are especially vulnerable, often lacking the maturity or tools to engage with PQC transition independently.

---

## 4. Technological Constraints

Many infrastructures are tightly coupled with outdated cryptographic primitives (RSA, ECC), and lack crypto-agility layers. Challenges include:

- Legacy system lock-in
- Vendor platforms that don’t yet support PQC algorithms
- Interoperability risks in hybrid deployments
- Certification dependencies that block change

