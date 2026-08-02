---
title: Programming Fundamentals
subject: Software Engineering
type: final
unit: Year 11
syllabus_topic: Programming Fundamentals
tags:
  - software-engineering
  - programming-fundamentals
  - hsc
  - final
  - exam-ready
  - year-11
aliases:
  - PF
  - SDLC
  - Desk Checks
---

# Programming Fundamentals — HSC Final Notes

> **Year 11, Unit 1** | Software development steps, algorithms, desk checks, data modelling tools, numbering systems and programming paradigms.

---

## 1. Software Development Steps

**The eight steps:**

```
1. Requirements definition
2. Determining specifications
3. Design
4. Coding
5. Testing
6. Installation
7. Maintenance
8. Evaluation
```

### 1.1 Tool-to-Step Mapping

| Step | Tools used |
|---|---|
| **1. Requirements** | Needs analysis, requirements definition, flowchart |
| **2. Specifications** | Data dictionary |
| **3. Design** | Flowchart, pseudocode, decision tree, storyboard, algorithm, DFD, structure chart, IPO chart, class diagram |
| **4. Coding** | Control structures |
| **5. Testing** | Syntax / logic / runtime error checking; white, black and grey box testing |
| **6. Installation** | Phased, pilot, direct or parallel conversion; installation plan |
| **7. Maintenance** | Maintenance plan |

> **Confusing pair — Requirements vs Specifications**
> **Requirements** = *what the user needs* — described in the user's language ("staff must be able to look up a booking").
> **Specifications** = *what the system must do* — described in technical terms, measurable and testable ("the system shall return booking records matching a surname within 2 seconds").
> Requirements come from the client; specifications are the developer's translation of them.

### 1.2 Requirements — Functional vs Non-Functional

| Type | Definition | Examples |
|---|---|---|
| **Functional** | What the system **must do** | Log in, calculate a total, store a record, print a receipt |
| **Non-functional** | **How well** the system does it — qualities and constraints | Security, performance, usability, reliability, portability, accessibility |

> **Security is a non-functional requirement** — this matters in [[Secure_Software_Architecture]], where security must be designed in from step 1 rather than added later.

### 1.3 Errors

| Error type | Definition | When detected |
|---|---|---|
| **Syntax error** | Breaks the rules of the language | At compile/interpretation — before running |
| **Logic error** | Code runs but produces the **wrong output** | Only by testing the output against expectations |
| **Runtime error** | Occurs **only at execution** — e.g. divide by zero, file not found | While the program is running |

> **Memory hook**: **Syntax** = the computer can't *read* it. **Runtime** = the computer *crashes* on it. **Logic** = the computer runs it happily and gives you the *wrong answer*.

### 1.4 Testing

**Error-detection testing:**

| Method | Definition |
|---|---|
| **Black box** | Tester knows only inputs and expected outputs — **not** the internal code |
| **White box** | Tester can see and test the **internal code** and logic paths |
| **Grey box** | A combination — partial knowledge of internals |

**NESA-specified system testing methods:**

| Method | Definition |
|---|---|
| **Functional testing** | Verifies each function performs according to its specification |
| **Acceptance testing** | The **client** confirms the system meets their requirements |
| **Live data** | Testing with real, current organisational data |
| **Simulated data** | Testing with artificially generated data, including edge cases |
| **Beta testing** | Release to a limited group of **real users** outside the development team |
| **Volume testing** | Testing with **large quantities** of data to check performance under load |

**Test data categories:**

| Category | Definition | Example (age must be 0–120) |
|---|---|---|
| **Normal / valid** | Typical expected values | 25 |
| **Boundary** | Values at the edges of the valid range | 0, 120 |
| **Extreme / invalid** | Values outside the range, or the wrong type | −5, 200, "abc" |

### 1.5 Installation and Conversion

**Installation methods**: complete download; partial download; **cloud-based deployment** (e.g. Google Suite — no install required).

