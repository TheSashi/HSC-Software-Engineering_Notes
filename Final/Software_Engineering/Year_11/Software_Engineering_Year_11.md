---
tags: [software-engineering, hsc, final, exam-ready, year-11]
aliases: [SE Yr11 Final, Software Engineering Year 11 Notes]
cssclass: topic-notes
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 (Programming Fundamentals, OOP, Mechatronics)
created: 2026-07-15
updated: 2026-07-15
---

# Software Engineering — Year 11 (Final Exam Notes)

> Complete, self-contained revision document for HSC Software Engineering Year 11. Covers Programming Fundamentals (SDLC, algorithms, desk checks, numbering systems, paradigms), Object-Oriented Programming, and Mechatronics. Built only from classroom sources — no external content.

---

## 1. Software Development Process (SDLC)

**Steps:** requirements definition → determining specifications → design → coding → testing → installation → maintenance → evaluation.

**Tool-to-step mapping (Logic Paradigm Starter):**
- Step 1 (Requirements): needs analysis, requirements definition, flowchart
- Step 2 (Specifications): data dictionary
- Step 3 (Design): flowchart, pseudocode, decision tree, storyboard, algorithm, DFD, structure chart, IPO chart, class diagram
- Step 4 (Coding): control structures
- Step 5 (Installation): phased / pilot / direct / parallel conversion
- Step 6 (Testing): syntax / logic / runtime errors; white / black / grey box testing
- Step 7: installation plan. Step 8: maintenance plan.

**Waterfall (5 stages, PF8):** 1 Define problem → 2 Plan & design (Gantt, context diagram, DFD, system flowchart, test plan) → 3 Implement → 4 Test & evaluate → 5 Maintain.

**Agile (PF8):** 1 Define → 2 Plan/design/implement → 3 Test & evaluate → 4 Release → 5 New requirements (stages 2–5 repeat). "Agile is iterative and flexible; Waterfall is linear and sequential. Agile more adaptable to changing requirements; Waterfall better for well-defined requirements."

**Errors:** Logic (wrong output), Syntax (breaks language rules), Runtime (only at execution).

**Installation methods:** Complete download; Partial download; Cloud-based deployment (e.g. Google Suite, no install). **Conversion:** Parallel (old+new together), Pilot (small group first), Phased (step-by-step), Direct (straight swap).

**Maintenance reasons:** changing user requirements, UI upgrades, data changes, new hardware/software, org focus, gov requirements, poor code. **Maintenance plan** includes: issue, urgency, change description, who, timeframe.

---

## 2. Algorithms & Desk Checks

**Three control structures:** Sequence, Selection, Repetition.

**Pseudocode templates (PF2):**
- `BEGIN … END` (start/end)
- `IF … THEN / ELSEIF … THEN / ELSE / ENDIF` (selection)
- `FOR I = 1 TO … / NEXT` (repetition)
- `WHILE … / ENDWHILE` (pre-test loop)
- `DO … WHILE …` (post-test loop)
- `PRINT` (output), `INPUT` / `READ` / `DISPLAY` (input/output), `LET x = 0` (process)

**Flowchart symbols:** terminator (start/stop), parallelogram (I/O), rectangle (process), diamond (decision), arrow (flow line).

### DESK CHECK RULES (PF2A Q2) — memorise
1. Variables must be there
2. Conditions must be there
3. Output statements must be there
4. Statements appear in the order they do in the code

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

### Worked Desk Check (a) — Multiplication
```
READ num1, num2
LET multi = num1*num2
DISPLAY multi
```
<table style='border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;'><thead><tr><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>num1</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>num2</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>multi</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>DISPLAY multi</th></tr></thead><tbody><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>3</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2*3 = 6</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>6</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>5</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>5*4 = 20</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>20</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>7</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>8</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>7*8 = 56</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>56</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>10</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>0</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>10*0 = 0</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>0</td></tr></tbody></table>

