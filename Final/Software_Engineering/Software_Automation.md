---
title: Software Automation
subject: Software Engineering
type: final
unit: Year 12
syllabus_topic: Software Automation
tags:
  - software-engineering
  - software-automation
  - machine-learning
  - hsc
  - final
  - exam-ready
  - year-12
aliases:
  - AI vs ML
  - Machine Learning
  - Regression
  - Neural Networks
---

# Software Automation — HSC Final Notes

> **Year 12, Unit 6** | AI vs ML, types of machine learning, MLOps, regression algorithms with worked calculations, neural networks and decision trees, and the ethics of automation.

---

## 1. AI vs Machine Learning

| Term | Definition |
|---|---|
| **Artificial Intelligence (AI)** | "A **broad field** of computer science focused on creating systems that can perform tasks requiring human-like intelligence. AI encompasses reasoning, problem-solving, perception, language understanding, and learning. It includes **rule-based systems, expert systems, robotics, and machine learning**" |
| **Machine Learning (ML)** | "A **subset of AI** that enables computers to **learn from data** and improve their performance over time **without being explicitly programmed**. It involves algorithms that identify patterns, make decisions, and adapt based on experience" |

```
┌─────────────────────────────────────────┐
│  ARTIFICIAL INTELLIGENCE                │
│  reasoning · perception · robotics ·    │
│  expert systems · rule-based systems    │
│   ┌───────────────────────────────┐     │
│   │  MACHINE LEARNING             │     │
│   │  learns from data, no explicit│     │
│   │  programming                  │     │
│   │   ┌─────────────────────┐     │     │
│   │   │  NEURAL NETWORKS /  │     │     │
│   │   │  DEEP LEARNING      │     │     │
│   │   └─────────────────────┘     │     │
│   └───────────────────────────────┘     │
└─────────────────────────────────────────┘
```

> **The relationship to state in an exam**: ML is a **subset** of AI. AI is the broader concept; ML is one **data-driven** way of achieving it. Not all AI is ML — a rule-based expert system is AI but is explicitly programmed, so it is not ML.

### 1.1 Types of Machine Learning

| Type | Definition |
|---|---|
| **Supervised** | "Taught using **labeled examples** — finds patterns from past examples to make predictions" |
| **Unsupervised** | "Given a lot of data but **no answers**. It figures out patterns by itself" |
| **Semi-supervised** | "**Some** labeled examples but also a lot of **unlabeled** data" |
| **Reinforcement** | "Learns by **trial and error** and gets **rewards or penalties** based on its actions" |

> **Confusing pair — Supervised vs Unsupervised**
> **Supervised** = you give the machine the **answers** during training ("this photo is a cat"). Used for **prediction and classification**.
> **Unsupervised** = you give it **no answers** and it finds structure itself. Used for **clustering and grouping**.
> The word "supervised" refers to whether a human supervised the *labelling*, not the *training*.

**Worked classifications:**

| Task | ML type |
|---|---|
| Grouping fruit with no labels given | **Unsupervised** |
| Maths problems supplied with their answers | **Supervised** |
| A note-taking task with some labelled examples | **Semi-supervised** |
| A game-playing agent improving through rewards | **Reinforcement** |
| Spam filter trained on emails marked spam/not spam | **Supervised** |

### 1.2 Automation That ML Supports

| Approach | Definition |
|---|---|
| **DevOps** | Combines software **dev**elopment and IT **op**erations. Automation manages deployment, monitors systems and fixes errors; ML predicts failures |
| **RPA** (Robotic Process Automation) | Automates **repetitive tasks** — data entry, invoices, customer responses. Bots learn from past actions |
| **BPA** (Business Process Automation) | Automates **entire workflows**, integrating multiple systems and departments |

> **Confusing pair — RPA vs BPA**
> **RPA** automates individual **tasks** (a bot copying data between two screens).
> **BPA** automates the whole **process** end to end (the entire invoice approval workflow across departments).
> RPA is narrow and bolts onto existing systems; BPA is broad and usually requires system integration.

---

## 2. MLOps — Machine Learning Automation Through DevOps

