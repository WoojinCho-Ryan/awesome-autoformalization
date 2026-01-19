# Awesome Autoformalization

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

A curated list of papers, datasets, and resources dedicated to **Autoformalization** and **Neural Theorem Proving**.

> **Scope:** This repository strictly focuses on translating natural language mathematics into formal logic (e.g., Lean, Isabelle) and solving math problems using formal verification. General LLM reasoning is out of scope.

---

## 🔥 Must-Read & Landmarks
*If you are new to this field, start here. These are the most influential works.*

- **[2025][Autoformalization in the Era of Large Language Models: A Survey]** [[Paper](https://arxiv.org/abs/2505.23486)]
  - *A comprehensive survey of autoformalization with LLMs, covering data, models, evaluation, and the role of formal verification for LLM outputs.*
- **[2025][Kimina-Prover Preview: Towards Large Formal Reasoning Models with Reinforcement Learning]** [[Paper](https://arxiv.org/abs/2504.11354)]
  - *Introduces the “formal reasoning pattern” and a large RL-trained Lean 4 prover that achieves strong MiniF2F performance with high sample efficiency and clear scaling with model size.*
- **[2021][MiniF2F: a cross-system benchmark for formal Olympiad-level mathematics]** [[Paper](https://arxiv.org/abs/2109.00110)]
  - *Defines the standard Olympiad-level formal math benchmark across Metamath, Lean, Isabelle and HOL Light, with GPT-f baselines and an ICLR 2022 release.*
- **[2024][Herald: A Natural Language Annotated Lean 4 Dataset]** [[Paper](https://arxiv.org/abs/2410.10878)]
  - *Builds a large-scale NL–Lean4 corpus over mathlib4 and demonstrates a high-accuracy Herald translator for NL→formal code on MiniF2F and related benchmarks.*
- **[2025][ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data]** [[Paper](https://arxiv.org/abs/2502.05567)]
  - *Proposes a teacher–student pipeline with Lean feedback to synthesize large NL–FL datasets and trains an ATLAS translator that achieves >90% pass@8 on MiniF2F.*
- **[2024][PutnamBench: Evaluating Neural Theorem-Provers on the Putnam Mathematical Competition]** [[Paper](https://arxiv.org/abs/2407.11214)]
  - *Introduces a Putnam-based formal benchmark and shows that both neural and symbolic provers still struggle on truly hard competition-level problems.*
- **[2022][Draft, Sketch, and Prove: Guiding Formal Theorem Provers with Informal Proofs]** [[Paper](https://arxiv.org/abs/2210.12283)]
  - *Presents the “Draft–Sketch–Prove” pipeline, where LLM-generated informal proofs are turned into formal sketches that significantly boost downstream prover success rates.*

---

## 📖 Table of Contents
- [Survey Papers](#-survey-papers)
- [Datasets & Benchmarks](#-datasets--benchmarks)
  - [Parallel Corpora (NL-FL Pairs)](#parallel-corpora-nl-fl-pairs)
  - [Synthetic Data Generation](#synthetic-data-generation)
- [Models](#-models)
  - [Theorem Provers (Solvers)](#-theorem-provers-solvers)
  - [Autoformalizers (Translators)](#-autoformalizers-translators)
- [Methodologies](#-methodologies)
  - [Retrieval-Augmented Generation (RAG)](#retrieval-augmented-generation-rag)
  - [Iterative Refinement & Feedback](#iterative-refinement--feedback)
  - [Multi-Agent Systems](#multi-agent-systems)
- [Evaluation](#-evaluation)
- [Tools](#-tools)

---

## 🗺️ Survey Papers
*Comprehensive overviews of the field.*

- **[2025][Autoformalization in the Era of Large Language Models: A Survey]** [[Paper](https://arxiv.org/abs/2505.23486)]

---

## 📚 Datasets & Benchmarks

### Parallel Corpora (NL-FL Pairs)
*Aligned pairs of Natural Language (NL) and Formal Logic (FL).*

- **[2024][Herald: A Natural Language Annotated Lean 4 Dataset]** [[Paper](https://arxiv.org/abs/2410.10878)]
- **[2021][MiniF2F: a cross-system benchmark for formal Olympiad-level mathematics]** [[Paper](https://arxiv.org/abs/2109.00110)]

### Synthetic Data Generation
*Datasets created or augmented by LLMs.*

- **[2025][ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data]** [[Paper](https://arxiv.org/abs/2502.05567)]

---

## 🚀 Models

### 🤖 Theorem Provers (Solvers)
*End-to-end systems that aim to generate complete proofs and verify them.*

- **[2025][Kimina-Prover Preview: Towards Large Formal Reasoning Models with Reinforcement Learning]** [[Paper](https://arxiv.org/abs/2504.11354)]
- **[2024][PutnamBench: Evaluating Neural Theorem-Provers on the Putnam Mathematical Competition]** [[Paper](https://arxiv.org/abs/2407.11214)]

### 📝 Autoformalizers (Translators)
*Models specialized in translating Natural Language (NL) to Formal Logic (FL).*

- **[2025][ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data]** [[Paper](https://arxiv.org/abs/2502.05567)]
- **[2024][Herald: A Natural Language Annotated Lean 4 Dataset]** [[Paper](https://arxiv.org/abs/2410.10878)]

---

## ⚙️ Methodologies

### Retrieval-Augmented Generation (RAG)
*Methods that retrieve relevant theorems or premises from libraries (e.g., Mathlib).*

- *(Work In Progress)*

### Iterative Refinement & Feedback
*Systems that improve solutions through compiler feedback (Lean/Coq).*

- **[2022][Draft, Sketch, and Prove: Guiding Formal Theorem Provers with Informal Proofs]** [[Paper](https://arxiv.org/abs/2210.12283)]

### Multi-Agent Systems
*Collaborative agents specifically for theorem proving.*

- *(Work In Progress)*

---

## ⚖️ Evaluation
*Metrics and methodologies to assess the quality of autoformalization and proving.*

### 1. Functional Correctness (Does it work?)
- **Pass@k**
  - *The standard metric: probability that at least one of `k` generated samples solves the problem (verified by the proof assistant).*
- **Compilation Rate**
  - *The percentage of generated formal code that successfully compiles without syntax or type errors. A crucial baseline metric for autoformalizers.*

### 2. Semantic Consistency (Is it the right translation?)
- **Automated Equivalence Checking**
  - *Using automated provers to verify if the generated formal statement ($F$) is logically equivalent to the ground truth ($F_{gt}$), i.e., proving $F \leftrightarrow F_{gt}$.*
- **Back-Translation Quality** (NL $\to$ FL $\to$ NL)
  - *Translating the generated formal code back into natural language and comparing it with the original text using NLP metrics (BLEU, ROUGE, BERTScore).*

### 3. Alignment & Reasoning
- **Informal-to-Formal Alignment**
  - *Measuring how well the steps in an informal proof map to the tactics in a formal proof.*
- **Premise Selection Accuracy**
  - *Evaluating if the model retrieves the correct axioms and theorems (from libraries like Mathlib) required for the proof.*

---

## 🛠️ Tools
*Proof Assistants and Environments.*

- **Lean 4**
  - *The most popular tool for modern autoformalization research.*
- **Isabelle**
- **Coq**

---

## 🤝 Contribution
Contributions are welcome! Please create a pull request.

**Maintainer**: [Woojin Cho](https://github.com/WoojinCho-Ryan)
