---
title: Secure Software Architecture
subject: Software Engineering
type: final
unit: Year 12
syllabus_topic: Secure Software Architecture
tags:
  - software-engineering
  - security
  - secure-software-architecture
  - hsc
  - final
  - exam-ready
  - year-12
aliases:
  - SSA
  - CIA Triad
  - Coding Securely
---

# Secure Software Architecture — HSC Final Notes

> **Year 12, Unit 7** | Designing software for security, the six security concepts, secure coding practices, testing strategies, encryption and the Australian privacy context.

---

## 1. Designing Software for Security

### 1.1 Security From the Start

> "Secure Software Architecture begins **when any software solution is proposed**. It needs to be **embedded right from the start** of the first Software Development Steps."

Security is a **non-functional requirement** "embedded **throughout** the software development lifecycle rather than **added as an afterthought**."

> **This is the single most important idea in the topic.** Almost every extended response should return to it: security designed in from step 1, not bolted on at the end.

**Why bolting security on later fails:**

- Architectural decisions made early (how data is stored, how sessions work) are **expensive or impossible** to reverse later
- Vulnerabilities discovered after release require **patching under pressure**, with users already exposed
- Retrofitted controls tend to be **inconsistent** — some paths protected, others missed

### 1.2 Benefits of Developing Secure Software

| Benefit | Detail |
|---|---|
| **Data protection** | User and organisational data is kept confidential and intact |
| **Minimising cyber attacks and vulnerabilities** | Fewer exploitable weaknesses reduces the attack surface |
| **Maintaining user trust and reputation** | A breach damages the brand far beyond the technical cost |
| **Legal and regulatory compliance** | Meets obligations under privacy legislation |
| **Lower long-term cost** | Fixing a design flaw at design time is far cheaper than after deployment |

### 1.3 The Six Fundamental Security Concepts

| Concept | Definition | Code illustration |
|---|---|---|
| **Confidentiality** | "How **secret** your data is" | Fernet **encryption** |
| **Integrity** | "How **whole** or intact your data is" | **SHA-256** hashing |
| **Availability** | "How **accessible** your data is" | **Retry** on `ConnectionError` |
| **Authentication** | "Method of **accessing** data e.g. usernames, passwords, **Two Factor Authentication (2FA)**" | Username/password check |
| **Authorisation** | "**Level of permission** to view, edit, delete data" | Role branching (`admin` / `viewer`) |
| **Accountability** | "**Level of responsibility** to view, edit, delete data" | Write `datetime` + user + action to `log.txt` |

> **The CIA triad** is the first three: **C**onfidentiality, **I**ntegrity, **A**vailability. The remaining three (Authentication, Authorisation, Accountability) are how you enforce them.

> **Confusing trio — Authentication / Authorisation / Accountability**
> **Authentication** — *who are you?* (proving identity)
> **Authorisation** — *what may you do?* (permission level)
> **Accountability** — *what did you do?* (logging and traceability)
> They run in that order: you identify, then permit, then record.

> **Confusing pair — Confidentiality vs Integrity**
> **Confidentiality** = nobody unauthorised can **read** it.
> **Integrity** = nobody unauthorised can **change** it, and you can detect if they did.
> Encryption protects confidentiality; hashing protects integrity.

### 1.4 Worked Case Studies

| Case | Concepts breached |
|---|---|
| **Instagram (November 2024)** | **Confidentiality** + **Authorisation** — a public API exposed user emails through *Broken Object Property Level Authorization* |
| **TikTok (June 2024)** | **Confidentiality** + **Integrity** — hijacked accounts allowed attackers to modify content. **Availability** and **Authorisation** were also affected |

> **How to use these in an exam**: name the specific concept(s) breached, explain the mechanism, then state which control would have prevented it.

### 1.5 Security Across the Software Development Lifecycle

| SDLC step | Security activity |
|---|---|
| **Requirements** | Capture **security requirements** alongside functional ones |
| **Specifications** | Define **security specifications** — measurable and testable |
| **Design** | Design the **security controls** into the architecture |
| **Development** | Apply secure coding practices |
| **Integration** | Verify components remain secure when combined |
| **Testing** | Test for errors **and vulnerabilities** |
| **Installation** | Deploy securely — configuration, permissions, secrets |
| **Maintenance** | **Patch vulnerabilities** as they emerge |

