---
title: Object-Oriented Programming
subject: Software Engineering
type: final
unit: Year 11
syllabus_topic: The Object-Oriented Paradigm
tags:
  - software-engineering
  - oop
  - hsc
  - final
  - exam-ready
  - year-11
aliases:
  - OOP
  - Object-Oriented Paradigm
  - Class Diagrams
---

# Object-Oriented Programming — HSC Final Notes

> **Year 11, Unit 2** | OOP concepts, design diagrams, design approaches, effectiveness criteria and collaboration.

---

## 1. Core OOP Concepts

| Term | Definition |
|---|---|
| **Object** | A self-contained unit consisting of both **data (attributes)** and **functionality (methods)**. It represents a real-world entity or concept |
| **Class** | A **blueprint or template** for creating objects. It defines the properties and behaviours that objects of that type will have |
| **Encapsulation** | The **bundling of data and methods** that operate on that data into a single unit or class. It **hides the internal state** of an object from the outside world |
| **Abstraction** | The process of **hiding complex implementation details** and showing only the essential features of an object |
| **Inheritance** | A mechanism where a new class (**derived / child class**) is created from an existing class (**base / parent class**). The derived class inherits properties and behaviours from the base class |
| **Generalisation** | Extracting common properties and behaviours from multiple classes and creating a more general **superclass** to represent them |
| **Polymorphism** | Allows objects of **different classes** to be treated as objects of a common superclass. It enables methods to **behave differently** based on the object that calls them |
| **Attribute** | A piece of data or property belonging to an object — typically represented by **variables** within a class |
| **Method** | A function or subroutine defined **within a class** that operates on objects created from that class |
| **Instantiation** | The process of creating an **instance** of a class — creating an object from a blueprint |
| **Message passing** | Objects communicating by **calling each other's methods** and passing data between them |

### 1.1 The Four Pillars — how they connect

> This is what an exam question actually tests.

You **bundle** data and methods into a class and **hide** the internals (**encapsulation**), you show only what the user needs to see (**abstraction**), you make a child class **reuse** a parent's code (**inheritance**), and you let different child classes **respond differently** to the same method call (**polymorphism**).

```
Encapsulation + Abstraction  →  about PROTECTING and HIDING
Inheritance   + Polymorphism →  about REUSING and VARYING
```

> **Confusing pair — Encapsulation vs Abstraction**
> **Encapsulation** is the *mechanism*: physically bundling data with the methods that use it, and restricting outside access.
> **Abstraction** is the *outcome*: the user sees a simple interface and doesn't need to know how it works.
> A car: **encapsulation** is the engine being sealed under the bonnet; **abstraction** is you only needing the steering wheel and pedals.

> **Confusing pair — Class vs Object**
> A **class** is the blueprint. An **object** is one thing built from it.
> `Apple` is the class; `GrannySmithApple` is an object. One class, many objects.

### 1.2 Worked Illustration — Fruit / Apple / Orange

```python
class Fruit:
    def __init__(self, shape, colour, taste):   # Constructor
        self.shape = shape
        self.colour = colour
        self.taste = taste
    def Eat(self): ...
    def Drink(self): ...

class Apple(Fruit):          # Inheritance
    def __init__(self): ...
    def Slice(self): ...

class Orange(Fruit):         # Inheritance
    def __init__(self): ...
    def Peel(self): ...

GrannySmithApple = Apple()   # Instantiation
ValenciaOrange = Orange()    # Instantiation
```

> **Classroom wording, clarified**: your source states *"redefinition of constructor is polymorphism"* — each subclass redefines `__init__()`.
> Strictly, redefining an inherited method in a subclass is called **method overriding**, and overriding is **one form of polymorphism**. So the classroom statement is a simplification rather than an error. If asked to define polymorphism, use the full definition in §1: *different classes responding differently to the same method call.*

### 1.3 JavaScript Mappings

| Concept | Code |
|---|---|
| **Object** | `const square = new Rectangle(10, 10);` |
| **Class** | `class Student { constructor() { var name; var marks; } getName() {…} setName(name) {…} }` then `var stud = new Student(); stud.setName("John");` |
| **Inheritance** | `class secondClass extends firstClass { add() { console.log(30+40); } }` |
| **Attribute** | `this.height`, `this.width` inside `class Rectangle` |
| **Method** | `calcArea()` / `get area()` inside `class Rectangle` |

### 1.4 Benefit of Instantiation — model answer

> "One benefit of instantiation in OOP is being able to create **multiple objects from the same class, each with its own data**. For example: `student1 = Student("Sashank")`, `student2 = Student("Fayez")`. Each student variable has its own name and can act **independently** while sharing the same class structure."

