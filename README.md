# 🚀 Learning Jev with Practical AI Applications

This repository is a hands-on learning series for understanding **Jev** through practical, real-world AI use cases.

Instead of learning Jev only through theory, we build small applications step by step and see how Jev can be used as a **structured decision-making layer** inside an AI system.

---

## 🤔 What is Jev?

Jev can be used when we want an AI system to make **structured decisions from unstructured text**.

For example:

```text
Customer Message
       ↓
      Jev
       ↓
Is it urgent? → Yes / No
Department?  → Billing / Technical / Account
Priority?    → Low / Medium / High
```

The important idea is:

> **Jev makes structured decisions, while our application decides what to do with those decisions.**

This makes Jev useful for classification, routing, prioritization, and decision-making workflows.

---

## 🎯 What Will You Learn?

By going through these notebooks, you will learn:

* What Jev is and where it fits in an AI application
* How to use Jev's main primitives
* How to make **Yes/No decisions** using `Noul`
* How to classify inputs using `Choice`
* How to assign structured levels using `Score`
* How to ask multiple questions in one Jev call
* How to build reusable Jev functions
* How to connect Jev outputs with Python business logic
* How to build real-world workflows around Jev
* How Jev can work alongside LLMs
* How Jev can act as a decision layer in an agentic system
* Why structured decision-making is useful in production AI systems

---

# 📚 Notebook Series

## 1️⃣ Customer Support Ticket Classifier

**Notebook:** `01_jev_customer_support.ipynb`

We start with the basics by building a customer-support ticket classifier.

Given a customer message, Jev determines things such as:

```text
Is the issue urgent?
        ↓
Which department should handle it?
        ↓
How frustrated is the customer?
```

### You will learn:

* `Noul`
* `Choice`
* `Score`
* Multiple questions in one call
* Reusable classification functions
* Basic routing logic

---

## 2️⃣ Sales Lead Qualification & Routing

**Notebook:** `02_jev_sales_lead_qualification.ipynb`

Next, we move to a sales use case.

Given an incoming lead, Jev helps determine:

```text
Lead
 ↓
Is the lead qualified?
 ↓
What type of customer?
 ↓
How strong is the buying intent?
 ↓
Where should the lead be routed?
```

### You will learn:

* Using Jev for qualification
* Combining multiple decision types
* Building priority logic
* Connecting Jev with business rules
* Turning structured AI output into a workflow

---

## 3️⃣ Contract & Document Risk Triage

**Notebook:** `03_jev_contract_risk_triage.ipynb`

Now we move from customer/sales data to documents.

We use Jev to analyze contract clauses and determine:

```text
Contract Clause
      ↓
Does it need review?
      ↓
What type of clause?
      ↓
What is the review priority?
      ↓
Does it contain a deadline?
      ↓
Human Review Queue
```

### You will learn:

* Applying Jev to document intelligence
* Clause classification
* Risk/review prioritization
* Human-in-the-loop workflows
* Separating AI decisions from application logic
* Using Jev + LLM together

> ⚠️ This notebook demonstrates document triage only. It is not intended to provide legal advice or replace legal professionals.

---

## 4️⃣ Jev + LLM Agent Harness

**Coming next 🚧**

The final notebook will combine Jev with an LLM/agent workflow.

The goal is to understand how Jev can act as a **decision layer around an LLM agent**.

For example:

```text
                 User Request
                      ↓
                   LLM Agent
                      ↓
                    Jev
                      ↓
          ┌───────────┼───────────┐
          ↓           ↓           ↓
       Use Tool    Ask User    Answer
          ↓
      Tool Result
          ↓
       LLM Agent
```

We will explore how structured decisions can be used for:

* Tool selection
* Routing
* Guardrails
* Agent control
* Model selection
* Workflow decisions

---

# 🧩 Jev Building Blocks

Throughout the notebooks, we mainly work with three primitives:

| Primitive | Purpose                | Example               |
| --------- | ---------------------- | --------------------- |
| `Noul`    | Yes/No decision        | "Is this urgent?"     |
| `Choice`  | Select a category      | "Which department?"   |
| `Score`   | Ordered classification | "Low / Medium / High" |

These simple building blocks can be combined to create more useful AI workflows.

---

# 🏗️ Overall Architecture

The main pattern we explore throughout this repository is:

```text
              Unstructured Input
                      ↓
                     Jev
                      ↓
             Structured Signals
                      ↓
              Python / Application
                      ↓
                  Workflow
                      ↓
            Human / System Action
```

Jev does not need to control the entire application.

Instead, it can provide **reliable structured signals** that the rest of the application can use.

---

# ⚙️ Setup

Install the required package:

```bash
pip install -U langchain-typesafe
```

You will also need a **TypeSafe API key**.

In the notebooks, the key is loaded using:

```python
import os
from getpass import getpass

if not os.getenv("TYPESAFE_API_KEY"):
    os.environ["TYPESAFE_API_KEY"] = getpass(
        "Enter your TypeSafe API key: "
    )
```

Then initialize the classifier:

```python
from langchain_typesafe import TypeSafeClassifier

classifier = TypeSafeClassifier()
```

---

# 👨‍💻 Who Is This Repository For?

This repository is useful for people who are learning:

* Generative AI
* LLM applications
* Agentic AI
* LangChain
* Structured AI workflows
* AI/ML engineering
* Python-based AI applications

You don't need advanced AI knowledge to follow the notebooks.

The examples are intentionally designed to be **practical and easy to understand**.

---

# 🛣️ Learning Path

If you are new to Jev, follow the notebooks in this order:

```text
Notebook 1
Customer Support
      ↓
Learn Jev Fundamentals
      ↓
Notebook 2
Sales Lead Qualification
      ↓
Apply Jev to Business Workflows
      ↓
Notebook 3
Contract Document Triage
      ↓
Apply Jev to Documents + Human Review
      ↓
Notebook 4
Jev + LLM Agent Harness
      ↓
Build More Advanced AI Workflows
```

---

# 💡 The Main Idea

The biggest lesson from this repository is not just how to call Jev.

It is understanding **where structured decision-making fits inside an AI application**.

Instead of:

```text
User Input → LLM → Everything
```

we can design systems like:

```text
User Input
    ↓
LLM / Extraction
    ↓
Jev
    ↓
Structured Decision
    ↓
Business Logic
    ↓
Action
```

This separation can make AI applications easier to understand, test, and control.

---

## ⭐ If You Find This Useful

If these notebooks help you understand Jev or structured AI workflows, feel free to:

* ⭐ Star the repository
* Fork it
* Experiment with the notebooks
* Create your own use cases
* Share improvements or ideas

The goal of this repository is simple:

> **Learn by building, experiment with real-world use cases, and understand how structured AI decisions can be used in practical applications.**