> **NESA definition**: "**MLOps** is the automated process of **designing, training and deploying** machine learning models. It borrows many of the same principles and practices used in DevOps, bringing together the teams involved in developing machine learning models and the operational teams involved in deploying and supporting the models in production."

> **Students should know the three stages of MLOps.**

### Stage 1 — Design

- Defining the **business problem** to be solved
- **Refactoring** the business problem into a **machine learning problem**
- Defining **success metrics**
- Researching **available data**

### Stage 2 — Model Development

- **Data wrangling**
- **Feature engineering**
- **Model training**
- **Model testing and validation**

### Stage 3 — Operations

- **Model deployment**
- Supporting operations and use
- **Monitoring model performance**

```
DESIGN                  MODEL DEVELOPMENT          OPERATIONS
business problem   →    data wrangling        →    deployment
ML problem              feature engineering        support
success metrics         training                   monitoring
available data          testing & validation
```

> **Key vocabulary**
> **Data wrangling** = cleaning and restructuring raw data into a usable form (handling missing values, fixing formats, removing duplicates).
> **Feature engineering** = choosing and constructing the input variables ("features") the model will learn from. Often matters more to accuracy than the choice of algorithm.
> **Validation** = testing the model on data it has **never seen** during training, to check it generalises rather than memorises.

---

## 3. Regression Algorithms

> **NESA scope**: "Linear regression and polynomial regression algorithms are used to **predict values in a continuous range**. **Logistic regression is used for classification problems.** Students should know how to **design programs which use and apply** these algorithms but are **not expected to implement (or code) these complex algorithms.**"

**Regression generally**: "Using past and present mathematical data to predict future values. Also known as finding the **Line of Best Fit**."

| Type | Purpose | Shape |
|---|---|---|
| **Linear** | "Drawing a straight line that helps guess" a value; good where one thing increases as another increases | Straight line |
| **Polynomial** | "Finds patterns that aren't straight — draws a **curvy** line" | Curve |
| **Logistic** | "Helps computers make **yes/no** decisions, like 'Will it rain?'" | S-curve (sigmoid) |
| **K-Nearest Neighbours (KNN)** | "Group things by looking at what's **nearby**" | Not smooth |

> **The choice rule**: plot the data first. **Curvy → polynomial. Straight → linear. Yes/no outcome → logistic.**

### 3.1 Linear Regression — the Least Squares Method

**Goal**: find the equation of the straight line of best fit, **y = mx + b**

**Method**: build a table of `x | y | xy | x²`, sum each column, then:

```
      n·Σxy − Σx·Σy                  Σy − m·Σx
m = ───────────────            b = ─────────────
      n·Σx² − (Σx)²                       n
```

#### Worked Example 1

Data: x = [1, 2, 3, 4, 5], y = [2, 3, 5, 6, 8]

| x | y | xy | x² |
|---|---|---|---|
| 1 | 2 | 2 | 1 |
| 2 | 3 | 6 | 4 |
| 3 | 5 | 15 | 9 |
| 4 | 6 | 24 | 16 |
| 5 | 8 | 40 | 25 |
| **Σ = 15** | **Σ = 24** | **Σ = 87** | **Σ = 55** |

n = 5

```
m = (5 × 87 − 15 × 24) / (5 × 55 − 15²)
  = (435 − 360) / (275 − 225)
  = 75 / 50
  = 1.5

b = (24 − 1.5 × 15) / 5
  = (24 − 22.5) / 5
  = 1.5 / 5
  = 0.3
```

> **y = 1.5x + 0.3**

**Function table:**

| x | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| y | 1.8 | 3.3 | 4.8 | 6.3 | 7.8 |

#### Worked Example 2 — ⚠️ correcting an error in the class worksheet

Data: x = [2, 4, 6, 8], y = [3, 4, 7, 9]

| x | y | xy | x² |
|---|---|---|---|
| 2 | 3 | 6 | 4 |
| 4 | 4 | 16 | 16 |
| 6 | 7 | 42 | 36 |
| 8 | 9 | 72 | 64 |
| **Σ = 20** | **Σ = 23** | **Σ = 136** | **Σ = 120** |

