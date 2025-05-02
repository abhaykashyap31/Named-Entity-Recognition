# Named Entity Recognition Using Hidden Markov Model (HMM)

## Overview

This project implements a **Named Entity Recognition (NER)** system using a **Hidden Markov Model (HMM)** from scratch, without relying on external NLP libraries. The system is designed to classify words from Twitter data into 10 fine-grained named entity types, including:

* Person
* Product
* Company
* Geolocation
* Movie
* Music Artist
* TV Show
* Facility
* Sports Team
* Others

The primary goal is to explore the effectiveness of statistical sequence modeling for informal social media text.

---

## Features

* Built four HMM models:

  1. **Bigram without context**
  2. **Trigram without context**
  3. **Bigram with contextual emission**
  4. **Trigram with contextual emission**
* Trained and evaluated on annotated Twitter datasets using BIO tagging.
* Implemented:

  * Maximum Likelihood Estimation with Laplace smoothing
  * Viterbi decoding algorithm
  * Context-based emission enhancements
  * Special handling for unknown tokens

---

## Results

| Model                  | Accuracy | Precision | Recall | F1 Score |
| ---------------------- | -------- | --------- | ------ | -------- |
| Bigram (No Context)    | 75.38%   | 0.2062    | 0.0841 | 0.1194   |
| Trigram (No Context)   | 75.99%   | 0.1406    | 0.0824 | 0.1039   |
| Bigram (With Context)  | 76.45%   | 0.1634    | 0.0729 | 0.1009   |
| Trigram (With Context) | 77.82%   | 0.1451    | 0.0824 | 0.1051   |

---

## Key Observations

* **Trigram with context** had the highest **accuracy** (77.82%).
* **Bigram without context** had the best **F1 score** (0.1194), suggesting better balance between precision and recall.
* Rare entities (like music artists, movies) were hard to detect due to severe class imbalance.
* Optimal Laplace smoothing parameter **α = 0.4** offered a balance between accuracy and entity detection.

---

## Challenges

* **Extreme class imbalance**: \~95% tokens labeled as non-entities.
* **Poor performance** on rare entities.
* **Informal Twitter language**: Abbreviations, hashtags, creative spellings affected precision.

---

## Future Work

* Incorporate advanced smoothing techniques.
* Explore data augmentation to improve rare entity recognition.
* Investigate neural architectures like BiLSTM-CRF or Transformers for better results on informal text.

---

## Dataset

* Annotated Twitter dataset with BIO-tagged named entities.
* Statistics:

  * Average sentence length: 19.41 tokens
  * Average entity length: 1.65 tokens
  * Total entities: 1,496