### Worked Desk Check (b) — IF/ELSEIF/ELSE
```
READ isfive
IF (isfive = 5)      DISPLAY "your number is 5"
ELSE IF (isfive = 6) DISPLAY "your number is 6"
ELSE                  DISPLAY "your number is not 5 or 6"
ENDIF
```
<table style='border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;'><thead><tr><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>isFive</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>isFive=5?</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>isFive=6?</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>DISPLAY</th></tr></thead><tbody><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>5</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>T</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"Your number is 5"</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>6</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>T</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"Your number is 6"</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>8</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"Your number is not 5 or 6"</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>0</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"Your number is not 5 or 6"</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>-1</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>F</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"Your number is not 5 or 6"</td></tr></tbody></table>

### Worked Desk Check (c) — WHILE loop
```
READ count
LET x = 0
WHILE (x < count)
    LET even = even + 2
    LET x = x + 1
    DISPLAY even
ENDWHILE
```
<table style='border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;'><thead><tr><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>X</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Even (before update)</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Even = even + 2</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>X = x + 1</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>DISPLAY even</th></tr></thead><tbody><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>0</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>0</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>1</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>1</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>2</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>6</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>3</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>6</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>3</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>6</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>8</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>8</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>4</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>8</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>10</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>5</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>10</td></tr></tbody></table>

