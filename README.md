# Part-of-Speech Tagging using Hidden Markov Models (HMM)

This project implements a Part-of-Speech (PoS) tagger using Hidden Markov Models (HMMs) from scratch, as part of a coursework assignment. The tagger is evaluated on the Penn Treebank (PTB) dataset using various HMM configurations and evaluated for both fine-grained (36-tag) and coarse-grained (4-tag) tag sets.

## 📌 Objective

To build a PoS tagger using the Viterbi algorithm and different configurations of HMMs without using any external libraries for sequence tagging. The project evaluates the performance of the models on:
- Standard 36-tag set from the Penn Treebank.
- Reduced 4-tag set: N (nouns), V (verbs), A (adjectives/adverbs), and O (others).

## 📁 Dataset

- **Name:** Penn Treebank (PTB) corpus
- **Format:** Sentences with word/POS-tag pairs
- **Split:** 80% Training, 20% Testing

## ⚙️ HMM Configurations Implemented

1. **First-Order HMM**  
   - Assumes: `P(tag_i | tag_{i-1})` and `P(word_i | tag_i)`

2. **Second-Order HMM**  
   - Assumes: `P(tag_i | tag_{i-2}, tag_{i-1})` and `P(word_i | tag_i)`

3. **Word-Dependent Emission HMM**  
   - Assumes: `P(tag_i | tag_{i-1})` and `P(word_i | tag_i, word_{i-1})`

All models use the Viterbi algorithm for decoding the most probable tag sequence.

## 🔄 Tag Set Reduction

The 36 original POS tags are collapsed into 4 coarse-grained categories:

| Tag Category | Mapped POS Tags                             |
|--------------|---------------------------------------------|
| N            | All noun tags (`NN`, `NNS`, `NNP`, etc.)    |
| V            | All verb tags (`VB`, `VBD`, `VBG`, etc.)    |
| A            | All adjectives and adverbs (`JJ`, `RB`, etc.) |
| O            | All other tags (prepositions, determiners, etc.) |

## 🧪 Evaluation Metrics

- **Overall Accuracy:** Percentage of correctly predicted tags
- **Tag-wise Accuracy:** Accuracy per tag/category
- **Comparison:** Between 36-tag and 4-tag models across different configurations

## 🧠 Handling Unknown Words

For unseen words in the test set, the most frequent tag in the training data is used as a default.

## 📊 Sample Results (Hypothetical)

| HMM Configuration       | Tag Set | Overall Accuracy |
|-------------------------|---------|------------------|
| First-Order HMM         | 36-tag  | 91.3%            |
| First-Order HMM         | 4-tag   | 95.6%            |
| Second-Order HMM        | 36-tag  | 92.1%            |
| Word-Dependent HMM      | 36-tag  | 92.8%            |

## 💬 Observations & Analysis

- The 4-tag model consistently outperforms the 36-tag model due to reduced sparsity in transition and emission probabilities.
- With fewer tags, the model generalizes better and is less affected by data imbalance.
- Second-order and word-dependent HMMs show better contextual understanding but require more computation and data.

## 📄 Submission Details

- **Report:** `Roll_no1_Roll_no2_...pdf`
- **Files:** Source code, results, and report submitted individually (not zipped)
- **Platform:** Google Classroom

## 👥 Team Members

- Roll_no1 – Name1  
- Roll_no2 – Name2  
- Roll_no3 – Name3  
- Roll_no4 – Name4

## 🚫 Restrictions

- No use of external PoS tagging libraries or pre-trained models.
- HMMs must be implemented from scratch.

---

