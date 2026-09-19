# Sentiment Analysis of YouTube Comments on the Weakening of the Rupiah Exchange Rate

## 📌 Overview

This project analyzes public YouTube comments related to the weakening of the Indonesian Rupiah exchange rate to identify audience sentiment and extract insights from online discussions.

The project applies a Natural Language Processing (NLP) pipeline to collect, preprocess, explore, and classify YouTube comments into three sentiment categories: **Negative, Neutral, and Positive**.

The analysis combines text preprocessing, sentiment distribution analysis, word frequency visualization, and machine learning classification using **TF-IDF and Multinomial Naive Bayes**.

---

## 🎯 Objectives

* Collect YouTube comments related to discussions about the Rupiah exchange rate.
* Clean and preprocess Indonesian text data for NLP analysis.
* Analyze the distribution and characteristics of audience sentiment.
* Build a machine learning model to classify comments into Negative, Neutral, and Positive categories.
* Evaluate the performance of the sentiment classification model.

---

## 🔄 Project Workflow

### 1. Data Collection

YouTube comments were collected from **three relevant YouTube videos** using the **YouTube Data API** and `google-api-python-client`.

The collected data includes comment text, video ID, comment ID, and publication timestamp.

**Total comments collected: 1,128**

### 2. Data Preprocessing

The raw comments were processed to reduce noise and prepare the text for NLP analysis.

The preprocessing pipeline includes:

* Text cleaning
* Duplicate checking
* Stopword removal
* Indonesian stopword filtering
* Stemming
* Text normalization

A customized stopword list was also used to remove words considered less informative for this analysis.

### 3. Sentiment Labeling

The processed comments were categorized into three sentiment classes:

* **Negative**
* **Neutral**
* **Positive**

The labeled dataset was then analyzed to understand the overall sentiment distribution within the collected comments.

### 4. Exploratory Text Analysis

Several visualizations were created to explore the characteristics of the discussions, including:

* Sentiment distribution
* Sentiment comparison before and after resampling
* WordCloud for positive comments
* WordCloud for negative comments

These visualizations provide an overview of frequently occurring words and expressions within each sentiment category.

### 5. Handling Class Imbalance

The sentiment classes were not evenly distributed. To reduce potential bias toward the majority class, **oversampling** was applied to the minority sentiment classes.

This process provided a more balanced representation of the three sentiment categories before model training.

### 6. Feature Extraction

The processed text was transformed into numerical features using **TF-IDF (Term Frequency–Inverse Document Frequency)**.

Both unigram and bigram features were used:

`TfidfVectorizer(ngram_range=(1, 2))`

This approach allows the model to capture individual words as well as two-word combinations that may provide additional contextual information.

### 7. Sentiment Classification

A **Multinomial Naive Bayes** classifier was trained using the TF-IDF features.

The dataset was divided into training and testing sets, and the model was trained to classify comments into **Negative, Neutral, and Positive** categories.

Model performance was evaluated using accuracy, precision, recall, and F1-score.

---

## 📈 Results

The final **Multinomial Naive Bayes** model achieved an accuracy of approximately:

**78.62% Accuracy**

The classification results showed different performance levels across the three sentiment categories. The model demonstrated strong performance in identifying positive comments, while the neutral and negative classes showed different precision-recall trade-offs.

The analysis also revealed varying sentiment within YouTube discussions surrounding the weakening of the Rupiah, which was further explored through sentiment distributions and sentiment-specific WordClouds.

---

## 💡 Key Findings

* **1,128 YouTube comments** were collected from three videos discussing the Rupiah exchange rate.
* Text preprocessing was necessary to reduce noise and improve the quality of NLP features.
* **Oversampling** was applied to address class imbalance.
* **TF-IDF with unigram and bigram features** was used for feature extraction.
* **Multinomial Naive Bayes** was used for sentiment classification.
* The model achieved approximately **78.62% accuracy**.
* WordCloud analysis provided additional insight into frequently occurring terms within positive and negative discussions.

---

## 🛠️ Tools & Technologies

| Category           | Tools                                 |
| ------------------ | ------------------------------------- |
| Programming        | Python                                |
| Environment        | Google Colab                          |
| Data Collection    | YouTube Data API                      |
| Data Processing    | Pandas, NumPy                         |
| NLP                | NLTK                                  |
| Feature Extraction | TF-IDF                                |
| Machine Learning   | Scikit-learn, Multinomial Naive Bayes |
| Visualization      | Matplotlib, Seaborn, WordCloud        |

---

## 📂 Repository Contents

| File                                       | Description                                                              |
| ------------------------------------------ | ------------------------------------------------------------------------ |
| `AnalisisSentimen_KursRupiah.ipynb`        | Complete data collection, preprocessing, analysis, and modeling workflow |
| `Hasil-Labeling-Kurs-Rupiah.csv`           | Labeled sentiment dataset                                                |
| `Hasil-Preprocesing-KursRupiah-Update.csv` | Processed text dataset                                                   |
| `naive_bayes_model_kursrupiah.pkl`         | Trained Multinomial Naive Bayes model                                    |
| `tfidf_vectorizer_kursrupiah.pkl`          | Trained TF-IDF vectorizer                                                |
| `stopwords_kurs_rupiah.txt`                | Customized stopword list                                                 |
| `PPT Analisis Sentimen Kurs Rupiah.pdf`    | Project presentation and analysis results                                |

---

## 🧠 Skills Demonstrated

* Data Collection & Web API
* Data Cleaning & Preprocessing
* Natural Language Processing (NLP)
* Exploratory Data Analysis
* Text Feature Engineering
* Sentiment Analysis
* Machine Learning Classification
* Model Evaluation
* Data Visualization

---

## 🏁 Conclusion

This project demonstrates an **end-to-end NLP workflow** for extracting sentiment insights from unstructured social media data.

Starting from YouTube comment collection, the project covers **data preprocessing, sentiment labeling, exploratory analysis, class balancing, TF-IDF feature extraction, machine learning classification, and model evaluation**.

The resulting **Multinomial Naive Bayes model achieved 78.62% accuracy**, demonstrating how traditional NLP techniques combined with machine learning can be used to classify Indonesian-language YouTube comments and provide a structured view of audience sentiment toward discussions surrounding the Rupiah exchange rate.
