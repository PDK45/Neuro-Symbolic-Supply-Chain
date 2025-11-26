# 🧠 Neuro-Symbolic Supply Chain Twin

**A hybrid AI system bridging the gap between Classical NLP, Probabilistic Deep Learning, and Deterministic Business Logic.**

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Architecture](https://img.shields.io/badge/Architecture-Neuro--Symbolic-purple)
![AI](https://img.shields.io/badge/AI-SentenceTransformers-green)
![NLP](https://img.shields.io/badge/NLP-NLTK-yellow)

---

## 📖 The Concept

In enterprise inventory management, two competing paradigms usually exist:
1.  **Traditional Systems:** Rigid, rule-based, and fail to understand natural human intent (e.g., keyword search fails on synonyms).
2.  **Pure Generative AI:** Flexible and capable of understanding context, but prone to "hallucinations" (e.g., inventing discounts or stock that doesn't exist).

This project implements a **Neuro-Symbolic Architecture** that combines the best of both worlds. It uses a **Multi-Stage NLP Pipeline** for intent understanding (The "Neuro" Brain) and a **Logic Engine** for safety and compliance (The "Symbolic" Guardrails).

---

## 🏗️ System Architecture

The system operates in a decoupled, layered pipeline:

### 1. The Neuro Layer (NLP & Perception)
This layer transforms raw text into machine-understandable signals using a hybrid approach:
* **Stage A: Text Preprocessing (NLTK):**
    * Utilizes **Natural Language Toolkit (NLTK)** for noise reduction.
    * Performs tokenization and stop-word removal to filter out irrelevant signals (e.g., "I", "want", "a") before embedding.
* **Stage B: Semantic Embedding (Transformers):**
    * Uses **HuggingFace SentenceTransformers** (`all-MiniLM-L6-v2`) to convert the cleaned text into high-dimensional vectors.
    * Retrieves products based on *meaning* (Cosine Similarity) rather than exact keyword matching.

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
Unlike standard SQL queries (`WHERE name LIKE '%query%'`), this system understands context. By preprocessing with **NLTK** and vectorizing with **Transformers**, it solves the "Zero Results" problem common in e-commerce.

### 🛡️ Explainable AI (XAI)
The system provides total transparency. Every recommendation includes a dynamic explanation:
* **AI Reason:** "Matched 85% with your search intent."
* **Logic Reason:** "Selected because Discount > 20% and Stock is Low."
This builds trust—users know exactly why an item was suggested.

### ⚡ Dynamic Rule Injection
Business policies are decoupled from the code. A non-technical manager can update `rules.json` (e.g., change the "High Discount" threshold from 20% to 30%) and the agent adapts instantly without recompiling.

---
Dharani Krishna