**Operating-system level**: "Secure software architecture aims to ensure that the operating system is secured so that **one session doesn't override another one**, nor **adversely affect memory**."

---

## 2. Developing Secure Code

### 2.1 Security by Design and Privacy by Design

| Principle | Definition |
|---|---|
| **Security by design** | "Software is designed to be **secure from the beginning** — i.e. in the **needs analysis and quality criteria** rather than as an afterthought" |
| **Privacy by design** | "Software is designed to **control who has access to what data** from the beginning" |

> **Confusing pair — Security by design vs Privacy by design**
> **Security** by design = protecting data from **attackers** (can it be broken into?).
> **Privacy** by design = controlling access by **legitimate users and the organisation itself** (should this person see this data at all? should we even collect it?).
> A system can be perfectly secure and still violate privacy by collecting far more data than it needs.

**Worked classification (from the class task):**

| Scenario | Classification |
|---|---|
| Health Records App | **Security by design** |
| School Attendance system | **Privacy by design** |
| Student Portal | **Both** |
| Online Survey Tool | **Neither / N/A** |

### 2.2 Secure Coding Practices

| Practice | What it addresses |
|---|---|
| **Memory management** | Preventing buffer overflows, memory leaks, and data persisting in memory after use |
| **Session management** | Secure session tokens, timeouts, invalidation on logout — preventing session hijacking |
| **Exception management** | Handling errors without leaking internal detail (stack traces, database structure) to the user |

> **Why exception handling is a security issue**: a raw error message can reveal the database type, table names, file paths and framework version — a roadmap for an attacker. Log the detail internally; show the user a generic message.

### 2.3 Common Vulnerabilities

| Vulnerability | Definition |
|---|---|
| **Cross-site scripting (XSS)** | "Injecting **malicious code** into an otherwise safe website. Usually done through **user input that is not sufficiently sanitised** before being processed and stored on the server" |
| **Broken authentication and session management** | Weak credentials, exposed session IDs, sessions that don't expire |
| **Invalid forwarding and redirecting** | Redirecting users to attacker-controlled destinations via unvalidated URL parameters |
| **Race conditions** | Two operations accessing the same resource simultaneously, producing an unintended result depending on timing |
| **Injection attacks** | Untrusted input executed as a command — SQL injection targets the database |

> **Sandboxing** = running code in an isolated environment with restricted access to the rest of the system, so that if it is compromised the damage is contained.

> **Confusing pair — XSS vs SQL injection**
> **XSS** injects script that runs in **another user's browser**.
> **SQL injection** injects commands that run on the **database server**.
> Both stem from the same root cause: **unsanitised user input**.

### 2.4 The Universal Defence: Input Validation and Sanitisation

| Term | Meaning |
|---|---|
| **Validation** | Checking input **conforms to expectations** — right type, length, format, range |
| **Sanitisation** | **Neutralising** dangerous content — escaping or stripping characters that could be interpreted as code |

> **Never trust user input.** Validate on the **server**, not only in the browser — client-side checks can be bypassed entirely.

### 2.5 Testing Strategies

| Strategy | Definition |
|---|---|
| **Code review** | Developers manually read each other's code looking for flaws |
| **SAST** (Static Application Security Testing) | Analyses the **source code** **without running** it |
| **DAST** (Dynamic Application Security Testing) | Tests the **running application** from the outside |
| **Vulnerability assessment** | Systematic scan identifying and ranking known weaknesses |
| **Penetration testing** | Authorised **simulated attack** to exploit weaknesses as a real attacker would |

> **Confusing pair — SAST vs DAST**
> **S**tatic = **S**ource code, application **stopped**.
> **D**ynamic = application **running**.
> SAST finds flaws early and points to the exact line; DAST finds flaws that only appear at runtime, including configuration and deployment issues.

> **Confusing pair — Vulnerability assessment vs Penetration testing**
> A **vulnerability assessment** produces a **list** of potential weaknesses (breadth).
> A **penetration test** actually **exploits** them to prove impact (depth).

### 2.6 Worked Application — the Tram Timetable System

From the class model answer:

