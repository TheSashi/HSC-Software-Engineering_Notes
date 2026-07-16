---
tags: [software-engineering, hsc, final, exam-ready, year-12]
aliases: [SE Yr12 Final, Software Engineering Year 12 Notes]
cssclass: topic-notes
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 12 (Web, Software Automation, Secure Software Architecture)
created: 2026-07-15
updated: 2026-07-15
---

# Software Engineering — Year 12 (Final Exam Notes)

> Complete, self-contained revision document for HSC Software Engineering Year 12. Covers Programming for the Web, Software Automation (AI/ML), and Secure Software Architecture. Year 11 concepts that recur in Year 12 (OOP, algorithms/desk checks, security principles) are **redefined here** so this note stands alone. Built only from classroom sources — no external content. Gaps in the provided materials are flagged.

---

## A. Year 11 Foundations Redefined (recur in Year 12)

### A1. OOP recap (used in web + automation design)
- **Class:** blueprint/template for objects. **Object:** instance with its own data. **Encapsulation:** bundle data+methods, hide internals. **Inheritance:** child class gets parent's properties/methods. **Polymorphism:** different classes via common interface; same method name, different behaviour. **Abstraction:** show essentials only. **Instantiation:** create object from class.
- **Diagrams:** DFD (boxes=verb→classes/methods; arcs=noun→attributes; no actors), Structure Chart (filled circle=control flag, empty=parameter, diamond=selection), Class Diagram (3 compartments; inheritance `class Child(Parent):`).
- **Effectiveness criteria (10):** Correctness, Efficiency, Readability/Maintainability, Scalability, Robustness, Portability, Testing, Security, Documentation, Feedback & Iteration.

### A2. Algorithms & desk checks recap (used in web + automation)
- **3 control structures:** Sequence, Selection, Repetition. **Pseudocode:** `IF/ELSEIF/ELSE/ENDIF`, `WHILE/ENDWHILE`, `FOR/NEXT`, `REPEAT/UNTIL`, `PRINT`, `INPUT`.
- **Desk-check 4 rules:** (1) variables present, (2) conditions present, (3) output statements present, (4) statements in code order. (Worked examples in [[Software_Engineering_Year_11]] §2.)


### How to actually do a desk check (step by step)

A desk check is a **trace table**: you run the code by hand, one line at a time, and write down what each variable holds AFTER every line. That is the whole skill. Markers just want to see your variables tracked step by step.

**Set it up:**
- One column per variable, plus an `Output` column and a `Step` column.
- Add a **Line executed** column naming the code line each row runs. This is what makes the table easy to follow, you see the code next to its effect.
- Use `-` for not assigned yet / unknown.
- For an `INPUT` line, drop in the test value you are feeding it.
- After each line, write the NEW value of whatever that line changed.

**Exam rules to lock in:**
- Every variable gets a column, even before it is used. Unused = `-`.
- Write the value AFTER the line runs, not before.
- The condition line (`IF` / `WHILE`) gets its own step. Jot true/false in the Note column.
- When a loop finishes, show the final FALSE check too. Markers look for that.
- Feed in test data as normal / boundary / extreme. That is the validation side of it.

**Worked example — straight lines (sequence):**
```
x = 5
y = 10
x = x + y
OUTPUT x
```
<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;"><thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Step</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Line executed</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">x</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">y</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Output</th></tr></thead><tbody><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>x = 5</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">5</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>y = 10</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">5</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">10</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>x = x + y</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">15</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">10</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>OUTPUT x</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">15</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">10</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">15</td></tr></tbody></table>

Final output = 15. Note x changes twice, row 3 shows the new 15.

**Worked example — WHILE loop:**
```
total = 0
count = 1
WHILE count <= 3:
    total = total + count
    count = count + 1
OUTPUT total
```
<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;"><thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Step</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Line executed</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">total</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">count</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Output</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Note</th></tr></thead><tbody><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = 0</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">init</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">init</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE, enter loop</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">5</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">7</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">8</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">9</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">10</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">11</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">12</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">FALSE, exit loop</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">13</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>OUTPUT total</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"></td></tr></tbody></table>

Final output = 6 (that is 1+2+3). Loop ran 3 times.

**Worked example — IF / ELSE:**
```
age = 16
IF age >= 18 THEN
    status = "adult"
ELSE
    status = "minor"
OUTPUT status
```
<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;"><thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Step</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Line executed</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">age</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">status</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Output</th></tr></thead><tbody><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>age = 16</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">16</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>age &gt;= 18</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">16</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">FALSE, go ELSE</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>status = "minor"</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">16</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">minor</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr><tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>OUTPUT status</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">16</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">minor</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">minor</td></tr></tbody></table>

