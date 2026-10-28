# 🍽️ Restaurant Segmentation Using Reviews & Metadata

This project implements an **end-to-end machine learning pipeline** to segment restaurants based on **customer reviews, pricing, popularity, cuisine types, and operational characteristics**. The objective is to derive meaningful clusters that can support **business decisions in marketing, pricing, and service optimization**.

---

## 📌 Problem Statement

The restaurant industry generates large volumes of structured and unstructured data such as customer reviews, ratings, pricing, and operational details. However, this data is rarely transformed into actionable insights.

This project aims to:
- Convert raw restaurant data and customer reviews into a structured analytical format
- Apply **unsupervised machine learning** to segment restaurants into meaningful groups
- Compare multiple clustering algorithms to identify the most effective approach
- Interpret the results for **real-world business impact**

---

## 📂 Datasets Used

### 1️⃣ Restaurant Metadata  
Contains restaurant-level attributes:
- Restaurant Name  
- Cost  
- Cuisines  
- Timings  
- Pictures  
- Total Reviews  
- Total Followers  

### 2️⃣ Customer Reviews  
Contains review-level data:
- Restaurant Name  
- Reviewer  
- Review Text  
- Rating  
- Review Date/Time  
- Review Engagement Metrics  

These datasets were merged and aggregated to create a **restaurant-level analytical dataset**.

---

## 🔧 Project Workflow

### 1. Data Understanding
- Inspected dataset structure using `.info()`, `.describe()`, and `.head()`
- Identified numerical, categorical, and textual features

### 2. Data Cleaning & Preprocessing
- Handled missing values using median imputation and logical replacements
- Removed duplicates and inconsistencies
- Processed textual data using NLP techniques

### 3. Text Preprocessing (NLP)
- Lowercasing
- Removing punctuation, URLs, and stopwords
- Tokenization
- Lemmatization
- TF-IDF Vectorization

### 4. Feature Engineering
- Grouped cuisines into broader categories (Indian, Asian, Western, etc.)
- Extracted operational features from timings (open hours, late night, breakfast, etc.)
- Created composite features:
  - **Popularity Score**
  - **Value for Money**

### 5. Outlier Handling
- Identified outliers using the IQR method
- Applied capping and log transformations for skewed features

### 6. Feature Selection
- Removed highly correlated and low-variance features
- Retained only business-relevant attributes

### 7. Scaling & Transformation
- Standardized numerical features using **StandardScaler**

### 8. Dimensionality Reduction
- Applied **PCA** for 2D visualization of clusters

---

## 🤖 Machine Learning Models

### 🔹 Model 1: K-Means Clustering
- Primary segmentation model
- Tuned number of clusters using evaluation metrics
- Achieved best cluster separation and compactness

### 🔹 Model 2: DBSCAN
- Density-based clustering
- Failed to form meaningful clusters for this dataset (most points labeled as noise)
- Demonstrated unsuitability for this data distribution

### 🔹 Model 3: Hierarchical Clustering
- Agglomerative approach
- Produced interpretable but broader clusters
- Lower performance compared to K-Means

---

## 📊 Model Evaluation Metrics

| Metric | Purpose | Business Meaning |
|--------|--------|------------------|
| **Silhouette Score** | Measures cluster separation | Clear customer/restaurant segmentation |
| **Davies–Bouldin Index** | Measures cluster compactness | Reliability of clusters |
| **Inertia** | Measures within-cluster variance | Tightness of groups |

---

## 🏆 Final Model Selection

**K-Means was selected as the final model** because it:
- Achieved the **highest Silhouette Score**
- Had the **lowest Davies–Bouldin Index**
- Produced **stable and interpretable clusters**
- Scaled efficiently for large datasets

---

## 🔍 Model Explainability

Since clustering is unsupervised:
- Feature importance was derived using **centroid-based analysis**
- Variance across cluster centroids identified key drivers:
  - Cost
  - Rating
  - Popularity
  - Cuisine Categories
  - Service Availability
  - Value for Money

---

## 📈 Visualization

- **PCA plots** for K-Means, DBSCAN, and Hierarchical clustering
- **Centroid visualization** for K-Means
- **Box plots** for outlier detection
- **Correlation heatmaps** for feature selection

---

## 💼 Business Impact

The clustering results support:

✔ Targeted marketing and promotions  
✔ Personalized restaurant recommendations  
✔ Pricing strategy optimization  
✔ Operational improvements  
✔ Identification of niche or underperforming restaurants  

---

## 📌 Technologies Used

- **Python**
- **Pandas, NumPy**
- **Matplotlib, Seaborn**
- **Scikit-learn**
- **NLTK / Text Processing**
- **Jupyter Notebook**

---

## ▶️ How to Run the Project

1. Clone the repository:
   ```bash
   git clone <repository_url>
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn nltk
    ```
3. Open the notebook:
    ```bash
    jupyter notebook
    ```
4. Run all cells in sequence.

## 📄 Project Report

A detailed Word (DOCX) project report is included with:

- Step-by-step explanations  
- Placeholders for code, plots, and screenshots  
- Business interpretation and conclusions  

---

## 🎯 Conclusion

This project demonstrates how machine learning and NLP can transform raw restaurant data into actionable business intelligence. By evaluating multiple clustering algorithms and selecting the most suitable model, the project delivers meaningful segmentation that supports data-driven decisions in the hospitality industry.

**K-Means clustering emerges as the most effective model**, providing scalable, interpretable, and business-aligned restaurant segmentation.

---

## 🙌 Acknowledgements

- Zomato Dataset  
- Scikit-learn Documentation  
- NLTTK Documentation  

---

## 📬 Contact

For questions, suggestions, or collaboration, feel free to connect.

---