### 1.5 Factors Influencing Choice of Paradigm

| Factor | Definition |
|---|---|
| **Modularity** | How easily the program can be broken into smaller, reusable modules |
| **Data management** | How data is stored, accessed and passed around |
| **Maintainability** | How simple it is to update, debug and scale without introducing errors |

> **The judgement to make**: OOP is more suitable for **complex systems with multiple interacting elements**, while procedural programming may be more efficient for **simpler, task-driven modules**.

---

## 2. OOP Design Diagrams

Three diagram types are examinable: **DFD**, **Structure Chart** and **Class Diagram**.

### 2.1 Data Flow Diagram (DFD)

> "A data flow diagram shows the flow of the data among a set of components. **The actors are not included** in the data flow diagram."

**Rules that convert a DFD into OOP code:**

| DFD element | Becomes in code |
|---|---|
| **Boxes are processes and must be verb phrases** | Your **classes** and/or **methods** |
| **Arcs / data flows are noun phrases** | Your **variables or attributes** |
| **Control is not shown** | Some sequencing can be inferred from ordering |

**Symbols**: Process (transforms data) · Data Store (storage) · External Entity (outside the system) · Data Flow (movement of data)

**Worked application — the Fruit system:**

- **Level 0**: `Make Fruit`
- **Level 1**: `Process Apple` / `Process Orange`
- **Level 2**: `Initialise fruit` → `Eat` / `Drink` / `Slice` / `Peel`
- Data flows labelled: `shape, colour, taste`

### 2.2 Structure Chart

> "Used to model the **hierarchy (top-down design)** of processes. Data movements between processes are included. Decisions and repetitions are also indicated."

| Symbol | Meaning |
|---|---|
| **Filled circle** | A **flag or control variable** sent between subroutines |
| **Empty circle** | **Data flow** between subroutines (arguments/parameters) |
| **Tiny diamond** | A **binary or multi-way selection** — a choice |
| **Curved arrow** | **Repetition** |
| **Box** | A function / manageable section of code |
| **Control box** | The **first box** — tells which part of the program is being diagrammed (e.g. `Process invoices`) |

> **Confusing pair — Parameter vs Control parameter**
> A **parameter** is ordinary **data** (empty circle).
> A **control parameter** is a **flag** (filled circle) that affects **which path is taken**.
> Example: `"OK funds"` is returned as a control flag so the parent module "now knows that it can generate the cheque."

### 2.3 Class Diagram

> "Used to show the **hierarchical relationship between classes**, especially when there is inheritance, abstraction and/or polymorphism."

**Notation — three compartments:**

```
┌─────────────────────┐
│      ClassName      │   ← top:    class name
├─────────────────────┤
│  shape:    string   │   ← middle: attributes
│  colour:   string   │
│  taste:    string   │
├─────────────────────┤
│  __init__()         │   ← bottom: methods
│  Eat()              │
│  Drink()            │
└─────────────────────┘
```

**Inheritance notation:**

- Pseudocode: `subclass VirtualLibrary is LibrarySystem { … }`
- Python: `class VirtualLibrary(LibrarySystem):`

**Worked example — Library System:**

`LibrarySystem` is the parent. Two subclasses inherit from it:

| Subclass | Additional attributes |
|---|---|
| `VirtualLibrary` | website URL, copies, regional restrictions |
| `PortableLibrary` | vehicle registration, driver licence |

> **Why subclass at all?** "Adding all these items to the `LibrarySystem` class would make it **enormous**. The solution is **inheritance and polymorphism**."

**Multiplicity**: In the NESA specifications, class diagrams may show relationships with multiplicity — e.g. a Student must study **1 or more** subjects, while a Subject can have **0 or more** students enrolled. In your class materials, multiplicity is handled instead by **subclassing**. Know both.

### 2.4 The DFD → Structure Chart → Class → Python Pipeline

> This mapping is directly examinable.

| Source | Becomes |
|---|---|
| The name of the system on the **Level 0 DFD** | The **class name** |
| The **Level 1 DFD** process names | The **method names** |
| The **data items on the data flows** | The **attributes / variables** |
| The **control box** of the structure chart | The **class name** |
| The **modules below** the control box | The **methods** |

**Worked skeleton — LibrarySystem:**

```python
class LibrarySystem:
    def __init__(self, admin, teachers, books):
        self.adminstaff    = admin
        self.teachingstaff = teachers
        self.books         = books

    def BorrowBook(self, BookNumber, StudentID, StudentName):
        ...
```

> **Deliberate error planted in the class materials**: the source version reads `def __init__(admin, teachers, books):` — **missing `self`**. In Python, the first parameter of an instance method must be `self`, which refers to the object being created. Without it, the first argument passed is bound to `admin` and the code fails. The corrected version is shown above.