**Conversion methods:**

| Method | How it works | Risk |
|---|---|---|
| **Parallel** | Old and new systems run **together** for a period | **Lowest risk** — old system is a fallback. Most expensive |
| **Pilot** | New system trialled with a **small group** first | Low risk; limited disruption if it fails |
| **Phased** | Introduced **step by step**, module by module | Moderate risk; slower |
| **Direct** | Old system switched off, new one switched on — a straight swap | **Highest risk** — no fallback. Cheapest and fastest |

### 1.6 Maintenance

**Reasons for maintenance**: changing user requirements, UI upgrades, data changes, new hardware or software, change in organisational focus, government requirements, poor code.

**A maintenance plan includes**: the issue, its urgency, a description of the change, who will do it, and the timeframe.

**Types of maintenance:**

- **Corrective** — fixing faults discovered after release
- **Adaptive** — adjusting to a changed environment (new OS, new hardware)
- **Perfective** — improving performance or adding features

### 1.7 Comparative Development Approaches

#### Waterfall (5 stages)

```
1. Define problem
2. Plan & design  (Gantt chart, context diagram, DFD, system flowchart, test plan)
3. Implement
4. Test & evaluate
5. Maintain
```

#### Agile

```
1. Define
2. Plan / design / implement  ┐
3. Test & evaluate            │  stages 2–5 repeat
4. Release                    │
5. New requirements           ┘
```

> **The comparison, in the exam's words**: "Agile is iterative and flexible; Waterfall is linear and sequential. Agile is more adaptable to changing requirements; Waterfall is better for well-defined requirements."

| | **Waterfall** | **Agile** |
|---|---|---|
| Structure | Linear, sequential | Iterative, incremental |
| Requirements | Fixed at the start | Expected to change |
| Client involvement | Mainly at start and end | Continuous |
| Working software | Only at the end | Every iteration |
| Best for | Well-defined, stable projects; safety-critical work | Evolving requirements; fast-moving projects |
| Weakness | Very costly to change late | Harder to predict total cost and time |

**WAgile** — a hybrid using Waterfall's structured planning with Agile's iterative build cycles.

---

## 2. Algorithms

### 2.1 The Three Control Structures

| Structure | Definition |
|---|---|
| **Sequence** | Steps executed one after the other, in the order written |
| **Selection** | A condition determines which path is taken |
| **Repetition** | A set of steps is repeated |

### 2.2 Pseudocode Conventions (NESA)

- **Keywords are written in CAPITALS**
- Structural elements come in **pairs** — every `BEGIN` has an `END`, every `IF` has an `ENDIF`
- **Indenting** identifies control structures
- Subroutines are referred to by **name**, with the detailed logic shown separately

**Templates:**

```
BEGIN … END                          start / end
IF … THEN / ELSEIF … THEN / ELSE / ENDIF     selection
CASEWHERE expression evaluates to … END CASE  multi-way selection
FOR I = 1 TO n … NEXT I              counted repetition
WHILE condition … ENDWHILE           pre-test loop
REPEAT … UNTIL condition             post-test loop
PRINT / DISPLAY                      output
INPUT / READ                         input
LET x = 0                            process / assignment
```

### 2.3 Selection in Detail

**Binary selection** — two possible paths:

```
IF condition THEN
    process 1
ELSE
    process 2
ENDIF
```

**Multi-way selection (case structure)** — several possible choices. Once a path is determined and executed, evaluation **ceases**. Only **one** process is executed:

```
CASEWHERE expression evaluates to
    choice a: process a
    choice b: process b
    OTHERWISE: default process
END CASE
```

**Nested IF** — tests multiple conditions, with only **one** process executed:

```
IF condition A THEN
    process 1
ELSEIF condition B THEN
    process 2
ELSEIF condition C THEN
    process 3
ELSE
    process 4
ENDIF
```

### 2.4 Repetition in Detail

