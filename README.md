# Product Recommender System

## Overview
This project focuses on analyzing and processing a dataset of product details to build a recommender system.

---

### 1. **Data Exploration**
- Analyzed the dataset structure and diversity:
  - Columns include product-specific attributes (e.g., name, category, brand, and rating).
  - High uniqueness in key columns, highlighting dataset richness.
- Identified **no null values** in the dataset.

---

### 2. **Data Processing**
#### Null Values
- Comprehensive examination of missing data across columns.
- Missing values handled strategically:
  - Removed rows with null values in critical fields like `product` and `description`.
  - Imputed missing ratings with the median to ensure data robustness.

#### Encoding Categorical Columns
- Converted categorical data into numerical formats:
  - **One-Hot Encoding** for `category`.
  - **Label Encoding** for `sub_category` and `type`.
  - **Frequency Encoding** for `brand`.
- Prepared data for statistical analysis and machine learning models.

#### Text Preprocessing (`Description` Column)
- Analyzed description lengths.
- Tokenized descriptions into sequences using Keras:
  - Captured **32,831 unique tokens**.
  - Applied padding to ensure uniform sequence lengths for compatibility with neural networks.

---

### 3. **Recommender System**
- Built a recommender system using **Jaccard Similarity** to find products similar to a user's selection:
  - Products are vectorized based on specific attributes.
  - A similarity threshold of **0.325** determines related products.
  - The user inputs a product, and the system suggests similar options iteratively.
- Outputs a dictionary of unique products for recommendations.

---
