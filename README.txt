# 📦 **Inventory Knowledge‑Based Agent (KBA)**

A highly modular, intelligent, and rule‑driven **Knowledge‑Based Agent** designed to automate inventory decision‑making, optimize stock operations, and provide real‑time insights through a modern Streamlit front‑end.

This system combines:

* A **declarative rule engine**,
* A **structured knowledge base**,
* A **forward‑chaining inference agent**, and
* An **interactive Streamlit UI**,

to create an enterprise‑grade inventory automation solution.

---

## 🚀 **Project Overview**

This project demonstrates how classical AI methodologies—specifically **Knowledge‑Based Systems**—can be applied to solve practical business problems such as inventory management.

Your agent:

* Reads structured inventory facts (JSON)
* Evaluates them against well‑defined domain rules
* Fires intelligent, explainable actions
* Provides insights through an intuitive UI
* Allows live editing of inventory data
* Re-applies rule reasoning instantly

The system functions like a production‑ready backend used by inventory teams, warehouses, and retail systems.

---

## 🧠 **Knowledge‑Based Agent (Core AI Brain)**

The agent is implemented in `agent.py` and follows the classic architecture:

### **Knowledge = Facts**

Stored in `inventory.json`, including:

* Quantity
* Reorder level
* Overstock threshold
* Expiry date
* Demand
* Metadata

### **Inference = Rule Engine**

Stored in `rules.json`, including rules like:

* Low stock → Reorder
* Overstock → Mark for sale
* High demand → Priority restock
* Near expiry → Investigate

### **Control = Agent Logic**

The agent:

1. Loads all facts from the Knowledge Base
2. Loads all rules from the Rule Base
3. Matches facts to rule conditions
4. Fires actions when conditions are satisfied
5. Returns structured outputs back to the UI or CLI

This creates a fully autonomous decision‑making engine.

---

## 🔧 **Rule Engine (Declarative, Explainable, Extensible)**

The rule engine in `rules_engine.py` is designed for:

* Safe and controlled evaluation
* Priority‑based rule conflict resolution
* Human‑readable rule expressions
* Multi‑condition AND logic
* Multiple action triggers per rule

Example rule:

```
IF quantity <= reorder_level
THEN REORDER item
```

Rules are fully **decoupled** from the code, enabling business teams to update policy without restarting the system.

---

## 🧩 **Knowledge Base (Fact Management)**

Implemented in `knowledge_base.py`, it:

* Loads/saves inventory facts
* Computes derived attributes (days until expiry, demand pressure, stock risk)
* Provides a clean dictionary of facts for rule matching
* Ensures data consistency

This forms the "world state" for the agent.

---

## 🌐 **Streamlit Front‑End Dashboard (User Interaction Layer)**

The UI (`app.py`) provides:

### ✔ Real‑time item insights

### ✔ Editable inventory values (quantity / reorder level / expiry / etc.)

### ✔ One‑click triggering of agent‑recommended actions

### ✔ Full visualization of rule‑based reasoning

### ✔ Automatic syncing with JSON data

This turns the system from a backend algorithm into a **full operational tool**.

---

```
               ┌─────────────────────────┐
               │       Streamlit UI      │
               │    (Interaction Layer)  │
               └─────────────┬───────────┘
                             │
                             ▼
               ┌─────────────────────────┐
               │     Inventory Agent     │
               │        (agent.py)       │
               └─────────────┬───────────┘
                             │
  ┌──────────────────────────┼───────────────────────────┐
  ▼                          ▼                           ▼
```

┌──────────────┐       ┌───────────────────┐        ┌──────────────────┐
│ Knowledge    │       │   Rule Engine     │        │ Utility Module   │
│ Base (facts) │       │  (rules_engine)   │        │  (expiry, dates) │
└──────────────┘       └───────────────────┘        └──────────────────┘
│
▼
┌──────────────────┐
│   Actions Fired   │
└──────────────────┘

```
Dharani Krishna



