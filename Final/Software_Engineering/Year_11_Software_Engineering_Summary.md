---
title: Year 11 Software Engineering Summary
subject: Software Engineering
type: final
unit: Year 11
syllabus_topic: Year 11 course overview
tags:
  - software-engineering
  - year-11
  - hsc
  - final
  - exam-ready
aliases:
  - Year 11 SE Summary
  - Year 11 Software Notes
---

# Year 11 Software Engineering Summary

> **Scope:** The three Year 11 focus areas in the NESA Software Engineering 11-12 Syllabus (2022): Programming Fundamentals, The Object-Oriented Paradigm, and Programming Mechatronics. This is a revision summary, not a prediction of exact HSC marks. Your estimate of roughly 15% in a typical paper and up to 30% is useful for prioritising revision, but do not treat it as a guaranteed weighting. No specific exam notification was provided, so this covers the broad Year 11 scope.

The main skill linking all three areas is turning a real need into a working solution: understand the problem, model the data and behaviour, design and code an algorithm, test it, then evaluate how well the complete system works. If revision time is short, start with those connected skills, then review the individual facts and definitions. That is a study order, not a claim about which questions will appear.

## 1. Programming Fundamentals

### 1.1 Software development process

A software development process breaks a project into stages so the team can move from a user need to a tested and maintained system.

<ol>
<li><b>Requirements definition:</b> identify the problem, users and what they need.</li>
<li><b>Determining specifications:</b> translate needs into precise, testable system requirements.</li>
<li><b>Design:</b> plan the algorithm, data, interfaces and system structure.</li>
<li><b>Development:</b> write and refine the program code.</li>
<li><b>Integration:</b> combine components and check that they work together.</li>
<li><b>Testing and debugging:</b> find faults, correct them, and check the revised solution.</li>
<li><b>Installation:</b> put the system into use, with a suitable conversion or deployment plan.</li>
<li><b>Maintenance:</b> fix faults and update the system as users, technology or requirements change.</li>
</ol>

> **Requirements vs specifications:** a requirement describes what the user needs; a specification states what the system must do in a measurable, testable way. For example, “staff can find a booking” is a need, while “show matching bookings within two seconds” is a testable specification.

A **functional requirement** describes an action the system performs, such as saving a booking. A **non-functional requirement** describes a quality or constraint, such as security, usability, speed or reliability.

### 1.2 Collaboration tools and project models

Online code collaboration tools let developers share code, track changes and coordinate work. Tools such as GitHub and GitLab can provide repositories, version histories, branches, code reviews and issue tracking. To evaluate their use, consider how widely they are used in the relevant context, how they support teamwork and recovery of earlier versions, and risks such as access control, merge conflicts, accidental sharing or dependence on internet access. Do not claim a tool is “the most common” unless you have evidence for that context.

<details><summary><b>Waterfall and Agile comparison</b></summary>
<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;"></th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Waterfall</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Agile</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Structure</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Linear stages, completed in sequence.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Short repeated cycles of design, development, testing and feedback.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Best fit</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Requirements are stable and clear from the start.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Requirements may change and users can give ongoing feedback.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Trade-off</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Easy to plan, but late changes can be costly.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Adapts quickly, but scope and total time can be harder to predict.</td></tr>
</tbody></table>
</details>

### 1.3 Algorithms and computational thinking

An **algorithm** is a precise sequence of steps for solving a problem. Before coding, identify the inputs, outputs, processing steps, conditions, repeated actions and data that must be stored.

- **Sequence:** steps run in order.
- **Selection:** a condition chooses a path, such as `IF / ELSE`.
- **Iteration:** a loop repeats steps while or until a condition is met.

Use **pseudocode** or a **flowchart** to plan logic before writing code. Flowcharts commonly use an oval for start/stop, a parallelogram for input/output, a rectangle for processing, and a diamond for a decision. Structured algorithms should be indented clearly and use named subprograms for separate tasks.

