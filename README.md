# Awesome Autoformalization

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Status](https://img.shields.io/badge/Status-Work%20in%20Progress-orange)](https://github.com/WoojinCho-Ryan/awesome-autoformalization)

A curated list of papers, datasets, and resources dedicated to **Autoformalization** and **Neural Theorem Proving**.

> **Scope:** This repository strictly focuses on translating natural language mathematics into formal logic (e.g., Lean, Isabelle) and solving math problems using formal verification. General LLM reasoning is out of scope.
>
> <img width="668" height="466" alt="image" src="https://github.com/user-attachments/assets/823a7d16-2b9e-4505-b2de-ac1e8cc9f6d2" />
> 
> Figure by paper 'Autoformalization in the Era of Large Language Models: A Survey'

---

## 🔥 Must-Read & Landmarks
*If you are new to this field, start here. These are the most influential works.*

- [2025] **Autoformalization in the Era of Large Language Models: A Survey** [[Paper](https://arxiv.org/abs/2505.23486)]
  - *A comprehensive survey of autoformalization with LLMs, covering data, models, evaluation, and the role of formal verification for LLM outputs.*
- [2025] **Kimina-Prover Preview: Towards Large Formal Reasoning Models with Reinforcement Learning** [[Paper](https://arxiv.org/abs/2504.11354)]
  - *Introduces the “formal reasoning pattern” and a large RL-trained Lean 4 prover that achieves strong MiniF2F performance with high sample efficiency and clear scaling with model size.*
- [2021] **MiniF2F: a cross-system benchmark for formal Olympiad-level mathematics** [[Paper](https://arxiv.org/abs/2109.00110)] **[[📝Deep Dive](./notes/2021-review-miniF2F.md)]**
  - *Establishes a unified, cross-system benchmark for formal Olympiad-level mathematics, serving as the primary testbed for evaluating autoformalization models.*
- [2024] **Herald: A Natural Language Annotated Lean 4 Dataset** [[Paper](https://arxiv.org/abs/2410.10878)] **[[📝Deep Dive](./notes/2024-review-herald.md)]**
  - *Builds a large-scale NL–Lean4 corpus over mathlib4 and demonstrates a high-accuracy Herald translator for NL→formal code on MiniF2F and related benchmarks.*
- [2025] **ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data** [[Paper](https://arxiv.org/abs/2502.05567)] **[[📝Deep Dive](./notes/2025-review-atlas.md)]**
  - *Proposes a teacher–student pipeline with Lean feedback to synthesize large NL–FL datasets and trains an ATLAS translator that achieves >90% pass@8 on MiniF2F.*
- [2024] **PutnamBench: Evaluating Neural Theorem-Provers on the Putnam Mathematical Competition** [[Paper](https://arxiv.org/abs/2407.11214)]
  - *Introduces a Putnam-based formal benchmark and shows that both neural and symbolic provers still struggle on truly hard competition-level problems.*
- [2022] **Draft, Sketch, and Prove: Guiding Formal Theorem Provers with Informal Proofs** [[Paper](https://arxiv.org/abs/2210.12283)] **[[📝Deep Dive](./notes/2022-review-dsp.md)]**
  - *Presents the “Draft–Sketch–Prove” pipeline, where LLM-generated informal proofs are turned into formal sketches that significantly boost downstream prover success rates.*

---

## 📖 Table of Contents
- [Survey Papers](#survey-papers)
- [Datasets & Benchmarks](#datasets-benchmarks)
  - [Parallel Corpora (NL-FL Pairs)](#parallel-corpora)
  - [Synthetic Data Generation](#synthetic-data)
  - [Reasoning Benchmarks](#reasoning-benchmarks)
- [Models & Agents](#models-agents)
  - [Theorem Provers (Solvers)](#theorem-provers)
  - [Autoformalizers (Translators)](#autoformalizers)
- [Methodologies](#methodologies)
  - [Search & Planning](#search-planning)
  - [Iterative Refinement & Feedback](#iterative-feedback)
  - [Execution & Verification](#execution-verification)
  - [Retrieval-Augmented Generation (RAG)](#rag)
  - [Multi-Agent Systems](#multi-agent-systems)
- [Evaluation](#evaluation)
  - [Standard Metrics](#standard-metrics)
  - [Evaluation Frameworks](#evaluation-frameworks)
- [Tools](#tools)

---

## 🗺️ Survey Papers <a name="survey-papers"></a>
*Comprehensive overviews of the field.*

- [2026] **AI for Mathematics: Progress, Challenges, and Prospects** [[Paper](https://arxiv.org/abs/2601.13209)]
- [2025] **Autoformalization in the Era of Large Language Models: A Survey** [[Paper](https://arxiv.org/abs/2505.23486)]

---

## 📚 Datasets & Benchmarks <a name="datasets-benchmarks"></a>

### Parallel Corpora (NL-FL Pairs) <a name="parallel-corpora"></a>
*Aligned pairs of Natural Language (NL) and Formal Logic (FL).*

- [2024] **Herald: A Natural Language Annotated Lean 4 Dataset** [[Paper](https://arxiv.org/abs/2410.10878)] **[[📝Deep Dive](./notes/2024-review-herald.md)]**
- [2021] **MiniF2F: a cross-system benchmark for formal Olympiad-level mathematics** [[Paper](https://arxiv.org/abs/2109.00110)] **[[📝Deep Dive](./notes/2021-review-miniF2F.md)]**

### Synthetic Data Generation <a name="synthetic-data"></a>
*Datasets created or augmented by LLMs to overcome data scarcity.*

- [2025] **ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data** [[Paper](https://arxiv.org/abs/2502.05567)] **[[📝Deep Dive](./notes/2025-review-atlas.md)]**

### Reasoning Benchmarks <a name="reasoning-benchmarks"></a>
*Benchmarks designed to evaluate step-by-step logical reasoning and chain-of-thought capabilities.*

- [2023] **The CoT Collection: Improving Zero-shot and Few-shot Learning of Language Models via Chain-of-Thought Fine-Tuning** [[Paper](https://arxiv.org/abs/2305.14045)]

---

## 🚀 Models & Agents <a name="models-agents"></a>

### 🤖 Theorem Provers (Solvers) <a name="theorem-provers"></a>
*End-to-end systems that aim to generate complete proofs and verify them.*

- [2025] **Kimina-Prover Preview: Towards Large Formal Reasoning Models with Reinforcement Learning** [[Paper](https://arxiv.org/abs/2504.11354)]
- [2024] **PutnamBench: Evaluating Neural Theorem-Provers on the Putnam Mathematical Competition** [[Paper](https://arxiv.org/abs/2407.11214)]

### 📝 Autoformalizers (Translators) <a name="autoformalizers"></a>
*Models specialized in translating Natural Language (NL) to Formal Logic (FL).*

- [2025] **ATLAS: Autoformalizing Theorems through Lifting, Augmentation, and Synthesis of Data** [[Paper](https://arxiv.org/abs/2502.05567)]
- [2024] **Herald: A Natural Language Annotated Lean 4 Dataset** [[Paper](https://arxiv.org/abs/2410.10878)] **[[📝Deep Dive](./notes/2024-review-herald.md)]**

---

## ⚙️ Methodologies <a name="methodologies"></a>

### Search & Planning <a name="search-planning"></a>
*Methods that utilize proof planning (sketching) or search algorithms to navigate the solution space.*

- [2024] **Self-Explore to Avoid the Pit: Improving the Reasoning Capabilities of Language Models with Fine-grained Rewards** [[Paper](https://arxiv.org/abs/2404.10346)]
- [2022] **Draft, Sketch, and Prove: Guiding Formal Theorem Provers with Informal Proofs** [[Paper](https://arxiv.org/abs/2210.12283)] **[[📝Deep Dive](./notes/2022-review-dsp.md)]**

### Iterative Refinement & Feedback <a name="iterative-feedback"></a>
*Systems that improve solutions through compiler feedback or error messages.*

- [2025] **KELPS: A Framework for Verified Multi-Language Autoformalization via Semantic-Syntactic Alignment** [[Paper](https://arxiv.org/abs/2507.08665)]
- [2024] **Towards Logically Sound Natural Language Reasoning with Logic-Enhanced Language Model Agents** [[Paper](https://arxiv.org/abs/2408.16081)]

### Execution & Verification <a name="execution-verification"></a>
*Approaches that leverage code execution (simulation) or formal verification to enhance reasoning accuracy.*

- [2025] **FoVer: First-Order Logic Verification for Natural Language Reasoning** [[Paper](https://direct.mit.edu/tacl/article/doi/10.1162/TACL.a.41/133797/FoVer-First-Order-Logic-Verification-for-Natural)]
- [2024] **Language Models as Compilers: Simulating Pseudocode Execution Improves Algorithmic Reasoning in Language Models** [[Paper](https://arxiv.org/abs/2404.02575)]

### Retrieval-Augmented Generation (RAG) <a name="rag"></a>
*Methods that retrieve relevant theorems or premises from libraries (e.g., Mathlib).*

- *(Work In Progress)*

### Multi-Agent Systems <a name="multi-agent-systems"></a>
*Collaborative agents specifically designed for theorem proving tasks.*

- *(Work In Progress)*

---

## ⚖️ Evaluation <a name="evaluation"></a>
*Metrics and methodologies to assess the quality of autoformalization and proving.*

### 📊 Standard Metrics <a name="standard-metrics"></a>

#### 1. Functional Correctness (Does it work?)
- **Pass@k**
  - *The standard metric: probability that at least one of `k` generated samples solves the problem (verified by the proof assistant).*
- **Compilation Rate**
  - *The percentage of generated formal code that successfully compiles without syntax or type errors. A crucial baseline metric for autoformalizers.*

#### 2. Semantic Consistency (Is it the right translation?)
- **Automated Equivalence Checking**
  - *Using automated provers to verify if the generated formal statement ($F$) is logically equivalent to the ground truth ($F_{gt}$), i.e., proving $F \leftrightarrow F_{gt}$.*
- **Back-Translation Quality** (NL $\to$ FL $\to$ NL)
  - *Translating the generated formal code back into natural language and comparing it with the original text using NLP metrics (BLEU, ROUGE, BERTScore).*

#### 3. Alignment & Reasoning
- **Informal-to-Formal Alignment**
  - *Measuring how well the steps in an informal proof map to the tactics in a formal proof.*
- **Premise Selection Accuracy**
  - *Evaluating if the model retrieves the correct axioms and theorems (from libraries like Mathlib) required for the proof.*

---

### 📑 Evaluation Frameworks <a name="evaluation-frameworks"></a>
*Research papers focusing on novel evaluation protocols and alignment checking.*

- [2024] **FormalAlign: Automated Alignment Evaluation for Autoformalization** [[Paper](https://arxiv.org/abs/2410.10135)]

---

## 🛠️ Tools <a name="tools"></a>
*Proof Assistants and Environments.*

- **Lean 4**
  - *The most popular tool for modern autoformalization research.*
- **Isabelle**
- **Coq**

---

## 🤝 Contribution
Contributions are welcome! Please create a pull request.

### Maintainer
- **[Woojin Cho](https://github.com/WoojinCho-Ryan)**: (Undergraduate Researcher @ SNU, Computer Science and Engineering)
  - e-mail: woojincho.cs@gmail.com

## 🗓 Roadmap
### Upcoming Deep Dives
- [ ] Kimina-Prover (2025): Exploration of Reinforcement Learning and scaling laws in Formal Reasoning.
- [ ] PutnamBench (2024): Evaluation of current LLMs on university-level math and the limits of Neural Theorem Provers.
- [ ] KELPS (2025): Deep dive into Iterative Refinement and semantic-syntactic alignment.

### Research & Expansion
- [ ] Literature Review: Identifying latest papers on Agentic Workflows for formal verification.
- [ ] Benchmark Comparison: Comparative analysis of MiniF2F, ProofNet, and PutnamBench.
- [ ] Tooling Updates: Curating resources for Lean 4 environment setup and Mathlib4 integration.
- [ ] Reinforcement Learning: Surveying Reward Model designs specifically tailored for formal logic.
