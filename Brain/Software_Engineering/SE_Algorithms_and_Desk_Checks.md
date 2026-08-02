---
tags: [software-engineering, year-11, hsc, algorithms, pseudocode, flowcharts, desk-checks, control-structures]
aliases: [SE Algorithms, Desk Checks, Pseudocode, Flowcharts, Control Structures]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Programming Fundamentals
created: 2026-07-15
updated: 2026-07-15
---

# Algorithms and Desk Checks — Year 11 SE

> Self-contained note on algorithms, the three control structures, pseudocode syntax, flowchart symbols, DFD symbols, and how to do a **desk check** (with every worked example reproduced exactly from the classroom docs). Built only from PF2, PF2(A), PF2(B), PF3, Terminology starter. No external content added.

---

## 1. What an algorithm is

"An algorithm [is] a step-by-step procedure or set of rules to solve a problem or accomplish a task. In programming, algorithms are expressed in code to instruct a computer to perform specific operations." [Terminology starter]

Algorithms are associated with **Step 3 (Design)** of the software development process. [Logic Paradigm Starter]

---

## 2. The three control structures

1. **Sequence** — steps in order, one after another.
2. **Selection** — a choice (IF/ELSE).
3. **Repetition** — steps repeated (loops).

[PF2 / PF2(B)]

---

## 3. Pseudocode keywords and templates (exact, from PF2)

<table style='border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;'><thead><tr><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Pseudocode</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Meaning</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Control structure</th></tr></thead><tbody><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`BEGIN … END`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Start and end</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>—</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`IF … THEN` / `ELSEIF … THEN` / `ELSE` / `ENDIF`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Binary and multiway selection</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Selection</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`FOR I = 1 TO …` / `NEXT`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>For loop</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Repetition</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`PRINT`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Display output</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>—</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`INPUT`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Get input</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>—</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`WHILE …` / `ENDWHILE`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>While loop (pre-test loop)</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Repetition</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>`DO` / `WHILE …`</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Do–While loop (post-test loop)</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Repetition</td></tr></tbody></table>

Additional forms (PF2(B)):
- `REPEAT … UNTIL …` → process symbol (post-test loop)
- `DISPLAY …` / `READ …` → input/output symbol
- `LET n = 0` → process symbol
- `BEGIN … END` → "terminator start and stop"
- `IF … THEN … ELSE … ENDIF` → decision diamond

### Worked pre-test (While) loop [PF2]
```
BEGIN
Count = 1
WHILE Count < 4
    Input number
    Print number
    Count = Count + 1
ENDWHILE
END
```

### Worked post-test (Repeat) loop [PF2]
```
REPEAT
    process(es)
UNTIL condition is true
```

### Worked array algorithms (PF3)
- **Load array:**
```
BEGIN LoadArray
Let i = 1
Let Element() be an array
Read DataValue
WHILE DataValue <> "xxx"
    Let Element(i) = DataValue
    i = i + 1
    Read DataValue
ENDWHILE
Let NumElements = i
Display " There are" NumElements " items loaded into the array"
END LoadArray
```
- **Print array:** `REPEAT Display Element(i); i = i + 1; UNTIL i >= NumElements`
- **Sum array:** `REPEAT total = Element(i) + total; i = i + 1; UNTIL i > NumElements`

---

## 4. Flowchart symbols (PF2(B))

<table style='border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;'><thead><tr><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Symbol</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Name</th><th style='border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;'>Meaning</th></tr></thead><tbody><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>---</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Oval</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>terminator</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>start/stop</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Parallelogram</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>input and output</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>input/output</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Rectangle</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>process</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>a process step</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Diamond</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>decision</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"used for if statements usually"</td></tr><tr><td style='border:1px solid #bdc1c6;padding:6px 10px;'>Arrow</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>flow line</td><td style='border:1px solid #bdc1c6;padding:6px 10px;'>"used to connect all the flowcharts"</td></tr></tbody></table>

---