**Divide and conquer** breaks a large problem into smaller parts, solves those parts, then combines their results. **Backtracking** explores a possible choice, then reverses that choice if it leads to a dead end. For example, a maze solver can try a path and backtrack when blocked.

A **structure chart** shows how modules or subprograms are organised. **Abstraction/refinement diagrams** show a task at different levels of detail: abstraction hides detail that is not needed at the current level; refinement adds detail in stages. A top-down design starts with the overall task and breaks it into parts. A bottom-up design builds or selects smaller components and combines them into a whole.

To analyse an algorithm, state its purpose, identify inputs and outputs, trace how values change, and check how it connects to other procedures or functions. A **desk check** traces the algorithm by hand; a **peer check** asks another person to review the logic. A procedure carries out a task; a function returns a value.

**Worked desk check:** this algorithm adds the integers from 1 to 3. Make a row for every executed line and every condition check, including the final false check.

```text
total = 0
count = 1
WHILE count <= 3
    total = total + count
    count = count + 1
OUTPUT total
```

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Step</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Line executed</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">total</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">count</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Output / note</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = 0</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">initialise</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">initialise</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">0</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">5</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">1</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">7</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">2</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">8</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">9</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">TRUE</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">10</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>total = total + count</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">3</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">11</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>count = count + 1</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">-</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">12</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">check <code>count &lt;= 3</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">FALSE, exit</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">13</td><td style="border:1px solid #bdc1c6;padding:6px 10px;"><code>OUTPUT total</code></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">4</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">6</td></tr>
</tbody></table>

The loop runs three times and outputs 6. In an exam trace, include every variable, condition and output, and show the final false condition that exits the loop.

### 1.4 Data, number systems and data structures

A **data dictionary** documents the data used by a system so developers agree on its names, types, formats, validation rules and relationships. A useful entry includes a variable name, data type, permitted values or format, description and example.

Common types include **character** and **string** (text), **Boolean** (true/false), **integer** (whole number), **real** and **single-precision floating point** (numbers that can include fractions), and **date/time**. Choose a type that can represent the values the system actually needs.

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Structure</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">What it stores / how it is used</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Useful point</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Array / list</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">An ordered collection of values. Arrays may be single- or multidimensional; lists can grow or shrink in many languages.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Use an index to select an item.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Record</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">A group of related fields describing one item, for example a student record with ID, name and date of birth.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Fields can have different data types.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Tree</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Hierarchical data made of connected nodes, such as a folder structure.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Useful when parent-child relationships matter.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Sequential file</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Records stored and read in order, one after another.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">To reach a later record, earlier data may need to be read first.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Stack / hash table</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">A stack uses last-in, first-out access. A hash table stores key-value entries using a hash function.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Choose the structure to fit the access pattern.</td></tr>
</tbody></table>

**Number systems:** decimal is base 10, binary is base 2, and hexadecimal is base 16. Binary uses 0 and 1. Hex uses 0-9 and A-F. Each hexadecimal digit represents exactly four binary bits.

- **Binary to decimal:** multiply each bit by its place value, then add. `1010₂ = 1×8 + 0×4 + 1×2 + 0×1 = 10₁₀`. A second example: `1101₂ = 8 + 4 + 0 + 1 = 13₁₀`.
- **Decimal to binary:** turn on the powers of 2 that add to the target. `13 = 8 + 4 + 1`, so `13₁₀ = 1101₂`. Similarly, `10 = 8 + 2`, so `10₁₀ = 1010₂`.
- **Binary to hexadecimal:** group from the right into sets of four bits, then convert each group. `1010 1100₂` becomes `A C`, so `AC₁₆`.
- **Two's complement:** to represent a negative integer at a fixed bit-width, write the positive value in binary, invert every bit, then add 1. For 8-bit `-5`: `00000101` → invert to `11111010` → add 1 to get `11111011`. Keep the specified bit-width throughout.

### 1.5 Programming paradigms

A **programming paradigm** is a general way of organising a solution. Be able to experiment with the paradigms and explain how a problem or data structure fits the approach.

