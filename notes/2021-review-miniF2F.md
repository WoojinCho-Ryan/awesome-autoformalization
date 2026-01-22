# 📝 [MiniF2F: a cross-system benchmark for formal Olympiad-level mathematics] Review

> **Paper**: [[Link](https://arxiv.org/abs/2109.00110)]
> 
> **Author**: Kunhao Zheng, Jesse Michael Han, Stanislas Polu
> 
> **Tags**: #miniF2F #Lean #Formal_Mathematics #Neural_Theorem_Proving #Cross-system_Mathematics
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
- **Pioneering Unified Benchmark:** It establishes a high-quality, standardized testbed for multiple formal systems (Lean, Isabelle, HOL Light, Metamath), enabling direct comparison beyond system-specific evaluations.
- **Granular Difficulty Stratification:** By categorizing problems from high-school curricula to IMO level, it allows for a systematic diagnosis of a model's reasoning bottlenecks (e.g., simple arithmetic vs. creative insight).
- **Facilitating Cross-System Evaluation:** The multi-lingual nature of the dataset opens the door for comparing neuro-symbolic approaches across different logical foundations.

### 🚧 Current Limitations
*What are the bottlenecks?*
- **Data Scarcity & Overfitting Risk:** With only 488 examples in the test set, the dataset is relatively small for data-hungry Transformer models, raising concerns about high evaluation variance and potential overfitting.
- **Subjectivity & Variance in Difficulty:** The difficulty labels are based on human curricula. Not only can this diverge from computational hardness, but there may also be significant perceived complexity variance even within the same difficulty level.
- **Validity of Domain Distribution:** The dataset segments math into Algebra, Number Theory, etc., but it remains questionable whether the current ratio of these domains effectively represents general mathematical reasoning capabilities. Further validation on domain balance is needed.
- **Performance Disparity:** The drastic performance gap between Lean (high) and Metamath (low) implies that current benchmarks may heavily favor systems equipped with high-level tactic libraries rather than measuring pure reasoning ability.

### 🚀 Research Implications
*How can the community use this?*
- **Ground Truth for Autoformalization:** This benchmark serves as an objective metric for Informal-to-Formal translation tasks, verifying not just syntactic correctness but also semantic validity.
- **Standard for Generalization:** It highlights the necessity of developing system-agnostic models that can reason effectively regardless of the underlying formal language or library dependencies.