n = 4

> **⚠️ The worksheet recorded Σx = 22. The correct value is Σx = 20** (2 + 4 + 6 + 8 = 20). That single error produced the answers **m = −9.5, b = 58**, which are internally consistent with Σx = 22 but wrong for this data.
>
> **Why you should have caught it**: the y values **rise** (3 → 9) as x rises, so the slope **must be positive**. A line predicting y = 39 down to y = −18 cannot be a line of best fit for data running 3 to 9. **Always sanity-check the sign of your slope against the trend of the data.**

**Correct working:**

```
m = (4 × 136 − 20 × 23) / (4 × 120 − 20²)
  = (544 − 460) / (480 − 400)
  = 84 / 80
  = 1.05

b = (23 − 1.05 × 20) / 4
  = (23 − 21) / 4
  = 2 / 4
  = 0.5
```

> **y = 1.05x + 0.5**

**Function table (correct):**

| x | 2 | 4 | 6 | 8 |
|---|---|---|---|---|
| y | 2.6 | 4.7 | 6.8 | 8.9 |
| *actual* | *3* | *4* | *7* | *9* |

The fitted values now sit close to the actual data, which is what a line of best fit should do.

### 3.2 Polynomial Regression — the Least Squares Matrix Method

**Goal**: find the equation of the curve **y = ax² + bx + c**

Build the LHS matrix (`x, x², x³, x⁴`) and RHS matrix (`y, xy, x²y`), sum each column, then solve the three simultaneous equations:

```
Σy    = a·Σx² + b·Σx  + c·n
Σxy   = a·Σx³ + b·Σx² + c·Σx
Σx²y  = a·Σx⁴ + b·Σx³ + c·Σx²
```

Eliminate **c** first (it is normally the easiest), solve for **a** and **b**, then substitute back.

#### Worked Example 3

Data: x = [1, 2, 3, 4, 5], y = [2, 5, 10, 17, 26], n = 5

| x | x² | x³ | x⁴ | | y | xy | x²y |
|---|---|---|---|---|---|---|---|
| 1 | 1 | 1 | 1 | | 2 | 2 | 2 |
| 2 | 4 | 8 | 16 | | 5 | 10 | 20 |
| 3 | 9 | 27 | 81 | | 10 | 30 | 90 |
| 4 | 16 | 64 | 256 | | 17 | 68 | 272 |
| 5 | 25 | 125 | 625 | | 26 | 130 | 650 |
| **Σ 15** | **Σ 55** | **Σ 225** | **Σ 979** | | **Σ 60** | **Σ 240** | **Σ 1034** |

> **⚠️ The worksheet recorded Σx³ = 255. The correct value is 225** (1 + 8 + 27 + 64 + 125 = 225).

**Answer: y = x² + 1**

**Verification** — substitute a = 1, b = 0, c = 1 into all three equations:

| Equation | Check |
|---|---|
| 60 = 55(1) + 15(0) + 5(1) | 55 + 0 + 5 = **60** ✓ |
| 240 = 225(1) + 55(0) + 15(1) | 225 + 0 + 15 = **240** ✓ |
| 1034 = 979(1) + 225(0) + 55(1) | 979 + 0 + 55 = **1034** ✓ |

All three hold exactly, so **y = x² + 1** is correct.

**Function table:**

> **⚠️ The worksheet's table was filled in using x² + x + 1** (giving 3, 7, 13, 21, 31), not the derived equation x² + 1. Use the equation you actually solved for.

| x | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| **y = x² + 1** | **2** | **5** | **10** | **17** | **26** |

This is a **perfect fit** — the curve passes exactly through every data point.

#### Worked Example 4

Data: x = [2, 4, 6, 8, 10], y = [4, 12, 18, 22, 25], n = 5

| Σx | Σx² | Σx³ | Σx⁴ | Σy | Σxy | Σx²y |
|---|---|---|---|---|---|---|
| 30 | 220 | 1800 | 15664 | 81 | 590 | 4764 |

*(These sums in the worksheet are all correct.)*

**Simultaneous equations:**