| Type | Definition | Key property |
|---|---|---|
| **Pre-test** (`WHILE`) | Tests the condition **at the start**. Body executes repeatedly **while** the condition is true | May execute **zero** times |
| **Post-test** (`REPEAT…UNTIL`) | Executes the body **first**, then tests. Repeats **until** the condition is true | Always executes **at least once** |
| **FOR / NEXT** (counted) | Repeats a **known number** of times. `FOR variable = start TO finish STEP increment` | Increment can be positive **or negative** |

> **Confusing pair — Pre-test vs Post-test**
> **Pre-test** checks **before** entering — so it can run **0 times**.
> **Post-test** checks **after** running — so it always runs **at least once**.
> This is the single most common multiple-choice trap in this topic.

### 2.5 Flowchart Symbols

| Symbol | Meaning |
|---|---|
| **Terminator** (rounded rectangle / oval) | Start / Stop |
| **Parallelogram** | Input / Output |
| **Rectangle** | Process |
| **Diamond** | Decision |
| **Arrow / flow line** | Direction of flow |

> Flowcharts are read **top to bottom, left to right**. Arrows coming from a decision symbol should be **labelled** to remove ambiguity.

### 2.6 Subroutines

The terms **subroutine, module, subprogram and procedure** are interchangeable — a collection of statements achieving a specific purpose.

> A **function** is a particular type of subroutine that **returns a single value**.

**Why use subroutines**: the same task can be performed at different points in an algorithm, operating on different data each time. **Parameters** indicate the data to be processed.

**One parameter:**

```
BEGIN
    read (name)
    read (address)
END

BEGIN read (arrayname)
    Set pointer to first position
    Get a character
    WHILE more data AND space in array
        Store data in arrayname at the position given by the pointer
        Increment the pointer
        Get next character
    ENDWHILE
END read (arrayname)
```

**Multiple parameters:**

```
BEGIN AddNumbers
    FOR i = 1 to 5
        Add (i, i + 1, sum)
        Display sum
    NEXT i
END AddNumbers

BEGIN Add (x, y, total)
    total = x + y
END Add (x, y, total)
```

**Returning a value from a function** — the word `RETURN` passes the single value back:

```
BEGIN Addnumbers
    FOR i = 1 to 5
        Display Add (i, i + 1)
    NEXT i
END Addnumbers

BEGIN Add (x, y)
    total = x + y
    RETURN total
END Add (x, y)
```

> **Mainline principle**: Start complex algorithms with a clear, uncluttered **mainline** that references subroutines. Each subroutine should be concise and may call further subroutines. Providing successively more detail this way is called **refinement**.

### 2.7 Sorting Algorithms

| Algorithm | How it works |
|---|---|
| **Bubble sort** | Repeatedly compares adjacent values and **swaps** if the next value is out of order. Largest values "bubble" to the end |
| **Selection sort** | Finds the smallest remaining value and swaps it into position, using a `Swap(A, B)` subroutine |

> **Known bug in the class source**: a version of bubble sort was given where the **swap is not inside the `IF`**, producing an **infinite loop**. Check that the swap is nested inside the condition.

---

## 3. Desk Checks

> This is a high-frequency exam skill. Get the table right and the marks follow.

A desk check is a **trace table**: you run the code by hand, one line at a time, and write down what each variable holds **after** every line.

### 3.1 The Four Desk Check Rules — memorise

1. **Variables** must be there
2. **Conditions** must be there
3. **Output statements** must be there
4. Statements appear **in the order they do in the code**

### 3.2 Setting Up the Table

- One column per **variable**, plus an `Output` column and a `Step` column
- Add a **Line executed** column naming the code line each row runs — this makes the table easy to follow
- Use `-` for *not assigned yet / unknown*
- For an `INPUT` line, drop in the **test value** you are feeding it
- After each line, write the **new** value of whatever that line changed

### 3.3 Exam Rules to Lock In

