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
- **Paradigm Shift to Data-Centric Autoformalization:** While previous works focused on architectural modifications (e.g., retrieval-augmented generation), HERALD demonstrates that high-fidelity data alignment is the dominant factor. By treating the entire Mathlib4 corpus as a parallel corpus source, it effectively solves the "cold start" problem for Lean 4 autoformalization.
- **Granular Semantic Alignment:** The "Dual Augmentation Strategy" (specifically Tactic-based augmentation) is critical. It bridges the semantic gap between high-level mathematical intent (informal) and low-level proof steps (tactics). This provides the model with a dense supervision signal, allowing it to learn not just what to prove, but how the logic decomposes at the tactic level.
- **Generalization via Synthetic Data:** The paper empirically proves that models trained on synthetic, library-derived data (Mathlib) can generalize effectively to out-of-distribution domains like competition math (miniF2F) and graduate-level textbooks, challenging the assumption that domain-specific human-written data is strictly necessary.

### 🚧 Current Limitations
*What are the bottlenecks?*
- **Reverse-Translation Bias:** The dataset is constructed via "Backward Translation" (Formal Code to Synthetic Natural Language). Consequently, the generated natural language inevitably carries the structural bias of Lean code. There is a risk that the model is learning to "de-compile" formal code rather than truly "formalize" ambiguous, messy, human-written mathematics.
- **Dependence on Existing Formalizations:** The augmentation pipeline relies on correctly compiling Lean code to extract tactic states. This limits the data generation strictly to theorems that already exist and compile in Mathlib. It does not inherently help the model learn to formalize novel definitions or axioms that fall outside the current scope of the library.
- **Inference Inefficiency:** While the accuracy (Pass@128) is impressive, the reliance on generating 128 samples suggests that the model's zero-shot "reasoning" certainty is still volatile. The gap between Pass@1 and Pass@128 indicates that the model is effectively searching a large space rather than proceeding with confident logical deduction.

### 🚀 Research Implications
*How can the community use this?*
- **Bootstrapping Self-Improvement Loops:** HERALD provides the critical mass of data needed to kickstart iterative training loops (like STaR or Expert Iteration). Future work can use HERALD-trained models to autoformalize new data, verify it with Lean, and add it back to the training set, creating a "LELMA-style" virtuous cycle.
- **From Translation to Co-Pilot Agents:** The success of tactic-based annotation suggests that future models shouldn't just be "translators" (Input NL $\to$ Output Code) but interactive "co-pilots" that can explain the state of the proof in natural language to the user, aiding in the debugging of formal proofs.
- **Benchmarking on "Wild" Math:** The community must now move beyond miniF2F. The next frontier is evaluating whether these models can handle the noise and ambiguity of raw arXiv papers or StackExchange discussions, effectively measuring the "Sim-to-Real" transfer capability of the HERALD dataset.