```
 81  = 220a  +   30b  +   5c
590  = 1800a +  220b  +  30c
4764 = 15664a + 1800b + 220c
```

**Solving gives:**

> **y = −0.2143x² + 5.1714x − 5.4**

**Function table:**

| x | 2 | 4 | 6 | 8 | 10 |
|---|---|---|---|---|---|
| **fitted y** | 4.09 | 11.86 | 17.91 | 22.26 | 24.89 |
| *actual y* | *4* | *12* | *18* | *22* | *25* |

> Note the **negative `a`** — the curve bends downward, matching data that rises steeply then flattens off. A negative coefficient on x² is entirely normal and indicates a concave-down curve.

### 3.3 Logistic Regression

**Aim**: "Calculate the **probability** of something being a **yes (1) or no (0)**."

Produces a **sigmoid / S-curve running from 0 to 1**.

**Worked example — passing grade:**

- The passing grade is approximately **3.5**, where the curve crosses the **0.5 probability threshold**
- A mark of **4.5** → approximately **50%** probability
- A mark of **7** → approximately **95%** probability

> **Why an S-curve and not a straight line?** A straight line would eventually predict probabilities above 1 and below 0, which are meaningless. The sigmoid **asymptotes** — it approaches 0 and 1 but never exceeds them.

> **The 0.5 threshold** is the decision boundary: above it the model predicts "yes", below it "no".

### 3.4 K-Nearest Neighbours (KNN)

> "KNN regression **does not make data fit a formula**. Instead, it highlights **K points within range** of the Line of Best Fit. The line **will not be smooth**."

**How it works**: to predict a value, find the **K nearest** data points and **average** them.

**Effect of K**: increasing K changes which points are considered near the line — a larger K gives a smoother but less locally sensitive result; a smaller K follows the data closely but is more affected by noise.

> **The key contrast**: linear and polynomial regression produce an **equation**. KNN produces **no equation at all** — it just looks at neighbours each time it is asked. That is why the output line is not smooth.

### 3.5 Programming Regression

**Linear (Python, from first principles):**

```python
n   = len(x)
Sx  = sum(x);  Sy = sum(y)
Sxy = sum(a*b for a, b in zip(x, y))
Sx2 = sum(a*a for a in x)

m = (n*Sxy - Sx*Sy) / (n*Sx2 - Sx**2)
b = (Sy - m*Sx) / n
print(f"y = {m}x + {b}")
```

**Polynomial (using a library):**

```python
import numpy
a, b, c = numpy.polyfit(x, y, 2)      # 2 = degree of the polynomial
```

**Linear regression using ML frameworks (NESA example):**

```python
import numpy as np
from sklearn.linear_model import LinearRegression

x = np.array([[2], [4], [6], [8], [10], [12], [14], [16]])
y = np.array([1, 3, 5, 7, 9, 11, 13, 15])

model = LinearRegression()
model.fit(x, y)                 # determine the line of best fit

y_prediction = model.predict(4)     # known data      → 3
y_prediction = model.predict(4.5)   # unknown data    → 3.5
```

> Note the pattern: **create the model → `fit()` it to the data → `predict()` new values.** This three-step pattern is what "designing a program that applies the algorithm" means — you are not expected to code the maths itself.

---

## 4. Neural Networks and Decision Trees

### 4.1 Neural Networks

> "A type of machine learning model **inspired by the human brain**. Layers of interconnected neurons — effective for recognising patterns in large, complex datasets."

**NESA description**: "Neural networks were designed to **mimic the processing inside the human brain**. They consist of a series of **interconnected nodes (artificial neurones)**. Each neurone can accept a binary input signal and potentially output another signal to connected nodes."

**Architecture:**

```
INPUT LAYER  →  HIDDEN LAYER(S)  →  OUTPUT LAYER
```

#### The Training Cycle

> "Internal **weightings** and **threshold values** for each node are determined in the initial **training cycle**. The system is exposed to a series of inputs with **known responses**. **Linear regression with backward chaining** is used to iteratively determine the set of unique values required for output. Regular exposure to the training cycle results in **improved accuracy and pattern matching**."

