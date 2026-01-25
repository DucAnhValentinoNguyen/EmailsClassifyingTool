# EmailsClassifyingTool
An intelligent email assistant using Llama helping users automatically classify their incoming emails: The system will identify which emails need immediate attention, which are regular updates, and which are promotions that can wait or be archived.

The Data
You'll work with a dataset of various email examples, ranging from urgent business communications to promotional offers. Here's a peek at what you'll be working with:

# Email Classification for NLP Task Prioritization

This repository contains a text classification pipeline designed to categorize emails into functional buckets. This project serves as a foundational component of my PhD research in Natural Language Processing, focusing on intent recognition and document classification.

## Dataset Specification

The model is trained and validated using `email_categories_data.csv`. The dataset follows the schema below:

| Column | Description |
| :--- | :--- |
| **email_id** | A unique identifier for each email record to ensure traceability during error analysis. |
| **email_content** | The raw text input. Format: `[Subject]` followed by a `\n` newline and the `[Message Body]`. |
| **expected_category** | The ground-truth label for evaluation. Labels: `Priority`, `Updates`, or `Promotions`. |

---

## Technical Approach

### 1. Data Preprocessing
Given the structure of the `email_content`, the pipeline includes a custom parsing step to differentiate between the Subject line and the Body. In NLP, the Subject often contains the highest "information gain," and is treated as a priority feature.

[Image of a typical text classification pipeline including tokenization, vectorization, and model training]

### 2. Proposed Methodology
* **Baseline:** N-gram TF-IDF vectorization with a Multinomial Naive Bayes classifier.
* **Deep Learning:** Fine-tuning a `distilbert-base-uncased` transformer model to capture the semantic context between the subject and the body.

### 3. Evaluation Metrics
To ensure a robust PhD-level analysis, the model is evaluated using