- Every variable gets a column, **even before it is used**. Unused = `-`
- Write the value **AFTER** the line runs, not before
- The condition line (`IF` / `WHILE`) gets its **own step**. Note true/false
- When a loop finishes, **show the final FALSE check**. Markers look for that
- Feed in test data as **normal / boundary / extreme**

### 3.4 Worked Example — Sequence

```
x = 5
y = 10
x = x + y
OUTPUT x
```

| Step | Line executed | x | y | Output |
|---|---|---|---|---|
| 1 | `x = 5` | 5 | - | - |
| 2 | `y = 10` | 5 | 10 | - |
| 3 | `x = x + y` | 15 | 10 | - |
| 4 | `OUTPUT x` | 15 | 10 | **15** |

Final output = **15**. Note `x` changes twice — row 3 shows the new value 15.

### 3.5 Worked Example — WHILE Loop

```
total = 0
count = 1
WHILE count <= 3:
    total = total + count
    count = count + 1
OUTPUT total
```

| Step | Line executed           | total | count | Output | Note                 |
| ---- | ----------------------- | ----- | ----- | ------ | -------------------- |
| 1    | `total = 0`             | 0     | -     | -      | init                 |
| 2    | `count = 1`             | 0     | 1     | -      | init                 |
| 3    | check `count <= 3`      | 0     | 1     | -      | TRUE, enter loop     |
| 4    | `total = total + count` | 1     | 1     | -      |                      |
| 5    | `count = count + 1`     | 1     | 2     | -      |                      |
| 6    | check `count <= 3`      | 1     | 2     | -      | TRUE                 |
| 7    | `total = total + count` | 3     | 2     | -      |                      |
| 8    | `count = count + 1`     | 3     | 3     | -      |                      |
| 9    | check `count <= 3`      | 3     | 3     | -      | TRUE                 |
| 10   | `total = total + count` | 6     | 3     | -      |                      |
| 11   | `count = count + 1`     | 6     | 4     | -      |                      |
| 12   | check `count <= 3`      | 6     | 4     | -      | **FALSE, exit loop** |
| 13   | `OUTPUT total`          | 6     | 4     | **6**  |                      |

Final output = **6** (that is 1+2+3). The loop ran **3** times.

### 3.6 Worked Example — IF / ELSE

```
age = 16
IF age >= 18 THEN
    status = "adult"
ELSE
    status = "minor"
OUTPUT status
```

| Step | Line executed | age | status | Output |
|---|---|---|---|---|
| 1 | `age = 16` | 16 | - | - |
| 2 | check `age >= 18` | 16 | - | FALSE, go ELSE |
| 3 | `status = "minor"` | 16 | minor | - |
| 4 | `OUTPUT status` | 16 | minor | **minor** |

Output = **"minor"**.

### 3.7 Worked Desk Check (a) — Multiplication

```
READ num1, num2
LET multi = num1 * num2
DISPLAY multi
```

| num1 | num2 | multi | DISPLAY multi |
|---|---|---|---|
| 2 | 3 | 2 × 3 = 6 | 6 |
| 5 | 4 | 5 × 4 = 20 | 20 |
| 7 | 8 | 7 × 8 = 56 | 56 |
| 10 | 0 | 10 × 0 = 0 | 0 |

### 3.8 Worked Desk Check (b) — IF / ELSEIF / ELSE

```
READ isFive
IF   (isFive = 5)  DISPLAY "your number is 5"
ELSE IF (isFive = 6)  DISPLAY "your number is 6"
ELSE                  DISPLAY "your number is not 5 or 6"
ENDIF
```

| isFive | isFive = 5? | isFive = 6? | DISPLAY |
|---|---|---|---|
| 5 | T | F | "Your number is 5" |
| 6 | F | T | "Your number is 6" |
| 8 | F | F | "Your number is not 5 or 6" |
| 0 | F | F | "Your number is not 5 or 6" |
| −1 | F | F | "Your number is not 5 or 6" |

