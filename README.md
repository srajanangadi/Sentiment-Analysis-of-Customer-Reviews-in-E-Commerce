**Sentiment Analysis of E-Commerce Customer Review**

This project performs sentiment analysis on laptop reviews from Flipkart using Natural Language Processing (NLP) and Machine Learning techniques. The goal is to automatically classify customer reviews as positive, neutral, or negative, analyze product aspects, and evaluate the relationship between numerical ratings and textual sentiment.
The project compares traditional machine learning models with transformer-based deep learning models to determine the most effective approach for analyzing large-scale e-commerce review data.

**Project Overview**

Online shopping platforms generate thousands of product reviews, making it difficult for customers and businesses to analyze feedback manually.
This project uses NLP techniques and sentiment classification models to extract meaningful insights from customer reviews.

*Key goals of this project:*

Classify review sentiment (Positive / Neutral / Negative)
Compare traditional ML models with transformer-based models
Handle class imbalance in review datasets
Extract sentiment related to specific product features
Analyze correlation between ratings and textual sentiment

**Dataset**

Dataset used in this project:
Flipkart Laptop Reviews Dataset
Total Reviews: 24,113

Source: Kaggle

Brands included:
Apple
HP
Lenovo
ASUS
Acer
MSI

Each review contains:

Product name
Review title
Review text
Star rating

Sentiment labels were created from ratings:

Rating	Sentiment
1–2 stars	Negative
3 stars	Neutral
4–5 stars	Positive
Project Pipeline

The entire workflow is implemented in a Jupyter Notebook.

1. Data Collection
The dataset was obtained from Kaggle and imported using Pandas.

2. Data Preprocessing
Text preprocessing was performed using NLP libraries such as SpaCy and NLTK.

Steps included:
Removing HTML tags
Removing URLs
Emoji normalization
Expanding contractions
Lowercasing text
Tokenization
Stopword removal
Lemmatization

3. Exploratory Data Analysis

Basic analysis was performed to understand the dataset.
*Key insights:*
Majority of reviews are positive (~81%)
Negative reviews account for ~10%
Neutral reviews account for ~8%
This created a class imbalance problem.

4. Dataset Balancing

To improve classification performance on minority classes, balancing techniques were used:
- Random Oversampling
- SMOTE (Synthetic Minority Oversampling Technique)

5. Feature Engineering

Two feature extraction approaches were used.
*Traditional Models*
- TF-IDF vectorization
- Unigrams and bigrams
- Review metadata features
*Deep Learning Models*
- Word2Vec embeddings
- FastText embeddings
- BERT embeddings

**Machine Learning Models**

The following models were implemented and compared:
*Traditional Machine Learning Models*
- Naive Bayes
- Logistic Regression
- Support Vector Machine (SVM)
- Deep Learning Model
*BERT (Bidirectional Encoder Representations from Transformers)*
- BERT was fine-tuned for sentiment classification using PyTorch and HuggingFace Transformers.
Model Evaluation

Models were evaluated using:
-Accuracy
-Precision
-Recall
-F1-score
-Confusion Matrix
-ROC-AUC
-Training split:
-80% training
-10% validation
-10% testing

*Results*
Unbalanced Dataset

| Model               | Accuracy          | Macro F1               |
| ------------------- | ----------------- | ---------------------- |
| Naive Bayes         | Lower performance | Poor neutral detection |
| Logistic Regression | ~90%              | Moderate               |
| SVM                 | ~91%              | Good                   |
| BERT                | **~95%**          | **Best performance**   |

BERT showed significantly better classification of minority classes.

**Balanced Dataset**

Balancing improved traditional models:
- Higher recall for neutral and negative classes
- More stable classification performance
BERT remained the most accurate model overall.

**Aspect-Based Sentiment Analysis**

Aspect-based sentiment analysis was performed to extract sentiment related to specific laptop features.
*Key aspects analyzed:*
Battery Life
Performance
Display
Design
Dependency parsing and transformer-based classification were used to detect sentiment at the feature level.
The model achieved over 85% accuracy for aspect sentiment classification.
Rating vs Sentiment Analysis
The study also compared numerical star ratings with textual sentiment.

**Results:**

Pearson Correlation: **0.649**
Inconsistency Rate: **13.6%**
This means that star ratings and textual sentiment do not always perfectly align.

*Examples observed:*

Positive rating but negative text
Negative rating but positive text
Mixed sentiment in neutral ratings
This highlights the importance of analyzing review text instead of relying only on ratings.

**Technologies Used**

*Programming Language:*
Python

*Libraries and Tools:*
Pandas
NumPy
SpaCy
NLTK
Scikit-learn
Imbalanced-learn
Gensim
HuggingFace Transformers
PyTorch
Matplotlib
Seaborn

*Development Environment:*
Jupyter Notebook

**Project Structure**

laptop-review-sentiment-analysis
│
├── README.md
├── notebook
│   └── sentiment_analysis.ipynb
│
├── report
│   └── project_report.pdf
│
├── images
│   ├── sentiment_distribution.png
│   ├── confusion_matrix.png
│   └── aspect_analysis.png
│
└── requirements.txt

**Key Findings**

Transformer-based models outperform traditional machine learning models for sentiment classification.
Class imbalance significantly affects traditional models.
Dataset balancing improves minority class detection.
Aspect-based sentiment analysis provides deeper insights into product features.
Star ratings alone cannot fully represent customer opinions.

**Conclusion**

This project demonstrates that advanced transformer models like BERT provide the most reliable approach for sentiment analysis in e-commerce review data.
Combining sentiment classification, aspect analysis, and rating comparison provides a more comprehensive understanding of customer feedback.

These techniques can help businesses:
Improve product quality
Monitor customer sentiment
Enhance recommendation systems
Identify feature-level issues quickly

**Future Improvements**

Potential improvements for this project include:
Multilingual sentiment analysis for Indian languages
Fake review detection
Real-time sentiment monitoring
More advanced aspect extraction techniques
Integration with recommendation systems
Applying the model to other product categories

**References**

Key research papers and studies referenced in this project include works related to:
Sentiment analysis in e-commerce
Transformer-based NLP models
Aspect-based sentiment analysis
Deep learning approaches for text classification