| Requirement | Control applied |
|---|---|
| Goals | **Confidentiality, integrity, availability** |
| Access | **Authentication + Access Control + RBAC + MFA** — passwords alone are "vulnerable to **brute-force and phishing**" |
| Legal | **Australian Privacy Act 1988 + APPs** — obligation to "collect only necessary data, store it securely, and destroy it when no longer needed" |
| Design phase | A **privacy impact assessment** should be conducted during design |
| Coding | **Input validation and error handling** to prevent injection |
| Process | Code reviews, penetration tests, Agile sprints, **SAST** |

> **RBAC (Role-Based Access Control)** = permissions assigned to **roles** rather than individuals. A user gets a role (driver, scheduler, admin), and the role carries the permissions. Simpler to manage and audit than per-user permissions.

> **MFA (Multi-Factor Authentication)** = requiring two or more independent factors: something you **know** (password), something you **have** (phone, token), something you **are** (biometric). Defeats stolen-password attacks because the password alone is insufficient.

---

## 3. Cryptography and Encryption

### 3.1 Core Terms

| Term | Definition |
|---|---|
| **Cryptography** | "The art and science of making data **unreadable except to those who should be able to access it**" |
| **Encryption** | Scrambling data into unreadable **ciphertext**, decipherable only with a key |
| **Plaintext** | The readable original data |
| **Ciphertext** | The scrambled, unreadable output |
| **Privacy** | "How **secret** data is" |
| **Security** | "How **safe** data is" |
| **Vulnerability** | "A **security gap**" |
| **Session** | "A specific **instance of an app and its data in memory**" |

### 3.2 The Three Encryption Types

| Type | Key | Purpose | Example |
|---|---|---|---|
| **Hash functions** | **No key** | **Integrity** and digital signatures. Produces a fixed-length fingerprint that changes completely on a tiny input change | MD5, SHA-256 |
| **Symmetric-key** | **Same key** both ways | Fast bulk encryption. Weakness: **secure key distribution** | **AES** — "gold standard", 128-bit blocks |
| **Asymmetric / public-key** | **Public** (shareable) + **private** (secret) | Secure communication and digital signatures | RSA |

> **Hashing is one-way.** You cannot reverse a hash to recover the original. That is precisely why it is used for **password storage** and **integrity checking** — not for sending secret messages you need to read later.

### 3.3 SSL and TLS

- **SSL** (1995) encrypts data between site and user
- Replaced by **TLS**, which is more secure
- Identity is verified via a **handshake** ("like a digital signature")
- Sites using them display **HTTPS**

*The full four-stage TLS handshake is covered in [[Programming_For_The_Web]] §8.2.*

### 3.4 Digital Signatures

```
SENDER:    hash the message → encrypt the hash with the sender's PRIVATE key
RECEIVER:  decrypt with the sender's PUBLIC key → compare against own hash
           match → INTEGRITY + AUTHENTICITY confirmed
```

> **The key order is the reverse of encryption for secrecy.** To keep something **secret**, encrypt with the recipient's **public** key. To **prove it came from you**, encrypt with your own **private** key.

---

## 4. Australian Legal and Privacy Context

> **Sourcing note**: In your classroom materials, this appears only in the **SSA2 student sample answer**. The wider legislative framework below is standard HSC content — worth knowing, but **confirm with your teacher** which parts your class is accountable for.

### 4.1 From Your Class Materials

- "Data protection and privacy must comply with the **Australian Privacy Act 1988** and its **Australian Privacy Principles (APPs)**"
- "Legal obligation under the APPs to **collect only necessary data, store it securely, and destroy it when no longer needed**"
- "A **privacy impact assessment** should be conducted during the **design phase**"

### 4.2 Wider Framework (standard content — verify with your teacher)

| Element | Detail |
|---|---|
| **Privacy Act 1988 (Cth)** | The principal Commonwealth privacy legislation |
| **Australian Privacy Principles (APPs)** | 13 principles governing collection, use, disclosure, quality, security and access to personal information |
| **OAIC** | Office of the Australian Information Commissioner — the regulator |
| **Notifiable Data Breaches (NDB) scheme** | Requires notifying affected individuals and the OAIC of eligible data breaches |
| **Privacy impact assessment (PIA)** | A structured assessment of a project's privacy risks, conducted during design |

### 4.3 Data Handling Principles

| Principle | Meaning |
|---|---|
| **Data minimisation** | Collect only what is **necessary** for the stated purpose |
| **Purpose limitation** | Use data only for the purpose it was collected for |
| **Storage limitation** | **Destroy** data when it is no longer needed |
| **Least privilege** | Give each user and process the **minimum access** required to do its job |
| **Defence in depth** | Layer multiple independent controls so no single failure exposes the system |