#### The Execution Cycle

> "Signal strength between nodes with the strongest weightings are **thicker**, representing a **higher priority** in determining the final output. The execution cycle **follows the training cycle** and utilises the internal values developed during training to determine the output."

| | **Training cycle** | **Execution cycle** |
|---|---|---|
| Purpose | **Determine** the weightings and thresholds | **Use** them to produce an output |
| Input | Data with **known responses** | New, unseen data |
| When | First, and repeatedly | After training |

> **Confusing pair — Weighting vs Threshold**
> A **weighting** is how much **importance** a connection carries — strong connections have high weights.
> A **threshold** is the value an accumulated signal must **exceed** before the neurone fires.

**Strengths and weaknesses:**

| Strengths | Weaknesses |
|---|---|
| Excel at **image recognition** and NLP | Need **lots of data** and compute |
| Handle very complex patterns | Often "**black boxes**" — lack interpretability |
| Improve with more training | Hard to explain a decision to a regulator or user |

### 4.2 Decision Trees

> "Splits data into **branches based on feature-based rules**, forming a **tree-like structure**."

- Used for **classification and regression**
- "**Clear and interpretable**"
- "Can suffer from **overfitting** if not properly pruned"

> **Overfitting** = the model learns the training data *too* precisely, including its noise and quirks, so it performs brilliantly on data it has seen and badly on anything new. **Pruning** cuts back branches that only exist to fit noise.

### 4.3 Choosing Between Them

| Model | Best suited to |
|---|---|
| **Neural networks** | Self-driving cars, recommendation engines, face recognition, image classification, spam detection |
| **Decision trees** | Tasks needing transparent reasoning — the semi-supervised note task, fruit grouping, maths-with-answers, spam filtering |

> **The trade-off to state in an exam**: neural networks give **higher accuracy on complex data** but are **black boxes**. Decision trees are **less powerful** but **interpretable** — you can trace exactly why a decision was made. Where accountability matters (medicine, lending, law), interpretability may outweigh raw accuracy.

### 4.4 Application Areas

| Area | Algorithms used |
|---|---|
| **Data analysis and forecasting** | **KNN regression** averages similar points; **decision trees** give transparent decisions |
| **Virtual personal assistants** | **Logistic regression** classifies intent; **neural networks** power NLP |
| **Image recognition** | **Logistic regression** for binary classification; **neural networks (CNNs)** detect edges and shapes |

---

## 5. Psychology and Human Behaviour

> The syllabus requires exploring "how patterns in **human behaviour** influence ML and AI."

**Core terms**: Stimulus · Response · Arousal · Impulse · Regulation

**Psychological responses**: Regression · Conditioning · Habituation · Sensitisation · Flight-Fight-Fawn · Stress

> **The "Goldilocks Zone"**: the band "between complete **impulsivity** and total **regulation**" — the state IT companies design their products to exploit. Too impulsive and the user acts erratically; too regulated and they close the app. The engagement sweet spot sits between.

**Four ways human behaviour influences AI:**

1. **Psychological response**
2. **Acute stress response**
3. **Cultural protocols**
4. **Belief systems**

> **Why this matters technically**: training data is generated by humans, so human bias, cultural assumptions and belief systems are **encoded into the dataset**. The model then reproduces and amplifies them.

---

## 6. Ethics and the Limits of Automation

> **The driving question**: "To what extent should software automation rule the world?"

**Required impacts to address:**

- **Safety of workers**
- **People with disability**
- **Nature and skills of employment**
- **Production efficiency, waste and the environment**
- **Economy and wealth distribution**

Plus: "how patterns in human behaviour influence ML and AI — psychological responses; acute stress response; cultural protocols; belief systems."

### 6.1 Benefits

| Area | Detail |
|---|---|
| **Worker safety** | AI image recognition detects **hazards** on construction sites and **defects** in manufacturing |
| **Disability access** | Screen readers; self-driving cars providing mobility |
| **Employment** | Repetitive tasks automated → demand rises for **data analysis, AI programming and tech-ethics** skills. Upskilling required |
| **Efficiency and environment** | ML catches errors early (less waste); AI energy management lowers carbon footprint |
| **Economy** | "AI can boost **productivity**, but raises concerns about **job displacement**. Wealth distribution may become **more unequal** unless governments invest in retraining" |