- **Object-oriented:** organises code around objects that combine data and methods.
- **Imperative / procedural:** describes a sequence of instructions and procedures that change or use data.
- **Logic:** describes facts and rules, then uses inference to answer a query. **Forward chaining** starts with facts and derives conclusions; **backward chaining** starts with a goal and looks for supporting facts.
- **Functional:** organises computation around functions and their results.

### 1.6 Developing solutions, testing and debugging

To turn an algorithm into code, preserve its sequence, decisions and loops, select data structures that suit the data, and use standard modules where they solve a common task. Break larger logic into subprograms. Pass required data through parameters, and make each subprogram responsible for one logical task.

The Year 11 structures include single- and multidimensional arrays, lists, trees, stacks and hash tables. Select by how the data needs to be organised or accessed: an array stores indexed items, a stack serves the most recently added item first, and a hash table associates keys with values. Records and sequential files are also important ways of organising and storing related data.

Test data should include **boundary values** at the edges of an allowed range, **faulty or abnormal values** that should be rejected or handled, and cases that exercise each decision path. For example, if an input must be from 0 to 120, test 0 and 120, values just outside the range, and a non-number. **Path coverage** checks that each important branch or route through the code has been tested.

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Test / tool</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">What it checks</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Unit, subsystem, system testing</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">One component / a group of connected components / the complete solution.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Black, white, grey box</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Test with no knowledge of internal code / with access to internal code / with partial knowledge of it.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Breakpoint and single-line stepping</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Pause execution at a chosen place and follow code one line at a time.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Watch and function-interface checks</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Track variable values and check that functions receive and return the expected data.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Debug output and IDE tools</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Print temporary state information or use the integrated debugger to locate a fault.</td></tr>
</tbody></table>

Typical errors have different causes: a **syntax error** breaks language rules, for example a missing bracket or misspelled keyword; a **logic error** uses incorrect reasoning, a condition or a formula, so the code runs but returns the wrong result; a **runtime error** occurs during execution, for example when the program tries to divide by zero or access unavailable data. Test and evaluate the solution against its required functionality, performance, code readability and documentation. **Quality assurance** is the planned checking that helps maintain reliable development and testing, not just one final test.

## 2. The Object-Oriented Paradigm

### 2.1 Classes, objects and the OOP concepts

A **class** is a blueprint; an **object** is an instance created from that blueprint. An object's **attributes** hold its data and its **methods** define actions. **Instantiation** means creating the object.

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Concept</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">What it means</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Why it matters</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Encapsulation</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Bundle related data and methods in a class, and control access to internal state.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Limits unwanted changes and keeps related logic together.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Abstraction</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Show the essential features while hiding implementation detail.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Users or other classes can use a simpler interface.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Inheritance</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">A child class receives and can extend features of a parent class.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Shared code can be reused instead of duplicated.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Generalisation</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Identify shared features and place them in a more general parent class.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Makes common properties and behaviours explicit.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Polymorphism</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Different objects can respond differently to the same method call.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">One interface can work with several related object types.</td></tr>
</tbody></table>

**Confusing pair:** encapsulation is how related data and methods are organised and protected; abstraction is what detail is hidden from the user. They often work together, but they are not the same thing.

```python
class Sensor:
    def __init__(self, name):
        self.name = name

    def read(self):
        return 0

class LightSensor(Sensor):
    def read(self):
        return 42

sensor = LightSensor("room light")  # instantiate an object
value = sensor.read()               # message/method call
```

`Sensor` is a class, `sensor` is an object, `name` is an attribute, and `read()` is a method. `LightSensor` inherits from `Sensor` and overrides `read()`. This is an example of polymorphism because the same `read()` call can produce behaviour appropriate to the object's class.

### 2.2 Procedural programming, design models and message passing

Procedural code organises a solution around procedures and a sequence of actions. OOP organises it around interacting objects. OOP can suit a system with many entities that have their own data and behaviour; a procedural approach can be simpler for a small, linear task. Choose by considering modularity, data management, maintenance and the complexity of the system.