### 3.9 Worked Desk Check (c) — WHILE Loop

```
READ count
LET x = 0
WHILE (x < count)
    LET even = even + 2
    LET x = x + 1
    DISPLAY even
ENDWHILE
```

| x | even (before update) | even = even + 2 | x = x + 1 | DISPLAY even |
|---|---|---|---|---|
| 0 | 0 | 2 | 1 | 2 |
| 1 | 2 | 4 | 2 | 4 |
| 2 | 4 | 6 | 3 | 6 |
| 3 | 6 | 8 | 4 | 8 |
| 4 | 8 | 10 | 5 | 10 |

---

## 4. System and Data Modelling Tools

### 4.1 Data Flow Diagram (DFD)

| Symbol | Meaning |
|---|---|
| **Circle** | A **process** — uses input(s) to generate output(s) |
| **Open-ended rectangle** | A **data store** — an electronic file or non-computer storage |
| **Rectangle** | An **external entity** — any person, organisation or element that provides data to, or receives data from, the system |
| **Labelled curved arrow** | A **data flow** between processes, data stores and external entities |

> **Level 0 DFD** represents an **overview of the entire system** and does **not** show data stores or internal processes.
> **Level 1 DFD** breaks the system into its main processes.

### 4.2 Structure Chart

Represents a system by showing the separate **subroutines** and their relationships.

| Symbol | Meaning |
|---|---|
| **Empty circle** | Data movement between subroutines (a **parameter**) |
| **Filled circle** | A **flag or control variable** passed between subroutines |
| **Small diamond** | A **decision** — optional execution of a subroutine, from binary or multi-way selection |
| **Curved arrow** | **Repetition** — a subroutine executed multiple times |

> Providing successively more detail in separate charts is called **refinement**.

### 4.3 Data Dictionary

A comprehensive description of **each variable** stored or referred to in a system.

**Columns**: Variable name · Data type · Format for display · Size in bytes · Size for display · Description · Example · Validation rule

**Worked extract:**

| Variable | Data type | Format | Bytes | Display | Description | Example | Validation |
|---|---|---|---|---|---|---|---|
| UserId | String | XXNNN | 5 | 5 | Primary key; first 2 letters of surname + unique 3-digit identifier | PT173 | First 2 characters letters, last 3 digits |
| UserName | String | XX..XX | 15 | 15 | Username of employee | Kim | First letter a capital |
| DOB | Date and Time | YYYY/MM/DD | 4 | 10 | Birth date of employee | 1953/10/05 | Valid date less than today |
| Times_Late | Integer | NNN | 2 | 3 | Times late to work this year | 147 | Integer between 0 and 999 |
| PayRate | Floating point | $NNN.NN | 4 | 7 | Hourly rate of pay | $124.37 | Decimal > 20 and < 400 |
| SocialClub | Boolean | X | 1 bit | 1 | Y or N | N | |

> **Note**: a date and time data type is **always stored as 32 bits (4 bytes)** and can be displayed in different formats such as `DD/MM/YYYY hh:mm:ss` or `YYYY/MM/DD`.

### 4.4 Decision Tree

A diagram representing **all possible combinations of decisions and their resulting actions**. Branches describe the eventual action depending on the condition at the time. Each decision path leads to **either another decision or a final action**.

> Example use: the rules controlling a temperature system in a smart house.

### 4.5 Storyboard

Shows the various **interfaces (screens)** and the **links between them**.

| Type | Structure |
|---|---|
| **Linear** | Screens in a fixed sequence |
| **Hierarchical** | A tree branching from a main menu |
| **Non-linear** | Any screen can link to any other |
| **Composite** | A combination of the above |

### 4.6 IPO Chart

| Column | Content |
|---|---|
| **Input** | Data entering the system |
| **Process** | What is done to it |
| **Output** | What comes out |