---

## 5. Impact of Safe and Secure Software Development

### 5.1 Benefits of Collaboration

Secure development is a team activity. Collaboration improves security through:

- **Code review** catching flaws a single developer would miss
- **Shared standards** ensuring consistent handling of input, sessions and errors
- **Version control** providing traceability of who changed what and when
- **Diverse perspectives** identifying threats an individual would not anticipate

*Collaboration factors are covered in [[Object_Oriented_Programming]] §5.*

### 5.2 Safe and Secure Practices

| Area | Practice |
|---|---|
| **Data protection** | Encryption at rest and in transit; access controls; backups |
| **Security** | Authentication, authorisation, logging, patching, testing |
| **Privacy** | Data minimisation, consent, transparency, retention limits |

### 5.3 The Enterprise Benefit

Secure software protects **reputation**, avoids **regulatory penalties**, maintains **user trust**, reduces **incident response costs**, and enables the business to operate in regulated markets.

---

## 6. HSC Exam Response Structures

### Security Question Scaffold

```
1. Name the security concept   (confidentiality / integrity / availability /
                                authentication / authorisation / accountability)
2. Explain what it means
3. Give a code or real-world example
4. Link to the SDLC stage      (by design, not as an afterthought)
```

### Common Question Types

| Question type | How to answer |
|---|---|
| **"Explain why security must be designed in from the start"** | Non-functional requirement → architectural decisions are expensive to reverse → retrofitting is inconsistent → cost rises with lateness |
| **"Identify the security concepts breached in this case study"** | Name each concept → explain the specific mechanism of the breach → state the control that would have prevented it |
| **"Distinguish security by design from privacy by design"** | Security = protection from attackers; privacy = controlling legitimate access and collection → give a scenario where a system is secure but not private |
| **"Compare SAST and DAST"** | Static/source/not running vs dynamic/running → what each catches → argue for using both |
| **"Explain how XSS occurs and how to prevent it"** | Unsanitised user input stored and re-served → executes in another user's browser → prevent with validation and sanitisation, server-side |
| **"Recommend security strategies for [system]"** | Use the tram model: authentication + RBAC + MFA → input validation → encryption → testing regime → legal obligation → PIA at design |
| **"Assess the impact of secure development practices"** | Benefits (trust, compliance, lower cost) vs costs (development time, complexity) → judge |

---

## 7. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **Confidentiality** | Nobody unauthorised can **read** it | **Integrity** — nobody can **alter** it |
| **Integrity** | Data is whole and unaltered; changes detectable | Confidentiality (secrecy) |
| **Availability** | Data is **accessible** when needed | Confidentiality (restricting access) |
| **Authentication** | Proving **who you are** | **Authorisation** — what you may do |
| **Authorisation** | Your **permission level** | **Accountability** — the record of what you did |
| **Accountability** | Logging and traceability of actions | Authorisation (the permission itself) |
| **Security by design** | Protection from **attackers** | **Privacy by design** — controlling legitimate access |
| **Privacy** | About **rights** — who *should* see data | **Security** — the technical measures |
| **Vulnerability** | A security **gap** | An **exploit** (the attack using it) |
| **Threat** | A potential source of harm | A vulnerability (the weakness it targets) |
| **XSS** | Script injected, runs in another **user's browser** | **SQL injection** — runs on the **database** |
| **Race condition** | Timing-dependent conflict between operations | A logic error (deterministic) |
| **Sandboxing** | Isolating code so damage is contained | Encryption |
| **Validation** | Input **conforms** to expectations | **Sanitisation** — neutralising dangerous content |
| **SAST** | **Static** — source code, not running | **DAST** — **dynamic**, running application |
| **Vulnerability assessment** | **Lists** weaknesses (breadth) | **Penetration test** — **exploits** them (depth) |
| **Hashing** | **One-way**, no key, for integrity | **Encryption** — reversible with a key |
| **Symmetric** | One shared key; fast | **Asymmetric** — public/private pair; slow |
| **Plaintext** | Readable original | **Ciphertext** — scrambled output |
| **Digital signature** | Encrypt hash with your **private** key | Encryption for secrecy uses the **public** key |
| **SSL** | The original 1995 protocol | **TLS** — its more secure replacement |
| **RBAC** | Permissions attached to **roles** | Per-user permissions |
| **MFA** | Two or more **independent** factors | Two passwords (same factor type) |
| **Least privilege** | Minimum access needed to do the job | Convenience-based access |
| **Session** | An instance of an app and its data in memory | A login (one event that starts a session) |
| **PIA** | Structured privacy risk assessment at design | A security audit (post-build) |

