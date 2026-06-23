# Hybrid PEFT Framework for Idiomatic Multilingual Neural Machine Translation

## Overview

This research presents a Hybrid Parameter-Efficient Fine-Tuning (PEFT) framework for idiomatic multilingual Neural Machine Translation (NMT) using the mBART-50 architecture. The proposed approach combines Houlsby-style adapter modules with selective Transformer layer adaptation to improve translation quality for idiomatic expressions while significantly reducing the number of trainable parameters.

Idiomatic expressions remain one of the most challenging aspects of machine translation due to their non-compositional nature and cultural dependence. While full fine-tuning achieves strong performance, it requires updating hundreds of millions of parameters, making deployment computationally expensive. This work investigates whether parameter-efficient adaptation techniques can preserve translation quality while substantially reducing training costs.

The proposed framework is evaluated on English–Hindi and English–Marathi translation tasks using both idiomatic and generalized datasets. Experimental results demonstrate that high translation quality can be maintained while training less than one-third of the model parameters.

---

## Research Objectives

The primary objectives of this research are:

* Develop a parameter-efficient multilingual NMT framework for idiomatic translation.
* Investigate the effectiveness of Houlsby adapters combined with selective layer adaptation.
* Reduce computational and memory requirements compared to full fine-tuning.
* Evaluate translation quality across morphologically diverse Indian languages.
* Analyze the trade-off between parameter efficiency and translation performance.

---

## Dataset Development

To support idiomatic multilingual translation research, bilingual datasets were constructed for English–Hindi and English–Marathi language pairs.

### Dataset Characteristics

* Approximately 15,000 English–Hindi idiomatic sentence pairs.
* Approximately 15,000 English–Marathi idiomatic sentence pairs.
* Additional generalized-domain sentence pairs for comparative evaluation.
* Idiomatic expressions collected from multiple linguistic resources and contextualized into complete sentences using Large Language Models.
* Human verification and filtering performed to ensure semantic consistency and translation quality.

---

## Proposed Hybrid PEFT Framework

The proposed architecture is based on the pretrained mBART-50 multilingual sequence-to-sequence model.

### Key Components

1. Freeze the lower six encoder layers and lower six decoder layers.
2. Fine-tune only the upper six encoder and decoder layers.
3. Insert Houlsby-style adapter modules within Transformer blocks.
4. Train adapter parameters together with selected Transformer layers.
5. Preserve multilingual knowledge learned during pretraining while adapting efficiently to idiomatic translation.

### Motivation

Traditional full fine-tuning updates all model parameters, resulting in high computational cost and memory consumption. The proposed Hybrid PEFT framework focuses adaptation on the most task-relevant layers while leveraging lightweight adapter modules to learn idiomatic translation patterns.

---

## Experimental Setup

### Base Model

* mBART-50 Multilingual Sequence-to-Sequence Transformer

### Training Configuration

* Mixed Precision Training (BF16)
* Early Stopping Strategy
* AdamW Optimizer
* Train/Validation/Test Split: 80/10/10
* NVIDIA A100 GPU

### Evaluation Metrics

* BLEU
* chrF++
* COMET

### Compared Configurations

* Full Fine-Tuning
* Houlsby Adapter Only
* Adapter + Half Encoder Fine-Tuning
* Adapter + Half Decoder Fine-Tuning
* Proposed Hybrid PEFT Framework

---

## Results

The proposed Hybrid PEFT framework achieved competitive performance while training only approximately 30% of the total model parameters.

Across all evaluation settings, the proposed model retained:

* 101.14% of the fully fine-tuned BLEU performance
* 96.40% of the fully fine-tuned chrF++ performance
* 98.47% of the fully fine-tuned COMET performance

These results demonstrate that substantial reductions in trainable parameters can be achieved without significant degradation in translation quality.

---

## Key Contributions

* Proposed a Hybrid PEFT framework combining Houlsby adapters and selective Transformer layer adaptation.
* Developed idiomatic multilingual datasets for English–Hindi and English–Marathi translation.
* Demonstrated effective idiomatic translation using only approximately 30% trainable parameters.
* Performed comprehensive ablation studies to analyze parameter-efficiency trade-offs.
* Investigated the impact of parameter-efficient adaptation on morphologically rich Indian languages.

---

## Research Outcomes

* M.Tech Thesis completed at the National Institute of Technology Hamirpur.
* Research manuscript prepared based on the proposed Hybrid PEFT framework.
* Manuscript currently under review and being finalized for submission to a peer-reviewed conference/journal venue.

---

## Future Work

Future research directions include:

* Extension to additional Indian languages.
* Integration with larger multilingual foundation models.
* Investigation of LoRA and other modern PEFT techniques.
* Domain adaptation for legal, healthcare, and conversational translation.
* Incorporation of linguistic and cultural knowledge for improved idiomatic understanding.

---

## Supervisor

Dr. Arun Kumar Yadav
Department of Computer Science and Engineering
National Institute of Technology Hamirpur

---

## Keywords

Neural Machine Translation, Multilingual NLP, mBART-50, PEFT, Adapter Tuning, Houlsby Adapters, Idiomatic Translation, English-Hindi Translation, English-Marathi Translation, Low-Resource Languages, Transformer Models

--------

<!-- 
### Presentation  
=> [Download PPT Presentation](Research_Presentation__Mrunal.pdf)
-->

