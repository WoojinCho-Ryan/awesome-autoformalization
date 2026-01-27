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
The paper introduces Herald, a large-scale dataset that aligns the vast mathematical knowledge of Mathlib4 with natural language using a Dual Augmentation Strategy, significantly improving the performance of LLMs in autoformalization.

## 2. ❓ Problem Definition
While mathematical reasoning using LLMs has advanced, there is a severe scarcity of high-quality parallel datasets pairing natural language mathematical proofs with machine-verifiable Lean 4 code. This shortage limits the ability of models to learn the translation from informal math to formal language, necessitating a robust pipeline to construct high-quality training data.

## 3. 💡 Key Methodology
- **Herald Dataset Construction:** The authors propose a framework to translate and annotate the entire Mathlib4 library (Lean 4's official math library) into natural language.
- **Dual Augmentation Strategy:** To ensure data quality and diversity, two strategies were combined:
  - **Tactic-based Augmentation:** Generating natural language explanations based on each step (tactic) of the proof.
  - **Informal-based Augmentation:** Converting mathematical statements into natural, textbook-style sentences.
- **Lean-jixia System:** Utilizing their custom-developed Lean 4 analyzer, Lean-jixia, they extracted precise hierarchical structures and contextual information from the code to enhance data alignment.

## 4. 📊 Key Results
- **SOTA on miniF2F:** he model trained on the Herald dataset (Herald Translator) achieved an accuracy of 93.2% (Pass@128) on the miniF2F-test set for statement formalization, significantly outperforming existing SOTA models like InternLM2-Math-Plus-7B (74.0%) and TheoremLlama (50.1%).
- **Complex Math Capability:** On a constructed Graduate-level textbook dataset, the model achieved an accuracy of 22.5%, showing superior performance compared to existing models (7.5%).
- **Real-world Application:** The model successfully formalized template sections of the Stacks Project, a real-world advanced mathematics project, demonstrating the feasibility of autoformalizing complex modern mathematical literature.

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