> **IPSO** adds **Storage** — used for web and mobile applications that persist data.

### 4.7 Gantt Charts (Project Management)

A Gantt chart displays each **component task** on an estimated **timeline**. Tasks should have self-explanatory titles; the estimated time and **dependent tasks** should be clearly shown; the time scale should show dates and **milestones**.

> Gantt charts can also **allocate resources**, including team members, and show percentage completion. Charts should be **regularly updated** to reflect actual versus estimated times.

### 4.8 Process Diaries / Log Books

Document the progress of a project. Entries at regular intervals should include: date · person making the entry · progress since the last entry · tasks achieved · stumbling blocks and how they were managed · possible approaches for upcoming tasks · reflective comments · resources used.

---

## 5. Numbering Systems

**What a numbering system (a "base") is**: the set of digits you are allowed to use, plus the rule that each position is worth `base ^ position` (counted from 0 at the right).

| Base | Name | Allowed digits | Why it exists |
|---|---|---|---|
| 10 | Decimal | 0–9 | The everyday system |
| 2 | Binary | 0, 1 | Computers are switches: 0 = off, 1 = on |
| 16 | Hexadecimal | 0–9 then A–F | Shorthand for binary (4 bits = 1 hex digit) |

**Place-value grids:**

| | Col 4 | Col 3 | Col 2 | Col 1 |
|---|---|---|---|---|
| **Decimal** | 10³ = 1000 | 10² = 100 | 10¹ = 10 | 10⁰ = 1 |
| **Binary** | 2³ = 8 | 2² = 4 | 2¹ = 2 | 2⁰ = 1 |
| **Hex** | 16³ = 4096 | 16² = 256 | 16¹ = 16 | 16⁰ = 1 |

### 5.1 Binary → Decimal

Write the place value above each bit, multiply, then add. **Only the 1-bits count.**

Worked `1010`:

| Bit | 1 | 0 | 1 | 0 |
|---|---|---|---|---|
| Place value | 8 | 4 | 2 | 1 |
| Bit × place | 8 | 0 | 2 | 0 |

Sum = 8 + 0 + 2 + 0 = **10**

Second example `1101`: 8 + 4 + 0 + 1 = **13**

### 5.2 Decimal → Binary

Start from the biggest power of 2 that fits, turn that bit ON, subtract, repeat until 0. Unused powers stay OFF.

Worked `10`:

- Biggest power ≤ 10 is **8** (2³). 10 − 8 = 2 → bit 8 ON
- Biggest power ≤ 2 is **2** (2¹). 2 − 2 = 0 → bit 2 ON
- Bits 4 and 1 never used → OFF
- 8 4 2 1 = **1 0 1 0** → `1010`

Second example `13`: 13 − 8 = 5; 5 − 4 = 1; 1 − 1 = 0 → bits 8, 4, 1 ON, bit 2 OFF → `1101`

**Powers to know (8 bits = 1 byte)**: 128, 64, 32, 16, 8, 4, 2, 1

### 5.3 Hex → Decimal

Each hex digit × 16^position, summed.

`DEAF` = (13 × 4096) + (14 × 256) + (10 × 16) + (15 × 1) = 53248 + 3584 + 160 + 15 = **57007**

### 5.4 Decimal → Hex

Repeatedly divide by 16, keep remainders, map 10–15 to A–F, read **bottom to top**.

`999` → 999 ÷ 16 = 62 r **7**; 62 ÷ 16 = 3 r **14 (E)**; 3 ÷ 16 = 0 r **3** → read up = **3E7**

### 5.5 Binary ↔ Hex Shortcut

Every **4 binary digits = exactly 1 hex digit**. Memorise this row:

| Dec | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Bin** | 0000 | 0001 | 0010 | 0011 | 0100 | 0101 | 0110 | 0111 | 1000 | 1001 | 1010 | 1011 | 1100 | 1101 | 1110 | 1111 |
| **Hex** | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |

