# Narration Analysis

A comprehensive data analysis project for analyzing transaction narrations and categorizing them using keyword-based and machine learning approaches.

## 📋 Project Overview

This project analyzes financial transaction narrations (descriptions) to:
- Extract and identify keywords associated with different transaction categories
- Calculate keyword frequency across categories
- Build predictive models for automatic transaction categorization
- Evaluate model performance using various scoring mechanisms

## 📁 Repository Structure

### Core Analysis Notebooks

| Notebook | Purpose |
|----------|---------|
| **narration_keywords.ipynb** | Defines comprehensive keyword lists for different transaction categories (e.g., Business Receipts, Dividends, Loans, etc.) |
| **hybrid.ipynb** | Implements a hybrid matching approach using Aho-Corasick algorithm for efficient keyword matching in transaction narrations |
| **predict_category.ipynb** | Builds predictive models to automatically categorize transactions based on narration scoring |
| **kw_check_in_narration_tokens.ipynb** | Analyzes keyword presence in tokenized narrations |
| **kw_check_in_narr_str.ipynb** | Checks keyword presence in normalized narration strings |

### Data Analysis & Visualization Notebooks

| Notebook | Purpose |
|----------|---------|
| **keyword_freq_category_wise.ipynb** | Analyzes and visualizes keyword frequency distribution across different transaction categories |
| **keyword_freq_txn_wise.ipynb** | Analyzes keyword frequency at individual transaction level |
| **freq_threshold_graph.ipynb** | Generates visualizations for keyword frequency thresholds |
| **score_threshold_graph.ipynb** | Generates visualizations for transaction score thresholds |
| **Levenshtein_1_distance.ipynb** | Analyzes string similarity using Levenshtein distance for fuzzy matching |

## 🔧 Key Features

### Text Normalization
All notebooks utilize a standard text normalization function that:
- Converts text to lowercase
- Removes special characters (keeps only alphanumeric and spaces)
- Removes extra whitespace

### Keyword-Based Classification
- Defines domain-specific keywords for each transaction category
- Supports multiple matching strategies:
  - Token-based matching (splitting by spaces)
  - String-based matching (substring search in normalized text)
  - Aho-Corasick efficient multi-pattern matching

### Scoring Mechanisms
- **Narration Score**: Aggregates frequency-based scores for keywords found in transactions
- **Threshold Analysis**: Determines optimal thresholds for category prediction

### Hybrid Approach
The `hybrid.ipynb` notebook combines multiple matching techniques for robust category prediction using the efficient Aho-Corasick algorithm.

## 📊 Data Requirements

The notebooks expect input files in Excel format (.xlsx) with columns including:
- `Narration`: Transaction description/narrative
- `Category`: Transaction category (if available for training)
- `Date`: Transaction date (optional, for temporal analysis)

## 🚀 Getting Started

1. **Install Dependencies**
   ```bash
   pip install pandas numpy openpyxl pyahocorasick
   ```

2. **Prepare Data**
   - Place your transaction data Excel files in the same directory as the notebooks
   - Ensure files have `Narration` and `Category` columns

3. **Run Analysis**
   - Start with `narration_keywords.ipynb` to review keyword definitions
   - Use `hybrid.ipynb` for efficient keyword matching
   - Use `predict_category.ipynb` for category prediction
   - Explore visualization notebooks for insights

## 📈 Workflow

```
Raw Data
   ↓
Text Normalization
   ↓
Keyword Extraction & Analysis
   ├→ Frequency Analysis (keyword_freq_*.ipynb)
   ├→ Token Analysis (kw_check_in_narration_tokens.ipynb)
   └→ String Analysis (kw_check_in_narr_str.ipynb)
   ↓
Hybrid Matching (hybrid.ipynb)
   ↓
Category Prediction (predict_category.ipynb)
   ↓
Performance Analysis & Visualization
   ├→ Threshold Graphs (freq_threshold_graph.ipynb, score_threshold_graph.ipynb)
   └→ Similarity Analysis (Levenshtein_1_distance.ipynb)
```

## 🔑 Key Concepts

### Text Normalization
Standardizes narration text by:
- Lowercasing all characters
- Removing non-alphanumeric characters
- Collapsing whitespace

### Keyword Matching
- **Token-based**: Splits text by spaces and matches whole tokens
- **String-based**: Searches for keyword substrings in normalized text
- **Aho-Corasick**: Efficient multi-pattern matching algorithm for large keyword lists

### Scoring
Transaction scores are calculated by:
1. Finding all matching keywords in the narration
2. Summing up the frequency-based scores for each keyword
3. Using score thresholds to make category predictions

## 🛠️ Technologies Used

- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Regular Expressions (re)**: Text pattern matching and normalization
- **pyahocorasick**: Efficient multi-pattern string matching
- **Matplotlib**: Data visualization (implied by analysis notebooks)

## 📝 Notes

- All keyword lists are defined in `narration_keywords.ipynb` for easy maintenance
- Text normalization is consistent across all notebooks
- The Aho-Corasick algorithm in `hybrid.ipynb` provides optimal performance for large datasets
- Threshold values should be calibrated based on your specific dataset

