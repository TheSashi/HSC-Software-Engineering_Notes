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

> **Year 12, Unit 6** | AI vs ML, types of machine learning, MLOps, when to use each regression model, neural networks and decision trees, and the ethics of automation.

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

> **Supplementary clarification — expert system:** A traditional expert system stores domain-specific facts and human-written IF–THEN rules, then applies those rules (often through an inference engine) to reach a conclusion or recommendation. It is AI, but not ML when it follows fixed rules rather than learning patterns from training examples; a hybrid system may combine both. Your SE source notes use expert systems as an example of AI that is not ML, but this longer explanation is supplementary rather than a new separate syllabus point.

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
> **Validation** = checking a model on a separate set of examples that were not used to fit its learned values. During development, these results help compare or tune models and check whether performance generalises beyond the training examples; a large drop from training performance can signal overfitting. In workflows that distinguish a final test set, keep that set for an independent final check. This is model validation, not input validation, which checks whether a submitted value has an allowed type, format or range. In the Enterprise Computing comparison notes, “validation” also means checking data quality and whether visualisation values match the source. Keep these three contexts separate; that last meaning is a comparison clarification, not a separate confirmed Software Engineering requirement.

---

## 3. Regression Algorithms

> **NESA scope**: "Linear regression and polynomial regression algorithms are used to **predict values in a continuous range**. **Logistic regression is used for classification problems.** Students should know how to **design programs which use and apply** these algorithms but are **not expected to implement (or code) these complex algorithms.**"

**Choose by the kind of answer you need and the pattern in the data:**

| Model | Best used when... | Why / practical note |
|---|---|---|
| **Linear regression** | The outcome is a continuous number and the plotted relationship is roughly a straight trend. | Useful for a simple, interpretable estimate when the change is approximately steady. |
| **Polynomial regression** | The outcome is a continuous number and the plotted relationship has a clear curve. | Captures a curved trend; use only when the curve reflects the data, not random noise. |
| **Logistic regression** | The outcome is one of two categories, such as yes/no or pass/fail, and you want a probability. | Produces a probability from 0 to 1; a chosen threshold turns it into a class. Despite its name, this is for classification, not a continuous-value prediction. |
| **K-nearest neighbours (KNN) regression** | The outcome is a number and similar, nearby examples are likely to have similar results. | Predicts from the target values of the nearest examples instead of fitting one global equation. A small K is more sensitive to local variation; a larger K gives smoother predictions. |
| **Decision-tree regression** | A numerical prediction can be explained through clear feature-based branches, and interpretability matters. | The tree is easy to follow, but can overfit; pruning helps control this. See §4.2. |

> **Fast choice:** yes/no outcome → logistic. Numeric outcome → straight pattern → linear; clear curve → polynomial; similar nearby cases → KNN; transparent feature-based branches → decision tree.
>
> The straight-versus-curved rule and logistic classification purpose are stated in SA2. The KNN and decision-tree rows summarise the practical implications of their methods described in SA2/SA3.

**Program-design reminder:** NESA expects you to design a program that applies an appropriate algorithm, not code the complex maths. Focus on the model choice, input data, and predicted output.

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
| **"Choose a regression model"** | Identify the outcome and data pattern → select the model whose best-use conditions fit → justify the choice |
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
| **Linear regression** | Best for continuous numeric outcomes with a roughly straight trend | **Logistic** — yes/no classification |
| **Polynomial regression** | Best for continuous numeric outcomes with a clear curved trend | Linear (roughly straight trend) |
| **Logistic regression** | Best for yes/no classification when a probability is useful | Linear/polynomial/KNN (continuous numeric prediction) |
| **KNN** | Best for numeric predictions when similar nearby examples tend to have similar results | Global trend models such as linear/polynomial |
| **Line of best fit** | A modelled trend that summarises the relationship in plotted data | The raw data points |
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
| Regression | Using data to predict an outcome; the model choice depends on whether the target is numeric or a class |
| Line of best fit | A trend used to represent the relationship between plotted data points |
| Linear regression | Use for a continuous numeric outcome with a roughly straight trend |
| Polynomial regression | Use for a continuous numeric outcome with a clear curved trend |
| Logistic regression | Use for yes/no classification; produces a probability from 0 to 1 |
| Sigmoid | The S-shaped curve produced by logistic regression |
| KNN regression | Use when similar nearby examples are expected to have similar numeric outcomes |
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
- [ ] Choose a suitable regression model from the outcome type and data pattern
- [ ] Explain why logistic regression is for yes/no classification and how a probability threshold is used
- [ ] Explain when KNN is useful and how changing K affects the prediction
- [ ] Explain the benefit and overfitting risk of decision-tree regression
- [ ] Describe how a program applies a chosen model to inputs to produce predictions, without implementing its maths
- [ ] Neural network architecture; training vs execution cycle
- [ ] Weighting vs threshold
- [ ] Decision trees, overfitting and pruning
- [ ] Accuracy vs interpretability trade-off
- [ ] The Goldilocks Zone and four behavioural influences on AI
- [ ] All five required ethical impact areas
- [ ] Fake news, astroturfing, dataset and human bias
- [ ] Argue a qualified "to what extent" judgement with human oversight

---
