
# On the Eligibility of LLMs for Counterfactual Reasoning: A Decompositional Study

## ⚠️ IMPORTANT
This repository is anonymous and is solely intended for review purposes. 

## 💡 Introduction
This repository contains the code and resources for our research on counterfactual reasoning in Large Language Models (LLMs). We introduce a systematic framework that includes standardized processes for counterfactual generation, evaluation, and interpretation across multiple domains.

## 📊 Datasets & Models
**Datasets (5 task categories)**:

- Question Answering: CRASS, CVQA-Bool, MalAlgoQA
- Text Parsing: CLOMO, RNN-Typology
- Reasoning: CVQA-count, Arithmetic
- Multimodal: COCO
- Code: HumanEval-Exe, Open-Critic, Code-Preference

**Models**:

- GPT-4o, Qwen-VL, LLaMA-3.2-11B, Gemini-Pro, DeepSeek-VL

**Modalities**: 
- Text, Images, Math symbols, Code

## 📄Decomposing Counterfactual Reasoning
To adapt these datasets for counterfactual reasoning evaluation, we conduct a careful manual curation process to augment each instance with three additional aspects of information. Specifically, we begin by identifying and annotating the **causal variables** ($X$, $Z$, $M$, $Y$) from the original data, questions, or descriptions. Using these annotations, we construct a DAG to represent the underlying causal structure of each data instance.

**causal variables**
- Exposure(or intervention, denoted $X$) refers to the action or condition imposed on a system;
- Outcome ($Y$) denotes the resulting response or effect influenced by the exposure;
- Covariates ($Z$) are pre-treatment variables that may influence both $X$ and $Y$;
- Mediator ($M$) lies on the causal pathway from $X$ to $Y$, representing intermediate mechanisms through which the exposure exerts its influence.