**Sorting:** Bubble Sort (swaps if next value higher; source notes a buggy version where swap isn't inside the if → infinite loop). Selection Sort (uses `Swap(A,B)` subroutine).

---

## 3. Numbering Systems

**What a numbering system (a "base") is:** it is just the set of digits you are allowed to use, plus the rule that each position in a number is worth `base ^ position` (positions counted from 0 at the right). Same digits, different base, different value.

| Base | Name | Allowed digits | Why it exists |
|------|------|---------------|---------------|
| 10 | Decimal | 0–9 | The everyday system we use |
| 2 | Binary | 0, 1 | Computers are switches: 0 = off, 1 = on |
| 16 | Hexadecimal | 0–9 then A–F | Shorthand for binary (4 bits = 1 hex digit) |

**Place-value grids (the top row is what each column is worth):**

| | Col 4 | Col 3 | Col 2 | Col 1 |
|---|---|---|---|---|
| Decimal | 10³ = 1000 | 10² = 100 | 10¹ = 10 | 10⁰ = 1 |
| Binary | 2³ = 8 | 2² = 4 | 2¹ = 2 | 2⁰ = 1 |
| Hex | 16³ = 4096 | 16² = 256 | 16¹ = 16 | 16⁰ = 1 |

### Binary → Decimal (the method)
Binary is base 2, so each position from the right is worth 2⁰, 2¹, 2², 2³, … = 1, 2, 4, 8, 16, 32, 64, 128. **Only the 1-bits count** — a 0 in a column contributes nothing. So the method is: write the place value above each bit, multiply (1×value or 0×value), then add the non-zero results.

Worked `1010`:

| Bit | 1 | 0 | 1 | 0 |
|---|---|---|---|---|
| Place value | 8 | 4 | 2 | 1 |
| Bit × place | 8 | 0 | 2 | 0 |

Sum = 8 + 0 + 2 + 0 = **10**.

Second example `1101`: 8 + 4 + 0 + 1 = **13**.

### Decimal → Binary (the method)
Start from the biggest power of 2 that fits inside your number, turn that bit ON, subtract it, then repeat with what's left until you reach 0. Any power you didn't use stays OFF (0). Read the bits top-to-bottom (128 down to 1).

Worked `10`:
- Biggest power ≤ 10 is **8** (2³). 10 − 8 = 2 → bit 8 is ON.
- Biggest power ≤ 2 is **2** (2¹). 2 − 2 = 0 → bit 2 is ON.
- Bits 4 and 1 were never used → OFF.
- 8 4 2 1 = **1 0 1 0** → `1010`.

Second example `13`: 13 − 8 = 5; 5 − 4 = 1; 1 − 1 = 0 → bits 8,4,1 ON, 2 OFF → `1101`.

Powers you need (8 bits = 1 byte): 128, 64, 32, 16, 8, 4, 2, 1.

### Hex → Decimal (worked)
Each hex digit × 16^position, summed left to right.

`DEAF` = 13×4096 + 14×256 + 10×16 + 15×1 = 53248 + 3584 + 160 + 15 = **57007**.

### Decimal → Hex (worked)
Repeatedly divide by 16, keep the remainders, map 10–15 to A–F, read remainders bottom-to-top.

`999` → 999÷16 = 62 r 7; 62÷16 = 3 r 14(E); 3÷16 = 0 r 3 → read up = **3E7**.

### Binary ↔ Hex shortcut
Every 4 binary digits = exactly 1 hex digit. Memorise this row (it is the key to fast conversion):

| Dec | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Bin | 0000 | 0001 | 0010 | 0011 | 0100 | 0101 | 0110 | 0111 | 1000 | 1001 | 1010 | 1011 | 1100 | 1101 | 1110 | 1111 |
| Hex | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |

So `3AB2` → `3`=0011, `A`=1010, `B`=1011, `2`=0010 ⇒ `0011 1010 1011 0010`.

### 2s complement (how computers store negative numbers)
Computers only have 0/1, so the leftmost bit is used as a **sign** (0 = positive, 1 = negative). 2s complement is the standard method because it lets the CPU use the same addition circuit for positive and negative numbers (no separate subtractor needed).

**To find the 2s complement of a number:**
1. Write the positive value in binary.
2. Flip every bit (0↔1) — this is the 1s complement.
3. Add 1 — this gives the 2s complement.

Worked: `-14`
- `+14` = `0001110`
- Flip every bit → `1110001`
- Add 1 → `1110010`
- With the sign bit separated: `1 1110010` ✓ (matches the source answer)

Source 2s-complement answers to memorise: `-127`→`1 0000001`; `+32`→`0 0100000`; `-14`→`1 1110010`. Binary addition/subtraction are worked in the source handouts.

---

## 4. Programming Paradigms

- **Object-Oriented (PF4):** the "things in the real world" style. Class (blueprint), Object (instance), Encapsulation (bundle data+methods, hide internals), Abstraction (show essentials only), Inheritance (child gets parent's properties/methods), Polymorphism (different classes treated via common interface; same method name, different behaviour), Instantiation (create object from class), Attribute/Property (data), Method (function in class). Used when modelling distinct real-world entities (your D&D app's characters).
- **Logic (PF4):** the "facts and rules" style. Variable, Rule ("if this then that"), Facts (knowledge base), Heuristics (shortcuts), Goals, Inference Engine, Backward/Forward Chaining, Expert system. Used for expert systems / decision-making from a knowledge base.
- **Imperative/Procedural:** named in sources (COBOL example) but NOT defined — do not assume a definition.
- **Functional:** absent from provided docs.

---

## 5. Object-Oriented Programming (detail)

**Design diagrams taught:** DFD, Structure Chart, Class Diagram. (No object/sequence/state diagrams in sources.)
- **DFD:** boxes = verb phrases (→ classes/methods); arcs = noun phrases (→ attributes); no actors; symbols: process, data store, external entity, data flow.
- **Structure Chart:** filled circle = control flag; empty circle = data parameter; diamond = selection; box = function; control box = top.
- **Class Diagram:** 3 compartments (name / attributes / methods); inheritance via `class Child(Parent):`; multiplicity handled by subclassing.

**How the 4 pillars connect (this is what an exam question tests):** you bundle data + methods into a class and *hide* the internals (encapsulation), you show only what the user needs to see (abstraction), you make a child class reuse a parent's code (inheritance), and you let different child classes respond differently to the same method call (polymorphism). Encapsulation + abstraction are about *protecting/hiding*; inheritance + polymorphism are about *reusing/varying*.

**DFD → code pipeline (INO2):** Level 0 DFD name → class name; Level 1 process names → methods; data-flow items → attributes.

**Design approaches (INO3):** Top-Down (general→specific), Bottom-Up (specific→general), Façade Pattern (hides complexity behind simple interface), Agility (Design-Build-Test cycles).

**Algorithm Effectiveness Criteria (10, INO4):** Correctness, Efficiency, Readability & Maintainability, Scalability, Robustness, Portability, Testing, Security, Documentation, Feedback & Iteration.

**Collaboration factors (INO4):** Consistency (shared style), Code Commenting, Version Control (Git), Feedback.

---

## 6. Mechatronics

**Definition:** Mechanics + Electronics + Computing + Control Systems. Coined by Tetsuro Mori (Yaskawa, Japan). Benefits: efficiency, fewer errors, dangerous-task take-over. Drawbacks: job loss, cost, ethics.

**CPU vs Microcontroller (M2):** CPU = processor only, needs extra parts, general-purpose, fast, complex opcodes. Microcontroller = CPU + memory + I/O in one chip, specific/embedded tasks (e.g. Arduino). Registers: PC (next address), MAR (address accessed), ACC (operation results), CIR/IR (current instruction). **Fetch-execute:** PC→MAR→RAM→MDR→CIR→decode (opcode bits 0–3, operand 4–7)→execute→PC+1.

**Sensors/Actuators (M3):** Sensor transduces physical→electrical (PIR, accelerometer, gyroscope, ultrasonic, LDR, I2C light, joystick). Actuator converts electrical→mechanical (servos, hydraulic, gripper). Data layer: operational/diagnostic/optimisation data; feedback loop sensor→controller→actuator.

**Control algorithms (M4):** read sensors → compute toward set point → output to actuators. **Open-loop** (no feedback: TV remote, traffic light, washing-machine timing) vs **Closed-loop** (feedback: cruise control, steering, A/C, line-follower). Three closed-loop types: On/off (bang-bang), Proportional (correction ∝ error; small steady-state error), PID (integral removes error; derivative damps overshoot).

**Electricity (Starter answers):** ammeter in series, voltmeter in parallel. Putty at 25 cm, 0.15 A → **37.5 Ω**; PD = 37.5×0.15 = **5.625 V**. "thicker putty = lower resistance." Reliability: repeat + mean.

---

## 7. HSC Exam Response Structures

**Verb → what to do:**
- **Define:** state meaning + essential qualities
- **Describe:** characteristics/features
- **Explain:** cause and effect; why/how
- **Analyse:** components + relationships + implications
- **Justify:** support an argument
- **Evaluate:** judgement by criteria

**Desk-check question scaffold:** (1) Write header row with every variable, condition, output in code order. (2) Execute row-by-row. (3) For loops, one row per iteration tracking counter + changed vars.

**Paragraph scaffold (extended):** Topic sentence (define term) → explain with mechanism → apply to a scenario (your D&D app / Wicked Problems project / a given case) → link to a syllabus concept (e.g. security by design, effectiveness criterion).

---

## 8. Quick Revision Checklist
- [ ] Name the 8 SDLC steps and a tool for each
- [ ] Waterfall vs Agile difference
- [ ] 4 desk-check rules + can run one
- [ ] Pseudocode templates (IF/WHILE/FOR/REPEAT)
- [ ] Binary/hex conversion (straight substitution)
- [ ] OOP 4 pillars (encapsulation, inheritance, polymorphism, abstraction) + definitions
- [ ] DFD/Structure/Class diagram notation
- [ ] CPU vs microcontroller; fetch-execute steps
- [ ] Open vs closed loop; PID
- [ ] 10 effectiveness criteria

---

> **See also:** [[Software_Engineering_Year_12]] | [[SE_Your_Projects]]