Output = "minor".

### A3. Security principles recap (used in web + secure architecture)
- **CIA triad:** Confidentiality (how secret data is), Integrity (how whole/intact), Availability (how accessible).
- **Authentication** (verify credentials) vs **Authorisation** (permission level). "You can have authentication without authorisation, but not authorisation without authentication."
- **Encryption types:** Hash (no key, integrity/signatures, e.g. MD5), Symmetric (same key, fast, AES), Asymmetric (public+private keys).

---

## 1. Programming for the Web

**Client vs Server:** Client = your device (HTML/CSS/JS, renders UI, handles interaction). Server = powerful computer (PHP/Python/Java/Node; stores data, processes requests, generates HTML). Full-stack = browser + server + database. Stacks: MERN/MEAN.

**Networking:** Hub (one cable, slow), Switch (many, traffic lights), Router (best path, internet), Bridge (same networks), Gateway (different networks). Topologies: star/ring/bus/hybrid/wireless. **MAC** permanent; **IP** changes. **DNS** = phone book (name→IP). **Packets** have source/dest/sequence number (packet switching reorders). Ports: HTTP 80, HTTPS 443, FTP 21, SMTP 25, DNS 53, SSH 22. Request lifecycle: URL→DNS→HTTP request→server files→browser renders (DOM/CSS/JS engine).

**Big Data — 6 V's:** velocity, volume, value, variety, veracity, variability. Data→Information→Knowledge→Understanding. Web mining: content / structure (Google ranking) / usage (logs). Social media collects location, device, contacts, history, biometrics. Ethics: privacy, security, validation, accuracy, sanitisation.

**W3C:** develops open web standards (HTML, CSS, XML, SVG, WCAG, Web APIs). Why: consistency across browsers/devices, accessibility, stability. **WAI** = accessibility tools (screen reader, magnifier, speech-to-text, sticky keys). **i18n** = multi-language/RTL support (UTF-8). Privacy (rights) vs Security (technical measures).

**Version control:** tracks file changes via commits; Git/GitHub (fork, repo, README, commit, push). Distributed (Git/GitHub) vs centralised (SVN). Open-source: code public, view/modify/share (React, Vue, Node, Django, Flask, MySQL, Linux).

**Server-side & CMS:** web server runs Python/PHP/Java; **MVC** = Model (data) / View (UI) / Controller (requests). **CMS** (WordPress, Drupal, Joomla) = website builder, easier without deep coding. Framework PMI: React (component, Virtual DOM), Angular (strong typing, enterprise), Express (minimal, Node), Django (rapid, secure, Python, ORM), Flask (lightweight), WordPress/Joomla.

**Secure web services:** **SSL/TLS** encrypt site↔user; TLS handshake agrees security settings + exchanges keys → symmetric session key. **Digital signatures:** hash message → encrypt hash with **private key** → receiver decrypts with **public key** → confirms integrity + authenticity.

**Need for standards:** without them, arbitrary syntax → no interoperability (motivates W3C).

**JavaScript algorithms:** IPO (Input-Process-Output; IPSO adds Storage). Control structures: Sequence, Selection (`if/else if/else`, operators `== < > != && ||`), Repetition (`for`, `while`). Storage: `localStorage`, `IndexedDB`, `Cache API`, `sessionStorage`.

**⚠️ Caesar cipher (Starter 2, flagged "WRITTEN WRONG"):** defines a "left shift of 3" (D→A correct) but describes it as moving "down the alphabet" (which would be forward, D→G) — contradiction; "down" should read "up/back". Uses left-shift-of-1 decryption. W3 uses the same left-shift convention.

---

## 2. Software Automation (AI/ML)

**AI vs ML:** AI = broad field (reasoning, problem-solving, perception, learning; includes rule-based, expert systems, robotics, ML). **ML = subset of AI** that learns from data without explicit programming.

**ML types:** Supervised (labeled examples), Unsupervised (finds patterns alone), Semi-Supervised (some labeled), Reinforcement (trial/error + rewards).

**Regression (SA2):**
- **Linear:** y = mx + b via Least Squares (build x|y|xy|x² table, sums, solve m, b). Worked: x=[1..5],y=[2,3,5,6,8] → **y=1.5x+0.3**.
- **Polynomial:** y = ax²+bx+c via matrix Least Squares. Worked: x=[1..5],y=[2,5,10,17,26] → **y=x²+1**.
- **Logistic:** sigmoid 0→1, yes/no; passing grade ≈3.5 at 0.5 threshold.
- **KNN:** no formula; averages K nearest points; line "not smooth."

