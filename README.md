# AI-Based Multilingual News Categorization System

## Project Overview

This project is an AI-based system that automatically categorizes news articles into different categories. The main aim is to reduce the time required for manual news classification and support news written in multiple languages.

The system uses Natural Language Processing (NLP) techniques and the **XLM-RoBERTa** multilingual transformer model to classify news articles.

## Problem Statement

A large amount of news is published every day in different languages and writing styles. Manually organizing and categorizing this content is time-consuming.

This project provides an automated approach for classifying news articles based on their content.

## Objectives

* Build a multilingual news classification system.
* Automatically identify the category of a news article.
* Support news content written in multiple languages.
* Use XLM-RoBERTa for multilingual text classification.
* Compare the proposed approach with baseline models.
* Analyze classification performance using standard evaluation metrics.
* Identify low-confidence predictions for further review.

## Research Gap

Existing research has already shown that multilingual transformer models can be used for news-related classification. However, classification performance can vary across languages and domains. Large transformer models can also require considerable computational resources.

This project focuses on developing a practical classification pipeline with:

* Language-aware preprocessing
* XLM-RoBERTa based classification
* Confidence-based prediction handling
* Comparison with baseline and multilingual models
* Language-wise and category-wise evaluation

## Proposed System

The proposed workflow is:

```text
News Article
     ↓
Language Detection
     ↓
Text Preprocessing
     ↓
XLM-RoBERTa Tokenization
     ↓
Fine-Tuned XLM-RoBERTa
     ↓
News Category
     ↓
Confidence Score
     ↓
Accept / Review
```

If the confidence of a prediction is below the selected threshold, the article can be marked for further review.

## News Categories

The project considers categories such as:

* Politics
* Sports
* Business
* Technology
* Entertainment
* Health

## Datasets

### AG News Dataset

AG News is a commonly used dataset for news classification.

It contains more than 120,000 news articles and includes:

* World
* Sports
* Business
* Science/Technology

### BBC News Dataset

The BBC News dataset contains news articles from categories including:

* Business
* Entertainment
* Politics
* Sport
* Technology

## Text Preprocessing

The preprocessing stage includes:

1. Text normalization
2. URL removal
3. HTML tag removal
4. Removal of unwanted special characters
5. Tokenization using the XLM-RoBERTa tokenizer

## Model

### XLM-RoBERTa

XLM-RoBERTa is a multilingual transformer model used to process text written in different languages.

In this project, the model is fine-tuned using news datasets so that it can predict the category of a given article.

## Model Comparison

The project plans to compare the following approaches:

| Model                         | Purpose                                    |
| ----------------------------- | ------------------------------------------ |
| TF-IDF + SVM                  | Classical baseline                         |
| mBERT                         | Multilingual baseline                      |
| XLM-RoBERTa                   | Transformer baseline                       |
| Proposed XLM-RoBERTa approach | Enhanced approach with confidence handling |

## Evaluation

The models will be evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Language-wise performance
* Category-wise performance
* Low-confidence/error analysis

Actual performance values will be added after training and testing the models.

## Applications

The system can be useful for:

* Digital news platforms
* Content management systems
* Automated news organization
* News recommendation systems
* Large-scale news analysis

## Technologies Used

* Python
* Natural Language Processing (NLP)
* XLM-RoBERTa
* Machine Learning
* Transformers
* AG News Dataset
* BBC News Dataset

## Team Members

| Name           | Roll No.   |
| -------------- | ---------- |
| G. Surya       | 2420090102 |
| Ch. Siddhartha | 2420090015 |
| Y.V. Likhith   | 2420090142 |
| K. Rishiwan    | 2420030762 |

**Team Number:** 6

**Guide:** KATANGURI SWATHANA
Assistant Professor
Department of Computer Science and Engineering
Koneru Lakshmaiah Education Foundation

## Future Work

* Add more multilingual news datasets.
* Test the system on Indian-language news.
* Test code-mixed news content.
* Improve classification performance for low-confidence cases.
* Reduce model inference time.
* Evaluate the system using larger real-world news data.

## Conclusion

The project aims to provide an automated multilingual news categorization system using NLP and XLM-RoBERTa. The proposed work goes beyond basic classification by including language-aware preprocessing, confidence-based handling and comparison with existing baseline approaches.

The final improvement will be justified through experimental results and comparative evaluation.