---

## 8. Key Definitions Quick Reference

| Term | One-Line Definition |
|---|---|
| Secure software architecture | Designing security into software from the moment it is proposed |
| Non-functional requirement | A quality or constraint rather than a feature |
| Confidentiality | How secret the data is |
| Integrity | How whole or intact the data is |
| Availability | How accessible the data is |
| Authentication | The method of proving identity to access data |
| Authorisation | The level of permission to view, edit or delete data |
| Accountability | The level of responsibility and record of actions taken |
| CIA triad | Confidentiality, Integrity, Availability |
| Security by design | Designing software to be secure from the needs analysis onward |
| Privacy by design | Designing control of who accesses what data from the beginning |
| Memory management | Preventing overflows, leaks and residual data in memory |
| Session management | Securing session tokens, timeouts and invalidation |
| Exception management | Handling errors without leaking internal detail |
| Cross-site scripting | Injecting malicious code via unsanitised user input |
| SQL injection | Injecting commands executed by the database |
| Race condition | Timing-dependent conflict between simultaneous operations |
| Broken authentication | Weak credentials or improperly managed sessions |
| Invalid forwarding | Redirecting users via unvalidated destination parameters |
| Sandboxing | Running code in an isolated, restricted environment |
| Validation | Checking input conforms to expected type, format and range |
| Sanitisation | Neutralising input that could be interpreted as code |
| Code review | Developers manually inspecting code for flaws |
| SAST | Static analysis of source code without executing it |
| DAST | Dynamic testing of the running application |
| Vulnerability assessment | Systematic identification and ranking of weaknesses |
| Penetration testing | Authorised simulated attack to exploit weaknesses |
| Cryptography | Making data unreadable except to those authorised |
| Encryption | Scrambling plaintext into ciphertext using a key |
| Hash function | One-way keyless transformation producing a fixed-length fingerprint |
| Symmetric encryption | Same key encrypts and decrypts; fast (AES) |
| Asymmetric encryption | Public and private key pair |
| Digital signature | Hash encrypted with the sender's private key |
| SSL / TLS | Protocols encrypting traffic between site and user |
| RBAC | Access permissions assigned to roles rather than individuals |
| MFA | Authentication requiring two or more independent factors |
| Privacy Act 1988 | Principal Commonwealth privacy legislation |
| APPs | Australian Privacy Principles governing personal information |
| Privacy impact assessment | Structured assessment of privacy risks during design |
| Data minimisation | Collecting only the data necessary for the purpose |
| Least privilege | Granting the minimum access required |
| Defence in depth | Layering multiple independent security controls |

---

## 9. Quick Revision Checklist

- [ ] Explain why security is a non-functional requirement designed in from step 1
- [ ] Name and define all **six** security concepts, and identify the CIA triad within them
- [ ] Distinguish authentication / authorisation / accountability
- [ ] Give a code illustration for each of the six concepts
- [ ] Analyse the Instagram and TikTok cases by concept breached
- [ ] Map security activities across all eight SDLC steps
- [ ] Distinguish security by design from privacy by design, with a scenario
- [ ] Three secure coding practices — memory, session, exception management
- [ ] Explain XSS, SQL injection, race conditions, broken authentication, invalid forwarding
- [ ] Validation vs sanitisation, and why server-side matters
- [ ] All five testing strategies; SAST vs DAST; assessment vs pen test
- [ ] Recommend a full control set using the tram model
- [ ] RBAC and MFA — what they are and what attacks they defeat
- [ ] Three encryption types; why hashing is one-way
- [ ] Digital signature steps and the reversed key order
- [ ] Privacy Act 1988, APPs, and the three obligations from your class notes
- [ ] Data minimisation, least privilege, defence in depth

---

> **See also:** [[Programming_For_The_Web]] | [[Software_Automation]] | [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Mechatronics]] | [[MOC]]
