---
tags: [software-engineering, year-12, hsc, software-automation, ai, machine-learning, regression, neural-networks, decision-trees, ethics]
aliases: [SE Automation, AI vs ML, Machine Learning, Regression, Neural Networks]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 12 Software Automation
created: 2026-07-15
updated: 2026-07-15
---

# Software Automation (AI/ML) — Year 12 SE

> Self-contained note on AI vs ML, types of ML, best-use guidance for regression models, decision trees & neural networks, the psychology/cognition links, and the ethics/limits of automation. Built from SA1–SA4 and the Student Version pptx. Every definition sourced. (Note: the SA0 .xlsx starter was not readable from the source set — flagged, not fabricated.)

---

## 1. AI vs ML Distinction (SA1)

- **Artificial Intelligence (AI):** "a broad field of computer science focused on creating systems that can perform tasks requiring human-like intelligence. AI encompasses reasoning, problem-solving, perception, language understanding, and learning. It includes rule-based systems, expert systems, robotics, and machine learning."
- **Machine Learning (ML):** "a subset of Artificial Intelligence (AI) that enables computers to learn from data and improve their performance over time without being explicitly programmed. It involves algorithms that identify patterns, make decisions, and adapt based on experience."
- **Relationship:** ML is a **subset** of AI. AI is the broader concept; ML is one (data-driven) way of achieving it.

### Types of ML (SA1)
- **Supervised:** "taught using labeled examples … finds patterns from past examples to make predictions."
- **Unsupervised:** "given a lot of data but no answers. It figures out patterns by itself."
- **Semi-Supervised:** "some labeled examples but also a lot of unlabeled data."
- **Reinforcement:** "learns by trial and error and gets rewards or penalties based on its actions."

### Regression types (overview; SA1)
SA1 names linear, logistic, K-nearest neighbours (KNN) and polynomial regression; the practical model-selection guide is in §2.

### Automation ML supports (SA1)
- **DevOps:** combines software dev + IT operations; automation manages deployment, monitors, fixes errors; ML predicts failures.
- **RPA (Robotic Process Automation):** automates repetitive tasks (data entry, invoices, customer responses); bots learn from past actions.
- **BPA (Business Process Automation):** automates entire workflows; integrates multiple systems/departments.

---

## 2. Choosing Regression Models (SA2)

| Model | Best used when... | Key reason |
|---|---|---|
| **Linear regression** | Predicting a continuous number from a roughly straight relationship. | Models a steady trend. |
| **Polynomial regression** | Predicting a continuous number from a clearly curved relationship. | Captures curvature that a straight trend misses. |
| **Logistic regression** | Classifying a yes/no outcome when a probability is useful. | Returns a probability from 0 to 1; a threshold gives the class. |
| **KNN regression** | Predicting a number when similar, nearby examples tend to have similar results. | Uses nearby examples rather than one global equation; K controls how local or smooth the prediction is. |
| **Decision-tree regression** | Predicting a number through understandable feature-based branches. | Transparent rules are useful when explanations matter; prune to reduce overfitting. See §3. |

SA2's explicit selection rule is to plot numeric data: use linear regression for a straight trend and polynomial regression for a curved trend. Logistic regression is for yes/no classification. The KNN rule above is the practical meaning of predicting from nearby examples.

---

## 3. Decision Trees, Neural Networks & Psychology (SA3 + Student)

- **Neural Networks:** "a type of machine learning model inspired by the human brain. Layers of interconnected neurons … effective for recognising patterns in large, complex datasets." Architecture: **Input layer → Hidden layer → Output layer**. Excel at image recognition, NLP, deep learning; need lots of data/compute; often "black boxes" (lack interpretability).
- **Decision Trees:** "splits data into branches based on feature-based rules, forming a tree-like structure." Used for classification and regression; "clear, interpretable"; "can suffer from overfitting if not properly pruned."
- **Suitability:** Neural Networks → self-driving, recommendations, face recognition, image/spam. Decision Trees → semi-supervised note task, fruit-grouping (unsupervised), math-with-answers (supervised), spam filter.
- **Application buckets:** Data Analysis & Forecasting (Regression KNN averages similar points; Decision Tree transparent decisions), Virtual Personal Assistants (Logistic classifies intent; Neural net powers NLP), Image Recognition (Logistic binary classification; Neural net CNN detects edges/shapes).

### Psychology / cognition links (Student)
- Terms: Stimulus, Response, Arousal, Impulse, Regulation.
- Psychological responses: Regression, Conditioning, Habituation, Sensitisation, Flight-Fight-Fawn, Stress.
- **"Goldilocks Zone":** "between complete impulsivity and total regulation" — the band IT companies exploit.
- Human behaviour influencing AI: psychological response, acute stress, cultural protocols, belief systems.

---

## 4. Ethics & Limits of Automation (SA4 + Student)

**Driving question:** "To what extent should software automation rule the world?"

Must address impacts on: **safety of workers; people with disability; nature/skills of employment; production efficiency, waste, environment; economy and wealth distribution.** Must explore "how patterns in human behaviour influence ML and AI … psychological responses; acute stress response; cultural protocols; belief systems." Note: "Do not use AI in this classroom task." [SA4]

### Benefits
- **Safety:** AI image recognition detects hazards (construction), defects (manufacturing).
- **Disability:** screen readers, self-driving cars for mobility.
- **Employment:** repetitive tasks automated → demand for data analysis, AI programming, tech-ethics skills; upskilling needed.
- **Efficiency/environment:** ML catches errors early (less waste); AI energy-management lowers carbon.
- **Economy:** "AI can boost productivity, but raises concerns about job displacement. Wealth distribution may become more unequal unless governments invest in retraining."

### Risks / manipulation
- **Fake news & 2016 US election:** bot accounts, fake-news sites; algorithms "amplified content aligned with existing views"; social engineering exploits cognitive biases.
- **COVID vaccine misinformation:** clickbait/fabricated testimony → hesitancy.
- **Astroturfing:** fake grassroots/fake accounts to discredit or promote.
- **Bias:** syllabus requires investigating "the effect of human and dataset source bias."
- **Human oversight implied:** weigh ethical implications, bias, need for retraining/safeguards — automation bounded by human judgement.

---

## 5. Coverage note
- **SA0 Starter (.xlsx)** is referenced in the Student pptx as a "tell a story with data" starter using `=COUNTIF` and charts, but the .xlsx was **not present in the readable source set** and could not be extracted. Not fabricated.
- The `Key Terms - Software Engineering.pdf` contains **HSC command terms only** (List/State/Define/Describe/Explain/Analyse/Justify/Evaluate; Create/Present/Design/Develop) — no AI/ML-specific vocabulary.

---
