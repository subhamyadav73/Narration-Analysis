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

### Hybrid Approach
The `hybrid.ipynb` notebook combines multiple matching techniques for robust category prediction using the efficient Aho-Corasick algorithm.

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

