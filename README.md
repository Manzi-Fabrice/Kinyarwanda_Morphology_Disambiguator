# **Kinyarwanda Morphological Disambiguator**

This project implements a morphological disambiguation model for Kinyarwanda, based on the research proposed by Antoine Nzeyimana in the paper "**[Morphological Disambiguation from Stemming Data](https://aclanthology.org/2020.coling-main.409.pdf)**". The implementation focuses on two principal types of feature extraction mentioned  in the paper: **Similarity Features** and **Morphological Features**.

## **Procedure:**

### **Generation of Inflection Forms:**
Given a stem (root), use a Finite-State Transducer (FST) to generate all possible morphological inflections by using the transition graph.

### **Similarity Features:**
Similarity features are constructed to quantify the relationship between a word and its morphological inflection set. Specifically, the following similarity measures are proposed:

**TF-IDF Similarity**: Measures textual similarity based on term frequency-inverse document frequency.

**Cosine Similarity:** Evaluates the cosine angle between vector representations of a word and its set of morphological inflections.

### **Morphological Features:**
Morphological features represents the linguistic plausibility of stem-morpheme combinations using a nonlinear sigmoid-based ratio. This ratio is calculated as the number of times a given stem and morphological feature have been correctly paired divided by the total number of times this pairing has been proposed. The assumption is that some stems inherently lacks specific morphological forms (e.g., passivization).

### **Neural Network Model:**
Both similarity and morphological features are fed into a neural network model trained to predict the correct morphological segmentation.