- A **data flow diagram (DFD)** shows data moving between processes, data stores and external entities.
- A **structure chart** shows the hierarchy of modules and the data or control passed between them.
- A **class diagram** shows classes, their attributes and methods, and relationships such as inheritance.

A useful design mapping is: the system in a high-level model suggests the main class; process names suggest methods; data items suggest attributes. Refine the model before coding, then check that the code still matches the original need. **Message passing** is how objects communicate, typically by calling another object's method and supplying any required data.

**Design approaches:** define the task first. Top-down design breaks the whole task into smaller tasks. Bottom-up design combines working components into a larger system. A **façade** provides a simple front-facing interface to a more complex subsystem. **Agility** means working in small design-build-test cycles and improving the solution from feedback.

### 2.3 Code quality, optimisation and teamwork

When assessing code that implements an algorithm, use evidence and relevant criteria: **functionality/correctness**, performance and resource use, readability, documentation, maintainability, robustness, scalability, portability, security and testability. Link each judgement to a specific feature of the code, not just the criterion's name.

**Code optimisation** changes code to improve performance or resource use. Optimise only when there is a reason and test the result, because changes made for speed can make code harder to read or maintain.

Good OOP development uses a clear mainline, with one logical task per subroutine. **Stubs** are temporary placeholders used to test a larger program before every component is complete. Use appropriate control and data structures, version control, regular backups and safe handling of data. Test components, their combinations and the complete system.

Collaboration improves when a team uses consistent naming and style, useful comments, version control and regular feedback. These practices reduce conflicting changes and make it easier to understand, review, restore and extend code.

### 2.4 OOP implementation and evaluation

An OOP program still uses branching, iteration and functions or methods. When implementing it, keep the mainline clear, use one logical task per subroutine, use stubs while parts are unfinished, and back up code regularly. Evaluate the classes and the complete program through unit, subsystem and system tests, using suitable black-box, white-box or grey-box methods. Check the interfaces between methods as well as the methods themselves.

## 3. Programming Mechatronics

### 3.1 How a mechatronic system works

**Mechatronics** combines mechanical systems, electronics, computing and control. A system senses a real-world condition, processes data in a controller, and produces an action through an actuator or end effector.

```text
Physical condition -> Sensor -> Controller / program -> Actuator -> Physical action
                         ^                                       |
                         +----------- feedback, if measured ------+
```

Applications include manufacturing, transport, agriculture, healthcare and assistive technology. When designing a system for a person with disability, begin with the specific user's abilities, environment, safety and control needs; these can affect the sensors, interface, movement and feedback the system should provide.

### 3.2 CPU, microcontroller and registers

A **CPU** is the processor that executes instructions and usually relies on other components for memory and input/output. A **microcontroller** integrates a processor, memory and input/output on one chip, which suits dedicated embedded tasks such as reading a sensor and controlling a motor.

The CPU uses an instruction set. An instruction's **opcode** identifies the operation; its **operand** identifies the data or address involved. Registers temporarily hold information during processing.

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Register</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Holds</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Memory cue</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>PC</b>, Program Counter</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Address of the next instruction.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Next instruction.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>MAR</b>, Memory Address Register</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Address of the memory location being accessed.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Where.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>MDR</b>, Memory Data Register</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Data being read from or written to memory.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">What.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>CIR</b>, Current Instruction Register</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Instruction currently being decoded or executed.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Current instruction.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>ACC</b>, Accumulator</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Intermediate or final results of operations.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Calculation result.</td></tr>
</tbody></table>

In a simplified **fetch-decode-execute cycle**, the processor fetches an instruction from memory using its address, places it in the instruction register, decodes the opcode and operand, executes the instruction, stores any result, then advances to the next instruction. Be able to explain how this hardware affects the way code and data are processed.

### 3.3 Sensors, actuators, data and physical constraints