So `3AB2` → `3`=0011, `A`=1010, `B`=1011, `2`=0010 ⇒ `0011 1010 1011 0010`

### 5.6 Two's Complement — Storing Negative Numbers

Computers only have 0 and 1, so the **leftmost bit is the sign bit** (0 = positive, 1 = negative). Two's complement is standard because it lets the CPU use the **same addition circuit** for positive and negative numbers — no separate subtractor is needed.

**Method:**

1. Write the **positive** value in binary
2. **Flip every bit** (0↔1) — this is the **one's complement**
3. **Add 1** — this gives the **two's complement**

> **Worked: −14**
> - `+14` = `0001110`
> - Flip every bit → `1110001`
> - Add 1 → `1110010`
> - With the sign bit separated: **`1 1110010`**

**Answers to memorise**: `−127` → `1 0000001` | `+32` → `0 0100000` | `−14` → `1 1110010`

### 5.7 Character Representation

Characters are represented with **ASCII** or **Unicode**. When working with text strings, a developer can use how the text is stored **in binary** to perform functions such as **changing the case** of letters or performing a **simple encryption**.

> This is the mechanism behind the Caesar cipher work in [[Programming_For_The_Web]] — shifting a character is arithmetic on its character code.

---

## 6. Programming Paradigms

A **paradigm** is the overall **style** a language uses to solve problems.

| Paradigm | What it is | Students should know how to |
|---|---|---|
| **Object-oriented** | Build the program as a set of "things" (objects), each bundling its own data and the actions it can perform. Models the real world | Define classes, objects, attributes and methods; use inheritance, polymorphism and encapsulation; perform **message passing**; use control structures and variables |
| **Logic** | Program as a base of **facts** and **rules**; an inference engine reasons over them to answer questions | Define and edit **facts**; create, edit and remove **rules**; display the solution **and the rules the system used** |
| **Imperative / procedural** | Code as a sequence of step-by-step commands that change program state | Use control structures and variables; use **assignment statements**; use **expressions**; use **subroutines** |
| **Functional** | Builds results by combining functions, avoiding changing state | Call functions and use **recursion**; use functions as **first-class objects** and collections; use abstraction, encapsulation, inheritance and polymorphism |

> Students should know how to use **appropriate data structures** for each paradigm.

### 6.1 Logic Paradigm Terms

| Term | Definition |
|---|---|
| **Fact** | A statement asserted to be true — part of the **knowledge base** |
| **Rule** | An "if this then that" relationship the system can apply |
| **Knowledge base** | The complete collection of facts and rules |
| **Inference engine** | The component that applies rules to facts to reach conclusions |
| **Forward chaining** | Starts from **known facts** and works forward to a conclusion |
| **Backward chaining** | Starts from a **goal** and works backwards to find supporting facts |
| **Heuristics** | Rules of thumb — practical shortcuts that usually work |
| **Goal** | The query the system is trying to prove |
| **Expert system** | A program that emulates the decision-making of a human expert |

> **Confusing pair — Forward vs Backward chaining**
> **Forward** = data-driven. "I know A and B — what can I conclude?"
> **Backward** = goal-driven. "I want to prove Z — what would I need to know?"

---

## 7. HSC Exam Response Structures

### Verb → Action

| Verb | What to do |
|---|---|
| **List / State** | Name items — no explanation |
| **Define** | State the meaning and essential qualities |
| **Describe** | Provide characteristics and features |
| **Explain** | Relate cause and effect; make relationships evident; say **why** and **how** |
| **Analyse** | Identify components and the relationships between them; draw out implications |
| **Justify** | Support an argument or conclusion with evidence |
| **Evaluate** | Make a judgement based on criteria |

### Desk Check Question Scaffold

1. Write the header row with **every variable, condition and output**, in code order
2. Execute **row by row**, writing the value after each line runs
3. For loops, one row per iteration, tracking the counter and changed variables
4. Show the **final FALSE check** that exits the loop

