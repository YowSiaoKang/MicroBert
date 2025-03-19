# MicroBert: Tokenization Techniques for Optimizing Large Language Models across Tasks
[Project Report](Team%2014_Project%20Report_ML%20for%20NLP.pdf)

## Overview

This project investigates the impact of different tokenization techniques on a scaled-down BERT model—named **MicroBERT**—across three key NLP tasks: text generation, question answering, and named entity recognition (NER). We compare three popular tokenization methods: **Unigram**, **Byte-Pair Encoding (BPE)**, and **WordPiece**. Our study demonstrates that while BPE delivers a balanced performance for text generation and question answering, Unigram shows superior results for NER.

## Motivation

Tokenization is a fundamental yet often underestimated step in natural language processing (NLP). The way text is segmented into tokens can significantly affect a model's ability to learn and perform on downstream tasks. This project aims to bridge the gap in guidance regarding the selection of tokenization techniques—especially for small-scale models—and provide empirical evidence to support best practices in NLP preprocessing.

## Objectives

- **Compare Tokenization Methods:** Evaluate Unigram, BPE, and WordPiece tokenizers to understand their strengths and weaknesses.
- **Task Performance Analysis:** Assess how each tokenizer influences the performance of MicroBERT on:
  - **Text Generation:** Measured using perplexity.
  - **Question Answering:** Evaluated with Exact Match (EM) and F1-Score.
  - **Named Entity Recognition (NER):** Assessed via Precision, Recall, and F1-Score.

## Methodology

1. **Dataset Collection:**
   - **Base Dataset:** A combination of BookCorpus and Wikipedia text.
   - **Task-Specific Datasets:**
     - *Text Generation:* WritingPrompts dataset.
     - *Question Answering:* SQuAD (Stanford Question Answering Dataset).
     - *Named Entity Recognition:* CoNLL-2003 dataset.

2. **Training the Tokenizers and Model:**
   - Three tokenizers (Unigram, BPE, and WordPiece) are trained on the same base dataset.
   - The MicroBERT model is a lightweight variant of BERT with 2 transformer layers, 128 hidden dimensions, and 4 attention heads, ensuring efficient training under limited computational resources.

3. **Fine-Tuning:**
   - Each variant of MicroBERT (paired with a different tokenizer) is fine-tuned on the respective task-specific datasets.

4. **Evaluation:**
   - **Text Generation:** Performance is evaluated via perplexity. (BPE achieved the lowest perplexity.)
   - **Question Answering:** Assessed using Exact Match and F1-Score.
   - **Named Entity Recognition (NER):** Evaluated using Precision, Recall, and F1-Score.

## Results

- **Text Generation:**  
  The BPE tokenizer produced the best perplexity score (2.24), indicating superior text generation quality compared to Unigram and WordPiece.
![image](https://github.com/user-attachments/assets/e8fe7b9e-2549-4c84-ba22-d9e621a2989e)

- **Question Answering:**  
  BPE slightly outperformed Unigram in both Exact Match and F1-Score, while WordPiece struggled to produce meaningful results.
![image](https://github.com/user-attachments/assets/7a00254b-03ba-4d66-9429-b0385c31ed6f)

- **Named Entity Recognition (NER):**  
  The Unigram tokenizer achieved the highest scores in precision, recall, and F1—likely due to its probabilistic segmentation approach that better captures entity boundaries.
![image](https://github.com/user-attachments/assets/47f2ea27-8575-43b4-a3f1-1d412fc62b52)

These findings underscore that the optimal tokenization method can vary depending on the specific NLP task.

## Conclusion and Future Work

This project highlights the importance of selecting a tokenization strategy that aligns with specific NLP tasks. The experiments indicate that:

- **BPE** is highly effective for text generation and question answering.
- **Unigram** excels in named entity recognition.

Future work could involve scaling these experiments to larger models and incorporating additional tokenization strategies to further enhance performance across diverse and more complex NLP tasks.

## References

- Toward a Theory of Tokenization in LLMs
- Effects of Tokenization on Transformers for Biological Sequences
- Impact of Tokenization on Language Models: An Analysis for Turkish
- An Information Extraction Study: Take in Mind the Tokenization!
- What Makes for Good Tokenizers in Vision Transformers
- How BPE Affects Memorization in Transformers
- LICHEE
- Efficient Domain Adaptation via Adaptive Tokenization
- Flexibly Scaling Contexts Through Extensible Tokenization

## Authors

- Jonas Endriss
- Mohammad Zain Farooq Gill
- Yow Siao Kang
- Orgil Dorj

