# Evilginx3 Phishing Simulation & Session Token Analysis

## Overview
This project demonstrates a **controlled adversary-in-the-middle (AiTM) phishing
simulation** to analyze how **session token theft** can occur during modern
authentication flows — even when traditional MFA is enabled.

The objective was to understand **why MFA alone is insufficient**, how session
tokens are abused by attackers, and which **defensive controls** are most effective
at mitigating token-based account compromise.

All activity was conducted in a **private lab environment** using test accounts
and infrastructure owned by the author. No real users or production systems
were involved.

---

## Objectives
- Simulate modern phishing techniques used by real-world threat actors
- Analyze session token exposure during authentication flows
- Demonstrate limitations of traditional MFA protections
- Evaluate defensive controls against AiTM-style attacks
- Produce mitigation guidance aligned with enterprise security best practices

---

## Threat Model (High-Level)
This project focused on **session hijacking risk**, not only credential harvesting risk.

At a high level, the simulated attack scenario involved:
- A reverse-proxy phishing framework
- Legitimate authentication flows
- Interception of authenticated session tokens
- Token replay to access protected resources

> No procedural steps, configurations, or exploit details are included.

---

## Lab Environment
- Isolated cloud-based lab infrastructure
- Test tenant and test user accounts
- Controlled DNS and TLS configuration
- Reverse proxy used solely for simulation and research
- No external victims or real-world targets

---

## Key Findings
- Traditional MFA does not protect against session token theft
- Authenticated sessions can be replayed without re-prompting MFA
- Token-based access represents a critical identity security risk
- Session hijacking bypasses many perimeter-based controls
- Visibility into authentication context is essential for detection

These findings mirror **documented real-world attack campaigns** observed across
enterprise environments.

---

## Defensive Takeaways & Mitigations
Based on the simulation, the following controls were identified as effective
against token-based phishing attacks:

- Phishing-resistant MFA (FIDO2 / passkeys)
- Device-bound authentication tokens
- Conditional access policies with risk-based enforcement
- Continuous authentication and session validation

The project emphasizes **prevention and detection**, not exploitation.

---

## Security & Ethical Considerations
This project was conducted strictly for **defensive security research**.

- No real credentials or personal data were involved
- No production services were targeted
- No phishing infrastructure was left active
- All sensitive indicators and configurations are excluded

The intent of this repository is to **raise awareness and improve defenses**
against modern identity-based attacks.

---

## Limitations
- Simulated environment does not capture all enterprise identity scenarios
- Detection and logging coverage varies by identity provider
- No automated response mechanisms were implemented

---

## Future Improvements
- Integrate identity risk signals into SIEM correlation
- Explore detection of anomalous session behavior
- Evaluate token protection mechanisms across providers
- Expand mitigation testing to additional authentication models

---

## Disclaimer
This repository is for educational and defensive security research only.
The author does not condone phishing, credential harvesting, or unauthorized
access to accounts or systems.
