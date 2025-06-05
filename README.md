# 🧠🗣️ Brain2Text: Decoding Language from fMRI Using Brain Adapters and LLMs (In Progress)

This project replicates and extends the findings of [Ye et al., *Nature*, 2025], which demonstrated that large language models (LLMs) can decode continuous language from non-invasive fMRI recordings. The goal is to build a robust pipeline from brain signals to text using modern transformer-based language models, and to expand upon the original architecture for deeper insights and improved performance.

---

## 🧪 Project Overview

### 🔹 Phase 1: Replication of Ye et al. (2025) with modifications

The first phase of this project replicates the original BrainLLM framework as faithfully as possible.

#### Tasks:
- **Data**:
  - 📌 Primary: [Narratives Dataset](https://openneuro.org/datasets/ds002345)
  - 📌 Secondary (optional): Pereira et al. (2018), Huth et al. (2016)

- **Preprocessing**:
  - Match Ye et al.’s preprocessing pipeline for the fMRI data

- **Modeling**:
  - Implement Ye et al.'s **Brain Adapter → LLaMA 2** architecture
  - Use their hyperparameters, prompt tuning strategies, and optimization procedures
  - Expand into **Brain Adapter → LLaMA 4** architecture

- **Evaluation**:
  - Replicate performance metrics reported in the paper
  - Analyze voxel-wise GLM fits and top-N decoding accuracies

#### 📌 Goal:
Establish a reproducible baseline that faithfully reflects the original paper’s findings using publicly available data and open-source models.

---

### 🔹 Phase 2: Expansion and Innovation

This phase explores architectural and methodological extensions to the baseline model.

#### Tasks:

- **Preprocessing**:
  - Align audio/text stimuli using WhisperX with word-level timestamps

- **Embedding Bridging**:
  - Explore embedding space alignment between BERT-based models and decoder LLMs
  - Investigate best practices for bridging encoder-decoder mismatches

- **Model Variants**:
  - ✅ Model A: `Brain Adapter → BERT/RoBERTa/NeoBERT → LLaMA 4`
  - ✅ Model B: `Brain Adapter → T5 (encoder-decoder)`

- **Model Comparisons**:
  - Evaluate improvements from LLaMA 2 → LLaMA 4
  - Test the value-add of introducing a BERT-style encoder before decoding

#### 🧠 Research Questions:

- **Primary**:
  - Can we model brain-to-text decoding by mimicking the functional separation of human language processing (Wernicke's and Broca's areas) — using encoder models (e.g., BERT) to simulate language comprehension and decoder models (e.g., LLaMA or T5) to simulate language generation - thereby capturing a more neurobiologically grounded pathway from neural activity to natural language?
- **Secondary**:
  - Can more recent models (e.g., LLaMA 4) improve decoding performance?
  - Does the addition of BERT-style embeddings enable better brain-to-text alignment?
  - How do different LLM architectures handle fMRI-induced representations?

---

## 📁 Repository Structure