**Neural Networks:** brain-inspired layers (Input→Hidden→Output); excel at pattern recognition (image/NLP); need lots of data; "black boxes." **Decision Trees:** split by feature rules; interpretable; can overfit. Both closed-loop in autonomous control.

**Psychology links:** Stimulus/Response/Arousal/Impulse/Regulation; "Goldilocks Zone" between impulsivity and regulation that IT exploits. Human bias (cultural, belief systems) affects ML.

**Ethics — "To what extent should software automation rule the world?":** Benefits: worker safety (hazard detection), disability access, new skills (data/AI/ethics), efficiency/less waste, productivity. Risks: job displacement, unequal wealth, fake news/manipulation (2016 election, vaccine misinformation, astroturfing), dataset/human bias. **Human oversight required** — automation bounded by judgement, not unchecked.

---

## 3. Secure Software Architecture

**Security by design:** "embedded right from the start of the first Software Development Steps," a non-functional requirement throughout the SDLC. **Privacy by design:** "control who has access to what data from the beginning."

**Six concepts (pptx):** Confidentiality, Integrity, Availability, Authentication, Authorisation, Accountability. Code examples: encryption (confidentiality), SHA-256 (integrity), retry (availability), user/pass (auth), role branching (authorisation), log file (accountability).

**SDLC with security:** Requirements (security reqs) → Specifications → Design (controls) → Dev → Integration → Testing (vulnerabilities) → Install → Maintenance (patch).

**Coding securely:** Security/Privacy by design; testing = code review, SAST, DAST, vulnerability assessment, penetration testing; practices = memory/session/exception management. Tram-model example: Auth + Access Control + RBAC + MFA; input validation/error handling to prevent injection; privacy impact assessment.

**Encryption (W3):** Hash (no key, integrity, MD5), Symmetric (AES, fast, key distribution issue), Asymmetric (public/private, signatures). **SSL/TLS:** encrypt + handshake verify identity → HTTPS.

**⚠️ Australian privacy context — HONEST GAP:** The **Australian Privacy Act 1988 + APPs** appear in ONLY ONE student sample answer (obligation to collect only necessary data, store securely, destroy when no longer needed; privacy impact assessment in design). **OAIC and the Notifiable Data Breaches scheme are ABSENT from all provided documents.** The NESA specs PDF has **NO security/privacy dot points** (only an XSS definition + "simple encryption" mention). Do NOT add OAIC/NDB/least-privilege unless your teacher supplies it.

---

## 4. Your Projects as Exam Evidence
- **D&D App (Yr12 systems report):** character manager for Ms Sheldon; problems = arithmetic errors, data vulnerability, complex point-buy (27 pts/6 scores), mobile access, session persistence. Maps to OOP + SDLC + security.
- **Wicked Problems group project (Yr11):** OOP Python solution + Systems Report (DFD/Structure/Class diagrams) + presentation.
See [[SE_Your_Projects]] (Brain) for full detail.

---

## 5. HSC Exam Response Structures

**Verb → action:** Define (meaning+qualities), Describe (features), Explain (cause/effect), Analyse (components+relationships), Justify (support), Evaluate (judgement by criteria).

**Extended-response scaffold (e.g. "To what extent should software automation rule the world?"):**
1. Define the concept (AI/ML/automation).
2. Explain the mechanism (how it learns / how it's built securely).
3. Present benefits with a concrete example (your project / a case).
4. Present risks/limits (bias, displacement, manipulation).
5. Judge "to what extent" — argue a balanced position with human oversight.

**Security question scaffold:** name the CIA aspect → explain → give code/real example → link to SDLC stage (by-design, not afterthought).

---

## 6. Quick Revision Checklist
- [ ] Client vs server; HTTP/HTTPS ports
- [ ] 6 V's of big data; W3C purpose
- [ ] Git terms; open-source examples
- [ ] MVC; CMS purpose
- [ ] TLS handshake; digital signature steps
- [ ] AI vs ML; 4 ML types
- [ ] Linear & polynomial regression worked forms
- [ ] Neural net vs decision tree
- [ ] Ethics: benefits + risks + oversight
- [ ] CIA triad; auth vs authorisation
- [ ] Security/Privacy by design; SAST/DAST/pentest
- [ ] Australian privacy GAP (only APPs in one sample; no OAIC/NDB in sources)

---

> **See also:** [[Software_Engineering_Year_11]] | [[SE_Your_Projects]]