A **sensor** converts a physical condition into data a controller can process. An **actuator** converts a controller's electrical output into movement or another physical action. An **end effector** or **manipulator** is the tool at the end of a mechanism that interacts with an object, such as a robotic gripper.

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Component / data</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Role or example</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Design point</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Motion sensor</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Detects movement, acceleration, tilt or distance.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Consider range, accuracy and update speed.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Light-level sensor</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Measures light, for example with an LDR or photodiode.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">An analogue output may need conversion to digital data.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Hydraulic actuator</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Uses fluid pressure to create high-force movement.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Check force, movement range and safety.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Robotic gripper</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">An end effector that grasps, holds or releases an object.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Match grip strength and shape to the object and user.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Operational data</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Current sensor readings while the system runs.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Supports real-time decisions.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Diagnostic / optimisation data</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Diagnostic data helps identify faults; optimisation data helps improve performance over time.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Use data to improve reliability without collecting unnecessary information.</td></tr>
</tbody></table>

A mechatronic system must respect **motion constraints** such as the available range, speed, load and risk of collision. **Degrees of freedom** describe the independent ways a mechanism can move. Use code and simulation to experiment with how components depend on each other, then combine compatible subsystems, sensors, actuators and end effectors so each part interacts correctly with the rest.

### 3.4 Control algorithms and feedback

A control algorithm reads sensor data, compares the current state with a target or rule, and sends an output to an actuator. An autonomous system repeats this process without a person making each control decision.

- **Open-loop control** follows a set instruction without measuring the result. It is simpler, but cannot automatically correct for disturbances.
- **Closed-loop control** measures the result and uses feedback to adjust the output. It can be more accurate, but needs sensors and additional processing.
- **On/off control** switches between two states. It is simple but can overshoot or oscillate.
- **Proportional control** changes the output in proportion to the difference between the target and measured value. It can leave a small steady-state error.
- **PID control** combines proportional response, accumulated error over time (integral), and response to the rate of change (derivative). The terms can reduce residual error and overshoot when correctly tuned.

For a design answer, state the sensor input, target or decision rule, repeated control steps, actuator output, and how feedback is used. A line-following robot, for example, reads a sensor, estimates whether it is left or right of the line, then adjusts the motors to reduce that error.

### 3.5 Building, wiring and testing a system

A real-world mechatronics solution combines software control, mechanical design, electronics and mathematics. Select components by checking their data and power requirements, battery capacity, material strength, motion limits and how the parts will connect. Wiring diagrams should clearly show both the data connections and the power supply. A resistor can limit current through an LED; a pull-up or pull-down arrangement can give a digital input a defined state when a switch is open.

Use a **simulation** or **prototype** to test code and component interactions before committing to the final physical build. A user interface should let the intended user control the system clearly and safely. Unit-test each component's control algorithm, then repeat tests to check that behaviour is effective and consistent. A successful test of one component does not prove that the integrated system works, so test the combined subsystems too.

Ohm's law links voltage, current and resistance: `V = I × R`. In a circuit, an ammeter measures current in series and a voltmeter measures potential difference in parallel. In a question, show the formula, substitute the values with units, and state the result.

## 4. High-value distinctions

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Do not mix up</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">The difference</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Requirement / specification</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">User need / measurable system statement.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Syntax / logic / runtime error</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Invalid language rules / wrong result / fault while executing.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Procedure / function</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Performs a task / returns a value.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Class / object</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Blueprint / instance created from it.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Encapsulation / abstraction</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Organise and protect internal state / hide unnecessary detail from the user.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Open-loop / closed-loop</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Does not measure the result / uses feedback to adjust.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Sensor / actuator</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Reads a physical condition / causes a physical action.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;">Unit / subsystem / system test</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Test one component / a connected group / the complete solution.</td></tr>
</tbody></table>

## 5. Exam response approach

For “explain”, describe the mechanism and its consequence. For “justify” or “assess”, make a judgement that fits the scenario, support it with specific evidence, and acknowledge an important limitation where relevant. For code-quality questions, name a criterion, point to the feature being assessed, and explain the effect on the user or system.

