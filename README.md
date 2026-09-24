# AI-Based News Categorization System

## Project Overview

This project is an AI-based system for automatically categorizing news articles based on their content.

The project initially explored conventional machine learning and multilingual transformer-based approaches. For the current Review-2 phase, the system is being extended into a more project-specific approach called the **Adaptive News Fingerprint Engine (ANFE)**.

ANFE is designed to combine multiple forms of evidence from a news article, including:

* Lexical evidence
* Entity/domain evidence
* Structural evidence
* Source/category evidence
* Adaptive scoring
* Confidence-based decision handling

The aim is to move beyond simply applying an existing classification model and develop a more interpretable and adaptive news categorization workflow.

---

## Problem Statement

A large amount of news is published every day across different topics, sources, and writing styles. Manually organizing this content into meaningful categories is time-consuming.

Traditional machine learning and transformer-based approaches can classify news effectively, but they generally focus on learning a classification boundary from text representations.

This project explores a different approach by combining multiple evidence signals and using adaptive decision handling to determine whether a classification should be accepted or sent for further review.

---

## Objectives

* Build an automated news categorization system.
* Automatically identify the category of a news article.
* Develop a project-specific classification workflow rather than directly reproducing an existing research model.
* Combine lexical, entity, structural and source-level evidence.
* Introduce adaptive scoring for classification decisions.
* Identify low-confidence predictions and mark them for review.
* Compare the proposed approach with existing machine learning and multilingual approaches.
* Evaluate the system using standard classification metrics.
* Analyze errors and low-confidence predictions.

---

## Research Gap

Existing research has extensively explored approaches such as:

* Support Vector Machines
* Convolutional Neural Networks
* BERT
* mBERT
* XLM-RoBERTa
* Other multilingual and transformer-based architectures

These approaches primarily focus on learning representations and predicting a category from the input text.

The current project explores a more integrated decision workflow rather than directly reproducing one of these existing models.

### Proposed Research Direction

The **Adaptive News Fingerprint Engine (ANFE)** combines:

* **Lexical evidence** from the article text
* **Entity/domain evidence** from important names and terms
* **Structural evidence** from different parts of the article
* **Source/category evidence**
* **Adaptive evidence weighting**
* **Confidence-based ACCEPT / REVIEW decisions**

The goal is to make the classification process more transparent and capable of identifying uncertain predictions rather than forcing every article into a category.

---

## Review-1 Baseline

During Review-1, a classical machine learning baseline was established using:

```text
News Article
     ↓
Text Preprocessing
     ↓
TF-IDF Feature Extraction
     ↓
Chi-Square Feature Selection
     ↓
Linear SVM
     ↓
News Category
```

The Review-1 baseline achieved:

| Metric             |     Result |
| ------------------ | ---------: |
| Accuracy           | **80.28%** |
| Weighted Precision | **80.36%** |
| Weighted Recall    | **80.28%** |
| Weighted F1-Score  | **79.80%** |

These results provide the baseline against which the Review-2 approach can be evaluated.

---

## Proposed System: ANFE

The current proposed system is the **Adaptive News Fingerprint Engine (ANFE)**.

The workflow is:

```text
                         News Article
                              ↓
                     Text Preprocessing
                              ↓
              ┌───────────────┼───────────────┐
              ↓               ↓               ↓
        Lexical Evidence  Entity Evidence  Structural Evidence
              ↓               ↓               ↓
              └───────────────┼───────────────┘
                              ↓
                    Source / Domain Evidence
                              ↓
                     Adaptive Scoring
                              ↓
                  Evidence Combination
                              ↓
                 ┌────────────┴────────────┐
                 ↓                         ↓
              ACCEPT                    REVIEW
                 ↓                         ↓
          News Category             Human / Further
                                    Analysis
```

Unlike a conventional single-model classification pipeline, ANFE is designed to combine multiple evidence sources before making the final decision.

---

## ANFE Components

### 1. Lexical Evidence

The system analyzes important words and phrases appearing in the article.

This provides the primary textual evidence for identifying the likely category.

### 2. Entity and Domain Evidence

Important entities, names, organizations, locations and domain-specific terms are considered as additional evidence.

This helps distinguish articles that may use similar vocabulary but belong to different domains.

### 3. Structural Evidence

Different sections of an article can provide different amounts of information.

ANFE considers structural information such as:

* Title
* Description
* Main article content

The agreement between these parts contributes to the classification decision.

### 4. Source / Category Evidence

The system can also use information associated with the news source and previously observed category patterns as supporting evidence.

### 5. Adaptive Scoring

Instead of relying on a single fixed signal, ANFE combines available evidence using adaptive weighting.

The contribution of an evidence source can be adjusted depending on whether that information is available and useful for the article.

### 6. Confidence-Based Decision

The final classification includes a confidence or evidence-margin assessment.

If the evidence is sufficiently strong:

```text
Prediction → ACCEPT
```

If the evidence is ambiguous:

```text
Prediction → REVIEW
```