## 5. Data Flow Diagram (DFD) symbols (PF2(B))

- **External Entity** — "People or groups of people using the system."
- **process** — a process node (transforms data).
- **flowline** — connecting the flowchart/data flow together.

For OOP design, DFD boxes are verb phrases (become classes/methods) and arcs are noun phrases (become attributes). See [[SE_Object_Oriented_Programming]].

Terminology-starter definitions:
- "Data Flow Diagram Level 0 — A diagram which shows the relation of which data has with processes within the program."
- "Flowchart — A diagram of which showcases the flow of data within a program."
- "Pseudocode — A detailed yet readable description of what a computer program/algorithm should do."
- "Structure chart — A visual representation of the relationships between parts of a system."

---

## 6. Sorting algorithms seen (PF2)

- **Bubble Sort** (the "mystery algorithm"): "swaps the numbers if the next value is higher than the last." Note from source: a student answer pointed out the given version is buggy — "the algorithm is wrong as an infinite loop is seen as the swap statement is not inside the if loop."
- **Selection Sort** (PF2 Q6): `BEGIN SelectionSort … Swap(Name(PosMax), Name(EndUnsorted)) …` with a `Swap(A,B)` subroutine.

---

## 7. DESK CHECKS — the rules and worked examples

### The 4 rules (exact, from PF2(A) Q2)

"Remember the following rules for desk checks in the header row:
1. Variables must be there
2. Conditions must be there
3. Output statements must be there
4. Statements have to appear in the order they do in the code."

### How to actually do a desk check (step by step)

A desk check is a **trace table**: you run the code by hand, one line at a time, and write down what each variable holds AFTER every line. That is the whole skill. Markers just want to see your variables tracked step by step.

**Set it up:**
- One column per variable, plus an `OUTPUT` column and a `STEP` column.
- Use `-` for not assigned yet / unknown.
- For an `INPUT` line, drop in the test value you are feeding it.
- After each line, write the NEW value of whatever that line changed.

**Exam rules to lock in:**
- Every variable gets a column, even before it is used. Unused = `-`.
- Write the value AFTER the line runs, not before.
- The condition line (`IF` / `WHILE`) gets its own step. Jot true/false next to it.
- When a loop finishes, show the final FALSE check too. Markers look for that.
- Feed in test data as normal / boundary / extreme. That is the validation side of it.

**Worked example — straight lines (sequence):**
```
x = 5
y = 10
x = x + y
OUTPUT x
```
| STEP | x | y | OUTPUT |
|---|---|---|---|
| 1 | - | - | - |
| 2 | 5 | - | - |
| 3 | 5 | 10 | - |
| 4 | 15 | 10 | - |
| 5 | 15 | 10 | 15 |

Final output = 15. Note x changes twice; row 4 shows the new 15.

**Worked example — WHILE loop:**
```
total = 0
count = 1
WHILE count <= 3:
    total = total + count
    count = count + 1
OUTPUT total
```
| STEP | total | count | OUTPUT | note |
|---|---|---|---|---|
| 1 | 0 | - | - | init |
| 2 | 0 | 1 | - | init |
| 3 | 0 | 1 | - | check 1<=3 TRUE |
| 4 | 1 | 1 | - | total = 0+1 |
| 5 | 1 | 2 | - | count = 2 |
| 6 | 1 | 2 | - | check 2<=3 TRUE |
| 7 | 3 | 2 | - | total = 1+2 |
| 8 | 3 | 3 | - | count = 3 |
| 9 | 3 | 3 | - | check 3<=3 TRUE |
| 10 | 6 | 3 | - | total = 3+3 |
| 11 | 6 | 4 | - | count = 4 |
| 12 | 6 | 4 | - | check 4<=3 FALSE, exit |
| 13 | 6 | 4 | 6 | output |

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
| STEP | age | status | OUTPUT |
|---|---|---|---|
| 1 | 16 | - | - |
| 2 | 16 | - | (16>=18? false, go ELSE) |
| 3 | 16 | minor | - |
| 4 | 16 | minor | minor |

