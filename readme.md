# 📝 Unsupervised Learning Final Project: Topic Modeling with LDA

## 📌 Project Overview
This project focuses on **Topic Modeling** using **Latent Dirichlet Allocation (LDA)** on the **20 Newsgroups dataset**. The objective is to **identify hidden topics** within text documents and **evaluate their coherence**.

## 📊 Dataset: 20 Newsgroups
- **Contains**: 18,846 text documents across **20 categories**.
- **Task**: Discover thematic structures within the dataset using **unsupervised learning**.

---

## 📂 Table of Contents
1. [Problem Description](#problem-description)
2. [Data Collection and Provenance](#data-collection-and-provenance)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Model Building and Training](#model-building-and-training)
5. [Results and Discussion](#results-and-discussion)
6. [Conclusion](#conclusion)
7. [Installation and Usage](#installation-and-usage)
8. [Future Enhancements](#future-enhancements)
9. [Repository Structure](#repository-structure)
10. [License](#license)

---

## 🔎 Problem Description
Topic Modeling is an **unsupervised learning** technique that helps in:
✅ **Understanding large-scale text data**.  
✅ **Content classification & clustering**.  
✅ **Improving search and recommendation engines**.  

Each **topic** is represented as a **distribution over words**, and each **document** is represented as a **distribution over topics**.

---

## 📥 Data Collection and Provenance
- The dataset is sourced from **[20 Newsgroups Dataset](http://qwone.com/~jason/20Newsgroups/)**
- No additional scraping or modification was performed.
- Dataset is stored in **plain text files**.

---

## 📊 Exploratory Data Analysis (EDA)
- **Dataset contains**: **18,846 documents** across **20 categories**.
- **Balanced category distribution** ensures no model bias.
- **TF-IDF Vectorization** was used to convert text into numerical format.

🔹 **Preprocessing Steps**:
✔ Removal of **special characters, newlines, and extra spaces**.  
✔ **Stop-word removal** for better feature representation.  
✔ **TF-IDF feature extraction** (Top 5,000 words).  

---

## ⚙ Model Building and Training
We implemented **LDA (Latent Dirichlet Allocation)** with **20 topics**, matching the dataset's category count.

### **Modeling Steps**
1. **Preprocess text data** using **TF-IDF**.
2. **Train LDA model** using `sklearn.decomposition.LatentDirichletAllocation`.
3. **Extract topics and top 10 words per topic**.
4. **Evaluate topic coherence** using **Gensim's Coherence Model**.

---

## 📈 Results and Discussion
### **Extracted Topics & Interpretation**
| **Topic ID** | **Top Words** | **Interpretation** |
|-------------|---------------------------------|----------------------|
| **Topic 0** | `edu, apple, drive, mac, university, modem, sale` | **Technology & Education** |
| **Topic 1** | `com, edu, writes, article, subject, organization` | **General Discussions** |
| **Topic 3** | `israel, turkish, armenian, jews, arab, turkey` | **Middle East Politics** |
| **Topic 6** | `team, game, hockey, season, players, sports` | **Sports & Games** |
| **Topic 11** | `god, jesus, bible, christian, church, faith` | **Religion & Theology** |
| **Topic 19** | `windows, file, program, graphics, software` | **Computer Science & Software** |

### **Topic Coherence Evaluation**
- **Best Coherence Score**: **0.43 (with 20 topics)**
- **Lower coherence for >30 topics** (suggests over-segmentation).
- **Lower coherence for <15 topics** (suggests merged themes).

**🔹 Trend Visualization**:  
The **Coherence Score vs. Number of Topics** graph confirms **20 topics as the optimal number**.

---

## 🛠 Installation and Usage
### **Prerequisites**
- Python 3.8+
- Jupyter Notebook
- Required Python libraries:
  ```bash
  pip install numpy pandas matplotlib scikit-learn gensim
