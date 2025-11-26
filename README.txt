# 🧠 Neuro-Symbolic Supply Chain Twin

**A hybrid AI system bridging the gap between Probabilistic Deep Learning and Deterministic Business Logic.**

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Architecture](https://img.shields.io/badge/Architecture-Neuro--Symbolic-purple)
![AI](https://img.shields.io/badge/AI-SentenceTransformers-green)
![Status](https://img.shields.io/badge/Status-Prototype-orange)

---

## 📖 The Concept

In enterprise inventory management, two competing paradigms usually exist:
1.  **Traditional Systems:** Rigid, rule-based, and fail to understand natural human intent (e.g., keyword search fails on synonyms).
2.  **Pure Generative AI:** Flexible and capable of understanding context, but prone to "hallucinations" (e.g., inventing discounts or stock that doesn't exist).

This project implements a **Neuro-Symbolic Architecture** that combines the best of both worlds. It uses **Vector Embeddings** for semantic understanding (The "Neuro" Brain) and a **Logic Engine** for safety and compliance (The "Symbolic" Guardrails).

---

## 🏗️ System Architecture

The system operates in a decoupled, layered pipeline:

### 1. The Neuro Layer (Perception & Retrieval)
* **Technology:** `sentence-transformers` (Hugging Face `all-MiniLM-L6-v2`).
* **Function:** Converts user queries (natural language) and product descriptions into high-dimensional vectors.
* **Process:** Uses **Cosine Similarity** to retrieve products based on *meaning* rather than exact keyword matching.
    * *Example:* User searches *"Device for heavy coding"* $\rightarrow$ System retrieves *"WorkMate Pro Laptop"* (even if the word 'coding' isn't in the text).

### 2. The Symbolic Layer (Reasoning & Control)
* **Technology:** Custom Python-based Inference Engine.
* **Function:** Applies strict business rules defined in external JSON configurations.
* **Process:** Evaluates retrieved items against hard constraints:
    * *Stock Availability*
    * *Budget Caps*
    * *Expiry Risk*
    * *Discount Thresholds*

### 3. The Application Layer (Interaction)
* **Technology:** Streamlit & SQLite.
* **Function:** Provides a real-time interface for users to interact with the inventory, view AI confidence scores, and see the "Why" behind every recommendation.

---

## 🚀 Key Capabilities

### 🧠 Semantic Search (Beyond Keywords)
Unlike standard SQL queries (`WHERE name LIKE '%query%'`), this system understands context. It handles typos, synonyms, and intent, solving the "Zero Results" problem common in e-commerce.

### 🛡️ Explainable AI (XAI)
The system provides total transparency. Every recommendation includes a dynamic explanation:
* **AI Reason:** "Matched 85% with your search intent."
* **Logic Reason:** "Selected because Discount > 20% and Stock is Low."
This builds trust—users know exactly why an item was suggested.

### ⚡ Dynamic Rule Injection
Business policies are decoupled from the code. A non-technical manager can update `rules.json` (e.g., change the "High Discount" threshold from 20% to 30%) and the agent adapts instantly without recompiling.

---

## 🛠️ Technology Stack

| Domain | Tools Used |
| :--- | :--- |
| **Language** | Python 3.x |
| **AI / NLP** | SentenceTransformers, Scikit-Learn, NumPy |
| **Data Layer** | SQLite3 (Relational), Vector Embeddings (In-memory) |
| **Frontend** | Streamlit |
| **Architecture** | Modular (Separation of Concerns) |

---

## 🔮 Future Enhancements

* **RAG Integration:** Connecting the inventory DB to an LLM (Llama 3) for conversational analytics.
* **Predictive Analytics:** Using LSTM networks to forecast stock depletion rates based on the "Demand" attribute.
* **Vector Database:** Migrating from in-memory arrays to Pinecone/ChromaDB for million-scale item retrieval.

---

Dharani Krishna