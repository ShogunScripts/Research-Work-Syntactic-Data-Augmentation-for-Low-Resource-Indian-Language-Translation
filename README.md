# Title : Data Augmentation for English–Hindi Parallel Corpora using Parse Trees and Large Language Models

## Overview
- This repository documents my ongoing M.Tech research work at NIT Hamirpur, under the guidance of Prof. Arun Kumar Yadav.
- My work focuses on improving Neural Machine Translation (NMT) quality for low-resource Indian languages using a syntactic data augmentation technique that leverages parse trees and Large Language Models (LLMs).
- The goal is to generate high-quality synthetic parallel data by extracting linguistically meaningful phrases and regenerating masked sentences using LLMs—ultimately boosting translation performance for low-resource English–Indian language pairs.


## Research Motivation
Indian languages suffer from a scarcity of parallel corpora.
This limits the performance of transformer-based NMT models.
My research explores:
- How much translation quality improves when we augment training data using syntactically controlled phrase regeneration.
- Whether LLM-based sentence reconstruction can help preserve domain meaning even when most words are masked.
- How parse tree structures can guide the extraction of high-quality phrases for back-translation.


## Methodology Pipeline
### 1️. Input Dataset

- English–Hindi sentence pairs

- Source: Samanantar / WMT datasets

### 2. Masking + LLM Reconstruction

We:

- Mask non-important (non-keywords) words (KeyBERT)

- Retain only key domain-specific tokens

- Regenerate full sentences using LLaMA (Groq Llama-3.3-70B)

Using LLaMA helps create syntactically diverse and semantically consistent variants before parsing.

### 3️. Parse Tree Generation

- Generate parse trees for the LLaMA-regenerated English & Hindi sentences (GPT-OSS-20B (Groq))

- Parsing improved sentences yields cleaner phrase boundaries

### 4. Phrase Extraction (Custom recursive parser)

Two extraction routes:

A. Fixed 7 Phrase Categories

  - NP, VP, PP, ADJP, ADVP, QP, INTJ

B. Dynamic Meaningful Phrases

  - Extract full meaningful subtrees based on constituent structure

### 5. Back-Translation (NLLB-200)

- English phrases → Hindi

- Hindi phrases → English

### 6. Training the NMT Model

- Transformer model

- Subword encoding (BPE / SentencePiece)

### 7. Evaluation

- BLEU, chrF, COMET

- Compare baseline vs. augmented performance

-------

### Pipeline Diagram  
<img src="7 phrase back-generation.svg" alt="Pipeline Diagram" width="800">

--------

### Presentation  
=> [Download PPT Presentation](Research_Presentation__Mrunal.pdf)



## Current Status (Ongoing Work)

I am currently working on:

- Designing and evaluating data augmentation techniques for low-resource Indian languages
- Using parse-tree-guided masking + LLM regeneration
- Improving translation quality by generating synthetic parallel phrases
- Testing augmentation effects on transformer-based NMT models

**Formally:**

> **I am working on a syntactic data augmentation method for low-resource Indian languages that regenerates masked sentences using LLaMA, extracts linguistically meaningful phrases using parse trees, and back-translates them to create high-quality synthetic training data for neural machine translation.**