---

## 3. OOP Design Processes and Approaches

| Approach | Definition |
|---|---|
| **Top-down** | "Starts with the **general concept** and repeatedly breaks it down into its component parts — from the **abstract to the specific**" |
| **Bottom-up** | "Starts with the **component parts** and repeatedly combines them to achieve the general concept — from the **specific to the abstract**" |
| **Façade pattern** | "An object that serves as a **front-facing interface masking** more complex underlying or structural code." Useful when a system is very complex, has many interdependent classes, or the source code is unavailable. Reduces complexity and dependencies; provides a **single entry point** |
| **Agility** | "Divide the problem into **small chunks**, tested both individually and together, added to the main program as they prove their stability" — a rapid **Design → Build → Test** cycle |

> **In practice, top-down and bottom-up are combined**: identify domain objects and refine them (top-down), then compose them into the system (bottom-up).

**Information hiding / encapsulation in design**: "You do not expose the implementation details of your code, but instead provide **well-behaved methods**."

> **Confusing pair — Façade vs Abstraction**
> **Abstraction** is a *principle* — hide unnecessary detail.
> **Façade** is a specific *design pattern* — one object that provides a simplified interface to a whole subsystem.
> Façade is one way of achieving abstraction.

---

## 4. Algorithm Effectiveness Criteria

> Ten criteria. Expect to be asked to **apply** several to a given algorithm or project.

| Criterion | Definition |
|---|---|
| **Correctness** | Checking if the code does what it is supposed to do — it shouldn't break or give weird answers |
| **Efficiency** | How **fast** the code runs and how much **memory** it needs (time and space complexity) |
| **Readability & maintainability** | Like a well-written story that is easy to understand, so other people can make changes without getting confused |
| **Scalability** | Whether the code can handle bigger and bigger tasks without getting slow or breaking |
| **Robustness** | The code can handle **unexpected** inputs and events without crashing |
| **Portability** | Works on different computers and platforms without needing lots of changes |
| **Testing** | Trying out the code to make sure it does what it should and has no bugs |
| **Security** | Only the right people can see or change important information — input validation, injection prevention |
| **Documentation** | A user manual for the code — how to use it and what everything does |
| **Feedback and iteration** | Making the code better over time with suggestions and changes |

> **Confusing pair — Robustness vs Correctness**
> **Correctness** = gives the right answer for **valid** input.
> **Robustness** = doesn't crash on **invalid or unexpected** input.
> A program can be correct but not robust: it calculates properly, then dies when someone types "abc" into an age field.

### 4.1 Why OOP Is Effective

| Benefit | Explanation |
|---|---|
| **Reusability** | Methods and classes can be reused across the program and in other projects — saves time |
| **Readability** | Code organised around real-world entities is easier to read and understand |
| **Maintainability** | Changes are localised to one class rather than scattered |
| **Code optimisation** | "A technique that helps make programs run faster and use fewer resources. Often performed at the **end** of the development stage. It **reduces readability** but improves performance" |

> **The trade-off to state in an exam**: optimisation improves **efficiency** at the cost of **readability and maintainability**. That is why it is done last.

---

## 5. Collaboration in Software Development

| Factor | How it helps |
|---|---|
| **Consistency** | "Speaking the same language within a team" — the same coding style and conventions (e.g. camel case `playerName`) |
| **Code commenting** | "Helpful notes for your teammates" — reduces the need for back-and-forth explanation |
| **Version control** | "A shared timeline of your team's progress" (Git) — track changes, collaborate, revert |
| **Feedback** | "A support network within your team" — catch errors, learn techniques |

> "By promoting consistency, encouraging code commenting, utilising version control, and fostering a culture of feedback, teams can work more efficiently and deliver higher-quality software together."

*Version control is covered in depth in [[Programming_For_The_Web]] §5.*

---

## 6. HSC Exam Response Structures

### Common Question Types

| Question type | How to answer |
|---|---|
| **"Define [OOP term]"** | Give the definition from §1 **plus** a one-line code or real-world example |
| **"Explain how inheritance improves maintainability"** | Define inheritance → mechanism (child reuses parent code) → effect (change once, applies everywhere) → link to an effectiveness criterion |
| **"Convert this DFD into a class structure"** | Level 0 name = class · Level 1 processes = methods · data flows = attributes |
| **"Assess the effectiveness of this algorithm"** | Pick 3–4 criteria from §4, apply each with evidence from the code, then judge |
| **"Justify the choice of OOP for this problem"** | Use modularity / data management / maintainability (§1.5), then contrast with procedural |

### Paragraph Scaffold