### 6.2 Risks and Manipulation

| Risk | Detail |
|---|---|
| **Fake news — 2016 US election** | Bot accounts and fake-news sites; algorithms "**amplified content aligned with existing views**"; social engineering exploited **cognitive biases** |
| **COVID vaccine misinformation** | Clickbait and fabricated testimony driving **vaccine hesitancy** |
| **Astroturfing** | Fake "grassroots" campaigns and fake accounts used to discredit or promote |
| **Bias** | The syllabus requires investigating "the effect of **human and dataset source bias**" |
| **Job displacement** | Automation removing roles faster than retraining can replace them |

> **Astroturfing** = manufacturing the appearance of spontaneous public support. The name is a joke on "grassroots" — it looks like grass, but it's fake.

### 6.3 The Judgement

**Human oversight is required.** Automation should be **bounded by human judgement**, not unchecked. A top-band answer weighs the ethical implications, acknowledges bias, and argues for safeguards and retraining rather than either uncritical enthusiasm or blanket rejection.

> **Note on the class task**: the SA4 assessment specified "**Do not use AI in this classroom task.**"

---

## 7. HSC Exam Response Structures

### Extended Response Scaffold — "To what extent should software automation rule the world?"

```
1. Define the concept          (AI / ML / automation, and their relationship)
2. Explain the mechanism       (how the system learns, how it is built)
3. Present benefits            with a concrete example
4. Present risks and limits    (bias, displacement, manipulation)
5. Judge "to what extent"      argue a balanced position with human oversight
```

> "**To what extent**" is asking for a **degree**, not a yes/no. Your thesis should contain a qualifier: *"Software automation should govern routine, high-volume and hazardous processes, but decisions affecting human rights, employment and safety must remain under human oversight."*

### Common Question Types

| Question type | How to answer |
|---|---|
| **"Distinguish AI from ML"** | Define both → state the subset relationship → give an example of AI that is **not** ML (rule-based expert system) |
| **"Classify this scenario's ML type"** | Ask: are the training examples **labelled**? Are there **rewards**? Then justify |
| **"Describe the three stages of MLOps"** | Design → Model development → Operations, with the four bullet points under each |
| **"Calculate the line of best fit"** | Build the `x, y, xy, x²` table → sum → apply the m and b formulas → **sanity-check the slope sign** |
| **"Compare neural networks and decision trees"** | Accuracy vs interpretability → data requirements → overfitting → judge by context |
| **"Explain the training and execution cycles"** | Training determines weightings/thresholds from known responses; execution uses them on new data |
| **"Discuss the ethics of automation"** | Cover all five required impact areas, then judge with human oversight |

---

## 8. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **AI** | Broad field of human-like intelligent systems | **ML** — a data-driven **subset** of AI |
| **Machine learning** | Learns from data without explicit programming | Rule-based AI (explicitly programmed) |
| **Supervised** | Trained on **labelled** examples | **Unsupervised** — no labels, finds patterns |
| **Semi-supervised** | Some labelled, mostly unlabelled | Supervised (all labelled) |
| **Reinforcement** | Learns by trial, error and reward | Supervised (learns from given answers) |
| **DevOps** | Development + IT operations | **MLOps** — the same idea applied to ML models |
| **RPA** | Automates individual repetitive **tasks** | **BPA** — automates whole **workflows** |
| **Data wrangling** | Cleaning and restructuring raw data | **Feature engineering** — choosing the inputs |
| **Feature engineering** | Constructing the input variables | Data wrangling (cleaning) |
| **Validation** | Testing on data never seen in training | Testing during training |
| **Linear regression** | Straight line; continuous prediction | **Logistic** — S-curve; classification |
| **Polynomial regression** | Curve; continuous prediction | Linear (straight line) |
| **Logistic regression** | Probability 0–1 for **yes/no** classification | Linear regression (continuous values) |
| **KNN** | No equation — averages nearby points | Linear/polynomial (produce an equation) |
| **Line of best fit** | The fitted equation | The raw data points |
| **Sigmoid** | S-shaped curve bounded by 0 and 1 | A straight line (unbounded) |
| **Neural network** | Layered interconnected nodes; black box | **Decision tree** — interpretable branching rules |
| **Weighting** | Importance of a connection | **Threshold** — the firing level |
| **Training cycle** | Determines weightings from known data | **Execution cycle** — applies them to new data |
| **Overfitting** | Memorises training data; fails on new data | Underfitting (too simple to capture the pattern) |
| **Pruning** | Cutting back tree branches to reduce overfitting | Training |
| **Astroturfing** | Fake grassroots campaigns | Genuine organic support |
| **Dataset bias** | Skew present in the training data | **Human bias** — skew in the people labelling it |

