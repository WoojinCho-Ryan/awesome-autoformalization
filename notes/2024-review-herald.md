# 📝 [Herald: A Natural Language Annotated Lean 4 Dataset] Review

> **Paper**: [[Link](https://arxiv.org/abs/2410.10878)]
> 
> **Author**: Guoxiong Gao, Yutong Wang, Jiedong Jiang, Qi Gao, Zihan Qin, Tianyi Xu, Bin Dong
> 
> **Tags**: #Lean_4 #Autoformalization #LLM #Dataset #RAG
>
> **Reviewer**: Woojin Cho (WoojinCho-Ryan)
> 
> **Status**: ✅ Read 

## 1. ⚡ One-Line Summary
The paper introduces MiniF2F, a unified benchmark consisting of 488 Olympiad-level mathematics problems formalized in multiple systems (such as Lean and Metamath) to evaluate and advance neural theorem proving models.
![Number of statements and their provenance in miniF2F](./images/MiniF2F_1.png)

## 2. ❓ Problem Definition
Existing benchmarks for automated theorem proving are often polarized—either too simple (synthetic data) or too difficult (research-level undergraduate math)—and lack comparability across different formal systems. The authors aim to bridge this gap by creating a shared benchmark of high-school competition-level problems to better measure progress in deep learning for theorem proving.

## 3. 💡 Key Methodology
- **Dataset Construction:** The authors collected 488 problems from mathematics competitions (AIME, AMC, IMO) and high school/undergraduate curricula, splitting them into a validation set (244 problems) and a test set (244 problems).
- **Cross-System Support:** To facilitate comparison, the collected problems were formalized in multiple major formal systems: Lean, Metamath, Isabelle, and HOL Light.
- **Baseline Evaluation:** They established baselines using GPT-f (a Transformer-based automated prover) to benchmark performance in Lean and Metamath, analyzing the effectiveness of neural search strategies and language models in different formal environments. 

## 4. 📊 Key Results
- **Superior Performance in Lean:** On the test set (Pass@8), the GPT-f model achieved a 29.2% success rate in Lean, whereas it only achieved 1.6% in Metamath.
- **Importance of High-Level Tactics:** The analysis revealed that this performance gap is largely due to Lean's access to high-level tactics (e.g., linarith, ring), which significantly compress the proof length (average 2.5 steps in Lean vs. 20.3 steps in Metamath), making the search space much more manageable for the neural network.
- **Benefits of Formalization:** The study demonstrated that formal systems effectively serve as objective verifiers, enabling neural networks to leverage search strategies (like best-first search) more effectively compared to informal mathematical reasoning.

## 5. 🧠 Critical Analysis & Insights

### 🌟 Significance (Contribution)
*Why does this paper matter?*
(WORKING IN PROCESS)

### 🚧 Current Limitations
*What are the bottlenecks?*
(WORKING IN PROCESS)

### 🚀 Research Implications
*How can the community use this?*
(WORKING IN PROCESS)