```
Topic sentence (define the term)
  → explain the mechanism (how it actually works)
  → apply to a scenario (your D&D app / Wicked Problems project / given case)
  → link to a syllabus concept (an effectiveness criterion, or maintainability)
```

---

## 7. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **Class** | The blueprint | **Object** — one instance built from it |
| **Object** | One instance with its own data | **Class** — the template |
| **Instantiation** | The **act** of creating an object | The object itself |
| **Attribute** | Data belonging to an object | **Method** — an action it can perform |
| **Method** | A function inside a class | A standalone function (not tied to a class) |
| **Constructor** (`__init__`) | Runs automatically when an object is created | An ordinary method (must be called) |
| **Encapsulation** | Bundling data + methods and hiding internals | **Abstraction** — showing only essentials |
| **Abstraction** | Hiding complexity from the user | **Encapsulation** — the mechanism that enables it |
| **Inheritance** | Child class reuses parent's properties/methods | **Generalisation** — extracting a superclass *from* existing classes |
| **Generalisation** | Creating a superclass from common features | **Inheritance** — using it |
| **Polymorphism** | Same method call, different behaviour by class | **Overriding** — one *form* of polymorphism |
| **Overriding** | Child redefines a parent's method | **Overloading** — same name, different parameters |
| **Superclass / base / parent** | The class being inherited **from** | **Subclass / derived / child** — the one inheriting |
| **Message passing** | Objects calling each other's methods | Data flow in a DFD |
| **`self`** | Reference to the current object instance | The class itself |
| **Empty circle** (structure chart) | A **data** parameter | **Filled circle** — a **control** flag |
| **Level 0 DFD** | Whole-system overview → **class name** | **Level 1** — processes → **method names** |
| **Top-down** | General → specific | **Bottom-up** — specific → general |
| **Façade pattern** | Simple interface over a complex subsystem | Abstraction (the general principle) |
| **Correctness** | Right answer for valid input | **Robustness** — survives invalid input |
| **Efficiency** | Speed and memory use | **Scalability** — coping as size grows |
| **Code optimisation** | Making it faster; **reduces readability** | Refactoring (improves readability) |
| **Modularity** | How easily code splits into reusable parts | Maintainability (ease of change) |

---

## 8. Key Definitions Quick Reference

| Term | One-Line Definition |
|---|---|
| Object | Self-contained unit of data (attributes) and functionality (methods) |
| Class | Blueprint or template for creating objects |
| Encapsulation | Bundling data and methods into one unit and hiding internal state |
| Abstraction | Hiding complex implementation and showing only essential features |
| Inheritance | A derived class inheriting properties and behaviours from a base class |
| Generalisation | Extracting common features into a more general superclass |
| Polymorphism | Different classes responding differently to the same method call |
| Overriding | A subclass redefining an inherited method |
| Attribute | A data property belonging to an object |
| Method | A function defined within a class |
| Instantiation | Creating an object from a class |
| Message passing | Objects communicating by calling each other's methods |
| Constructor | Method that runs automatically when an object is instantiated |
| DFD | Diagram showing the flow of data among components; excludes actors |
| Structure chart | Models the top-down hierarchy of processes and data movement |
| Class diagram | Shows hierarchical relationships between classes |
| Control parameter | A flag affecting which execution path is taken |
| Top-down design | From the abstract to the specific |
| Bottom-up design | From the specific to the abstract |
| Façade pattern | An interface masking more complex underlying code |
| Agility | Small chunks designed, built and tested in rapid cycles |
| Modularity | How easily a program breaks into reusable modules |
| Maintainability | How simply code can be updated, debugged and scaled |
| Code optimisation | Making programs faster at the cost of readability |
| Version control | A shared timeline of a team's changes |

---

## 9. Quick Revision Checklist

- [ ] Define all four pillars and explain how they group into protect/hide vs reuse/vary
- [ ] Class vs object vs instantiation
- [ ] Write a class with a constructor, attributes, methods and a subclass
- [ ] Explain why the missing `self` breaks the LibrarySystem constructor
- [ ] DFD symbols and the verb-phrase / noun-phrase rule
- [ ] Structure chart symbols — especially empty vs filled circle
- [ ] Class diagram three compartments and inheritance notation
- [ ] Run the DFD → class → method → attribute pipeline on a given diagram
- [ ] Four design approaches, including the façade pattern
- [ ] All 10 effectiveness criteria, and can apply 3–4 to a given algorithm
- [ ] Four collaboration factors
- [ ] Justify OOP vs procedural using modularity, data management, maintainability

---

> **See also:** [[Programming_Fundamentals]] | [[Mechatronics]] | [[Programming_For_The_Web]] | [[Software_Automation]] | [[Secure_Software_Architecture]] | [[MOC]]
