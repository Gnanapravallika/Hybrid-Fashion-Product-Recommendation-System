# 🛍️ Hybrid E-commerce Product Recommendation System

An advanced **Machine Learning project** designed to provide **personalized product suggestions** for an e-commerce platform by combining **user behavioral data** and **product content features**.

---

## ✨ Key Project Highlights

### 🚀 1. Robust Hybrid Recommendation Engine
- Combined **Content-Based Filtering (CBF)** and **Collaborative Filtering (CF)**.
- Mitigates the *cold-start problem* and ensures both **high relevance** and **product discoverability**.
- Achieves superior recommendation accuracy by leveraging the strengths of both models.

### 🧠 2. Scalable ML Algorithms
- Used **Singular Value Decomposition (SVD)** from `scikit-surprise` for CF.
- Computed **Cosine Similarity** on **TF-IDF** product vectors for CBF.
- Ensures scalable, personalized predictions across users and products.

### 🗂️ 3. Real-World E-commerce Data Integration
- Processed a dataset containing **User Ratings** and **Product Metadata** (*Brand, Category, Color, Size*).
- Delivered a **combined hybrid output** of top personalized product recommendations.

---

## ⚙️ Technical Stack

| Category | Tool / Library | Purpose |
|-----------|----------------|----------|
| **Language** | Python | Main programming language |
| **Data Processing** | Pandas | Data manipulation & preprocessing |
| **Collaborative Filtering** | Scikit-surprise (SVD) | Matrix Factorization for behavioral analysis |
| **Content-Based Filtering** | Scikit-learn (TfidfVectorizer) | Convert text features into numerical vectors |
| **Similarity Metric** | Cosine Similarity (`linear_kernel`) | Measure similarity between products |

---

## 💡 Methodology

The system is engineered in a **three-stage hybrid pipeline** to combine inputs from both models.

### 🔹 1. Data Processing & Feature Engineering
- **Feature Combination:** Concatenated product metadata (*Name, Brand, Category, Color, Size*) into a single text string for the Content-Based model.  
- **Data Validation:** Verified dataset integrity and handled missing values.

### 🔹 2. Model Implementation
- **Content-Based Model:**  
  - Used `TfidfVectorizer` to transform product descriptions into TF-IDF vectors.  
  - Computed **Cosine Similarity** to identify similar items.

- **Collaborative Model:**  
  - Applied **SVD algorithm** on the user–item rating matrix.  
  - Predicted missing ratings based on latent user–item interactions.

### 🔹 3. Hybridization & Output
- Combined the top-N results from both CBF and CF.
- Merged into a **unique ranked list** of personalized recommendations for each user.

---

## 📊 Quick Start Example

```python
# Example usage of hybrid recommender
user_id = 79
product_id = 5
top_n = 10

recommendations = get_hybrid_recommendations(user_id, product_id, top_n)

print(f"Hybrid Recommendations for User {user_id} based on Product {product_id}:")
# Output: Top 10 unique product IDs