For a mechatronics design question, connect the chain clearly: **user need -> sensor/data -> algorithm -> controller -> actuator/action -> test result**. For an OOP question, explain how the class, object, attribute, method or relationship helps implement that need. Avoid listing terms without showing how they apply.

## 6. Quick revision checklist

- [ ] Recall the eight software development steps and explain how requirements differ from specifications.
- [ ] Compare Waterfall and Agile, and explain benefits and risks of online code collaboration.
- [ ] Design and trace algorithms using sequence, selection, iteration and subprograms.
- [ ] Use divide and conquer and backtracking appropriately; identify inputs, outputs and stored data.
- [ ] Convert binary and hexadecimal values, use two's complement at a stated bit-width, and select suitable data types.
- [ ] Explain data dictionaries, arrays, records, trees, sequential files, lists, stacks and hash tables.
- [ ] Find and correct errors using testing, test data, debugging tools and clear evaluation criteria.
- [ ] Explain classes, objects, encapsulation, abstraction, inheritance, generalisation and polymorphism.
- [ ] Read DFDs, structure charts and class diagrams, and connect a model to code.
- [ ] Explain message passing, optimisation, stubs, version control, backup and collaborative practices.
- [ ] Distinguish CPU and microcontroller; explain the fetch-decode-execute cycle and key registers.
- [ ] Identify sensors, actuators and end effectors, and describe the data and physical constraints of a system.
- [ ] Design an open- or closed-loop control algorithm; distinguish on/off, proportional and PID control.
- [ ] Explain how wiring, power, simulation, prototyping, UI and repeatable unit tests contribute to a working system.

## Sources and related notes

- [NESA Software Engineering 11-12 Syllabus (2022), Year 11 Programming Fundamentals](https://curriculum.nsw.edu.au/learning-areas/tas/software-engineering-11-12-2022/content/year-11/fac3c86ce1)
- [NESA Software Engineering 11-12 Syllabus (2022), The Object-Oriented Paradigm](https://curriculum.nsw.edu.au/learning-areas/tas/software-engineering-11-12-2022/content/year-11/fa332a6f82)
- [NESA Software Engineering 11-12 Syllabus (2022), Programming Mechatronics](https://curriculum.nsw.edu.au/learning-areas/tas/software-engineering-11-12-2022/content/year-11/fa70b5c187)
- Detailed revision notes: [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Mechatronics]]

## Glossary: Confusing Terms Quick Reference

<table style="border-collapse:collapse;width:100%;font-size:14px;margin:8px 0;">
<thead><tr><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Term</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Meaning</th><th style="border:1px solid #bdc1c6;padding:6px 10px;text-align:left;background:#e8eaed;color:#000000;font-weight:600;">Do not confuse with</th></tr></thead>
<tbody>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Requirement</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">What the user needs.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Specification, the testable system statement.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Syntax error</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Code breaks language rules.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Logic error, which runs but produces the wrong answer.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Procedure</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">A subprogram that performs a task.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Function, which returns a value.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Class</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Blueprint for objects.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Object, one instance created from the blueprint.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Encapsulation</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Organises related data and methods, controlling access to internal state.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Abstraction, hiding detail behind an essential interface.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Sensor</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Reads a physical condition as data.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Actuator, which creates a physical action.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>Open loop</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Acts without measuring its result.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Closed loop, which uses feedback to adjust.</td></tr>
<tr><td style="border:1px solid #bdc1c6;padding:6px 10px;"><b>MAR</b></td><td style="border:1px solid #bdc1c6;padding:6px 10px;">Holds the memory address being accessed.</td><td style="border:1px solid #bdc1c6;padding:6px 10px;">MDR, which holds the data being transferred.</td></tr>
</tbody></table>

> **See also:** [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Mechatronics]] | [[MOC]]

*This summary follows the NESA Year 11 focus areas and condenses the existing class revision notes into one document. Use the linked detailed notes for extra examples and full worked explanations.*