---

## 9. Key Definitions Quick Reference

| Term | One-Line Definition |
|---|---|
| Artificial intelligence | Broad field creating systems performing tasks requiring human-like intelligence |
| Machine learning | Subset of AI that learns from data without explicit programming |
| Supervised learning | Trained using labelled examples |
| Unsupervised learning | Finds patterns in data with no answers supplied |
| Semi-supervised learning | Some labelled examples plus much unlabelled data |
| Reinforcement learning | Learns by trial and error with rewards and penalties |
| DevOps | Combining software development with IT operations |
| MLOps | Automated process of designing, training and deploying ML models |
| Data wrangling | Cleaning and restructuring raw data for use |
| Feature engineering | Selecting and constructing the model's input variables |
| RPA | Automation of repetitive individual tasks |
| BPA | Automation of entire business workflows |
| Regression | Using past and present data to predict future values |
| Line of best fit | The equation minimising the distance to all data points |
| Linear regression | Fitting a straight line, y = mx + b |
| Polynomial regression | Fitting a curve, y = ax² + bx + c |
| Logistic regression | Producing a 0–1 probability for classification |
| Sigmoid | The S-shaped curve produced by logistic regression |
| KNN | Predicting by averaging the K nearest data points |
| Least squares | Method minimising the sum of squared distances to the line |
| Neural network | Layers of interconnected nodes mimicking the brain |
| Training cycle | Determining weightings and thresholds from known responses |
| Execution cycle | Using trained values to determine output for new data |
| Weighting | The importance assigned to a connection between nodes |
| Threshold | The value an accumulated signal must exceed for a node to fire |
| Decision tree | Splits data into branches using feature-based rules |
| Overfitting | Fitting training data so closely the model fails on new data |
| Pruning | Removing branches to reduce overfitting |
| Astroturfing | Fake grassroots campaigns using fabricated accounts |
| Dataset bias | Systematic skew present in the training data |

---

## 10. Quick Revision Checklist

- [ ] Define AI and ML, and explain the subset relationship with an example of AI that isn't ML
- [ ] All four ML types, and classify a given scenario
- [ ] DevOps, RPA and BPA — and RPA vs BPA
- [ ] The **three stages of MLOps** and the four bullet points under each
- [ ] Choose between linear, polynomial and logistic for given data
- [ ] Compute a linear regression by hand — table, sums, m, b
- [ ] **Sanity-check the slope sign against the data trend**
- [ ] Set up the polynomial least-squares matrix and three simultaneous equations
- [ ] Explain the logistic sigmoid and the 0.5 threshold
- [ ] Explain why KNN produces no equation and an unsmooth line
- [ ] The create → fit → predict programming pattern
- [ ] Neural network architecture; training vs execution cycle
- [ ] Weighting vs threshold
- [ ] Decision trees, overfitting and pruning
- [ ] Accuracy vs interpretability trade-off
- [ ] The Goldilocks Zone and four behavioural influences on AI
- [ ] All five required ethical impact areas
- [ ] Fake news, astroturfing, dataset and human bias
- [ ] Argue a qualified "to what extent" judgement with human oversight

---

> **See also:** [[Programming_For_The_Web]] | [[Secure_Software_Architecture]] | [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Mechatronics]] | [[MOC]]