Output = "minor".

### Worked Desk Check (a) — Multiplication (Sequence)

Pseudocode:
```
READ num1, num2
LET multi = num1*num2
DISPLAY multi
```

| num1 | num2 | multi | DISPLAY multi |
|---|---|---|---|
| 2 | 3 | 2*3 = 6 | 6 |
| 5 | 4 | 5*4 = 20 | 20 |
| 7 | 8 | 7*8 = 56 | 56 |
| 10 | 0 | 10*0 = 0 | 0 |

### Worked Desk Check (b) — IF / ELSEIF / ELSE (Selection)

Pseudocode:
```
READ isfive
IF (isfive = 5)      DISPLAY "your number is 5"
ELSE IF (isfive = 6) DISPLAY "your number is 6"
ELSE                  DISPLAY "your number is not 5 or 6"
ENDIF
```

| isFive | isFive=5? | isFive=6? | DISPLAY |
|---|---|---|---|
| 5 | T | F | "Your number is 5" |
| 6 | F | T | "Your number is 6" |
| 8 | F | F | "Your number is not 5 or 6" |
| 0 | F | F | "Your number is not 5 or 6" |
| -1 | F | F | "Your number is not 5 or 6" |

### Worked Desk Check (c) — WHILE loop (Repetition)

Pseudocode:
```
READ count
LET x = 0
WHILE (x < count)
    LET even = even + 2
    LET x = x + 1
    DISPLAY even
ENDWHILE
```
(note: `even` starts at 0)

| X | Even (before update) | Even = even + 2 | X = x + 1 | DISPLAY even |
|---|---|---|---|---|
| 0 | 0 | 2 | 1 | 2 |
| 1 | 2 | 4 | 2 | 4 |
| 2 | 4 | 6 | 3 | 6 |
| 3 | 6 | 8 | 4 | 8 |
| 4 | 8 | 10 | 5 | 10 |

### Worked Desk Check — Bubble Sort (PF2)

Array `a = [5, 1, 4, 2, 8]`, `N = 5`, `i = 0`, `j = 0`, `swaps = 0`, `temporary = 0` initially. Completed desk-check table from the source:

| N | i | j | swaps | temporary | a[j] > a[j+1]? | a[j] | a[j+1] |
|---|---|---|---|---|---|---|---|
| 5 | 2 | 0 | 0 | 1 | TRUE | 1 | 5 |
| 5 | 2 | 1 | 1 | 4 | TRUE | 4 | 5 |
| 5 | 2 | 2 | 2 | 2 | TRUE | 2 | 5 |
| 5 | 2 | 3 | 3 | — | FALSE | 5 | 8 |
| 5 | 3 | 0 | 0 | — | FALSE | 1 | 4 |
| 5 | 3 | 1 | 0 | 2 | TRUE | 2 | 4 |
| 5 | 3 | 2 | 1 | — | FALSE | 4 | 5 |
| 5 | 3 | 3 | 1 | — | FALSE | 5 | 8 |
| 5 | 4 | 0 | 0 | — | FALSE | 1 | 2 |
| 5 | 4 | 1 | 0 | — | FALSE | 2 | 4 |
| 5 | 4 | 2 | 0 | — | FALSE | 4 | 5 |
| 5 | 4 | 3 | 0 | — | FALSE | 5 | 8 |

---

## 8. HSC exam tips for desk checks

- Always build the header row FIRST from the 4 rules: every variable, every condition, every output statement, in code order.
- Fill the table row-by-row, executing the code exactly as written (do not skip the order).
- For loops, show each iteration as its own row(s); track the loop counter and the changed variables.
- A desk check proves what the code does, not what it was meant to do — if the code is buggy, the desk check shows the bug.

---

> **See also:** [[SE_Software_Dev_Process]] | [[SE_Numbering_Systems]] | [[SE_Programming_Paradigms]] | [[SE_Object_Oriented_Programming]] | [[SE_Mechatronics]]