### Extended Paragraph Scaffold

```
Topic sentence (define the term)
  → explain the mechanism (how it works)
  → apply to a scenario (your project or a given case)
  → link to a syllabus concept
```

---

## 8. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **Requirements** | What the **user** needs | **Specifications** — the technical translation |
| **Functional requirement** | What the system **does** | **Non-functional** — how well it does it |
| **Syntax error** | Breaks language rules; caught before running | **Logic error** — runs but gives the wrong answer |
| **Logic error** | Wrong output, no crash | **Runtime error** — crashes during execution |
| **Black box testing** | Tester sees only inputs and outputs | **White box** — tester sees the code |
| **Beta testing** | Real users outside the dev team | **Acceptance testing** — the client signs off |
| **Volume testing** | Large quantities of data | Load/stress testing (related but about traffic) |
| **Parallel conversion** | Old and new run together — safest | **Direct** — straight swap, riskiest |
| **Pilot conversion** | Small group trials it first | **Phased** — introduced module by module |
| **Pre-test loop** | Checks first; may run **0** times | **Post-test** — always runs **at least once** |
| **Binary selection** | Two paths (IF/ELSE) | **Multi-way** — several cases |
| **Subroutine** | A block of statements achieving a purpose | **Function** — a subroutine that **returns a value** |
| **Parameter** | The variable named in the subroutine definition | **Argument** — the actual value passed in |
| **Level 0 DFD** | Whole-system overview; **no** data stores | **Level 1** — shows main processes |
| **Data store** (DFD) | A file or storage location | **External entity** — a person or organisation |
| **Structure chart** | Shows subroutines and their relationships | **DFD** — shows data movement |
| **Empty circle** (structure chart) | A data parameter | **Filled circle** — a control flag |
| **Data dictionary** | Describes **every variable** in the system | Data flow diagram (shows movement) |
| **Decision tree** | All combinations of decisions and actions | Structure chart |
| **Storyboard** | Screens and the links between them | Flowchart (logic, not interface) |
| **Gantt chart** | Tasks on a timeline | Critical path (dependencies) |
| **One's complement** | Flip every bit | **Two's complement** — flip, then **add 1** |
| **Refinement** | Adding successive detail in separate diagrams | Refactoring (rewriting code) |
| **Forward chaining** | Facts → conclusion | **Backward chaining** — goal → facts |
| **Heuristic** | A rule of thumb that usually works | An algorithm (guaranteed correct) |
| **Corrective maintenance** | Fixing faults | **Adaptive** — adjusting to a new environment |

---

## 9. Quick Revision Checklist

- [ ] Name the 8 software development steps and a tool for each
- [ ] Distinguish requirements from specifications
- [ ] Syntax vs logic vs runtime errors
- [ ] Black / white / grey box testing, and the 6 NESA system testing methods
- [ ] Four conversion methods and their risk profiles
- [ ] Waterfall vs Agile — structure, requirements, client involvement
- [ ] The three control structures; pre-test vs post-test
- [ ] The four desk check rules, and can run a full trace table with a FALSE exit
- [ ] Pseudocode templates: IF/ELSEIF, CASEWHERE, WHILE, REPEAT/UNTIL, FOR/NEXT
- [ ] Subroutines with parameters, and functions with RETURN
- [ ] DFD symbols; Level 0 vs Level 1
- [ ] Structure chart symbols (empty vs filled circle, diamond, curved arrow)
- [ ] Data dictionary columns and a worked row
- [ ] Binary ↔ decimal ↔ hex conversion
- [ ] Two's complement in three steps
- [ ] Four paradigms and what students must be able to do in each
- [ ] Forward vs backward chaining

---

> **See also:** [[Object_Oriented_Programming]] | [[Mechatronics]] | [[Programming_For_The_Web]] | [[Software_Automation]] | [[Secure_Software_Architecture]] | [[MOC]]