This prevents uncertain articles from being treated as equally reliable predictions.

---

## Dataset

The project uses a news dataset containing **1,458 records**.

The dataset contains information such as:

* News title
* Description
* Article content
* Category
* Language
* Country
* Source information
* Other article metadata

The dataset is used to develop and evaluate the proposed news categorization workflow.

---

## News Categories

The dataset contains multiple news-category combinations.

For the current project evaluation, the main target categories considered in the classification workflow include:

* Politics
* Business
* Technology

Additional categories and labels present in the dataset can be analyzed during further experimentation.

---

## Text Preprocessing

The preprocessing pipeline includes:

1. Text normalization
2. URL removal
3. HTML/tag removal
4. Removal of unwanted special characters
5. Whitespace normalization
6. Tokenization
7. Preparation of text for evidence extraction

The Review-2 system additionally extracts information useful for:

* Lexical fingerprints
* Entity/domain evidence
* Structural evidence
* Source-level evidence

---

## Model Comparison

The project compares the proposed workflow with established approaches.

| Approach            | Role                                       |
| ------------------- | ------------------------------------------ |
| TF-IDF + Linear SVM | Review-1 classical baseline                |
| Character-level CNN | Existing research approach                 |
| BERT                | Existing Transformer approach              |
| mBERT               | Existing multilingual approach             |
| XLM-RoBERTa         | Existing multilingual Transformer approach |
| **ANFE**            | **Proposed Review-2 approach**             |

The comparison will consider standard metrics such as:

* Accuracy
* Precision
* Recall
* F1-Score

The project will also analyze the additional behavior of ANFE through:

* Low-confidence predictions
* Review rate
* Error analysis
* Evidence-based decision analysis

---

## Evaluation

The systems will be evaluated using:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-Score**
* **Confusion Matrix**
* **Category-wise performance**
* **Low-confidence/error analysis**
* **Review rate**

Review-1 currently provides the baseline results.

ANFE metrics will be added after the Review-2 implementation is executed and evaluated using the project dataset.

---

## Key Difference from Existing Approaches

The primary difference of the proposed Review-2 work is not simply using another existing classifier.

Instead, the project focuses on building a **multi-evidence adaptive classification workflow**.

```text
Existing Approaches
       ↓
Text Representation
       ↓
Classification Model
       ↓
Prediction


Proposed ANFE
       ↓
Lexical Evidence
       +
Entity Evidence
       +
Structural Evidence
       +
Source/Domain Evidence
       ↓
Adaptive Scoring
       ↓
Confidence Assessment
       ↓
ACCEPT / REVIEW
       ↓
Final Category
```

This provides a project-specific direction for experimenting with interpretable evidence fusion and uncertainty handling in news categorization.

---

## Applications

The system can be useful for:

* Digital news platforms
* Automated news organization
* Content management systems
* News recommendation systems
* News monitoring systems
* Large-scale news analysis
* Automated content filtering

---

## Technologies Used

* Python
* Natural Language Processing (NLP)
* Machine Learning
* Text Classification
* TF-IDF
* Linear SVM
* Transformers
* Multilingual NLP
* ANFE
* Antigravity
* Dataset-based evaluation

---

## Development Environment

The project is currently being developed and experimented with using **Antigravity** as the primary development environment.

Additional tools may be used for experimentation, evaluation and visualization when required.

---

## Team Members

| Name            | Roll No.   |
| --------------- | ---------- |
| G. Surya        | 2420090102 |
| Ch. Siddhartha  | 2420090015 |
| Y.V. Likhith    | 2420090142 |
| K. Rishiwan     | 2420030762 |
| R. Sai Sidhardh | 2400032486 |

**Team Number:** 6

**Guide:** KATANGURI SWATHANA
Assistant Professor
Department of Computer Science and Engineering
Koneru Lakshmaiah Education Foundation

---

## Future Work

* Complete the ANFE implementation.
* Evaluate ANFE on the project dataset.
* Compare ANFE against the Review-1 baseline.
* Compare results with existing research approaches.
* Perform category-wise error analysis.
* Analyze low-confidence predictions.
* Improve adaptive evidence weighting.
* Extend the system to additional languages.
* Test the system on Indian-language and code-mixed news.
* Explore larger real-world news datasets.
* Optimize inference time and scalability.

---

## Conclusion

This project aims to develop an automated news categorization system using Natural Language Processing and machine learning techniques.

The project began with a classical **TF-IDF + Chi-square + Linear SVM** baseline during Review-1.

For Review-2, the project introduces the **Adaptive News Fingerprint Engine (ANFE)**, a project-specific workflow that combines lexical, entity, structural and source-level evidence with adaptive scoring and confidence-based **ACCEPT / REVIEW** decisions.

The final contribution will be validated through experimental evaluation and comparison with existing approaches using standard classification metrics.

The objective is to develop a practical and interpretable news categorization workflow while identifying and analyzing uncertain predictions rather than treating every classification as equally reliable.
