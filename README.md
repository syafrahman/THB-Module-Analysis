# Project Documentation

## Overview
This project involves advanced text processing and analysis using Python and Jupyter Notebooks. The primary goal is to analyze module handbooks from THB using **Latent Dirichlet Allocation (LDA)** and **Word Vectors (WV)** techniques. The project focuses on identifying distinct academic themes and analyzing semantic content. The main data source for this project is stored in a pickled DataFrame file, and various notebooks are used for different aspects of the analysis.

## Data Source
- **df_00.pkl**: This is the main data file for the project. It is a pickled DataFrame containing essential information in the following columns: `Title`, `Subject`, `Author`, `Creation Date`, `ExtractedText`. This file serves as the input for various processing notebooks.

## Motivation
This study investigates the effectiveness of **Latent Dirichlet Allocation (LDA)** and **word embeddings** in analyzing THB module handbooks. It explores:
- The ability of LDA to categorize major academic themes.
- The capability of word embeddings to represent the semantic content of module titles and descriptions.
  
The ultimate goal is to enhance understanding and categorization of academic content at THB using Python-based tools for data processing and analysis.

## LDA Directory
- **Notebook Name**: `LDA-with-pre-processing.ipynb`
  - **Purpose**: This Jupyter Notebook handles all the pre-processing required for Latent Dirichlet Allocation (LDA) and models topics using LDA techniques.
  - **Input**: Takes `df_00.pkl` as the input.
  - **Description**: In this notebook, the data from `df_00.pkl` undergoes various pre-processing steps to prepare it for topic modeling using LDA.
- **Pre-trained LDA Model**: `lda_model`
  - **Purpose**: This is a pre-trained LDA model on the given dataset, trained to identify 10 distinct topics.
  - **Usage**: You can directly load this model to print or analyze the 10 topics identified in the training phase without having to retrain the model from scratch.

### Findings from LDA Analysis:
- **Topic Identification**: The LDA model identified **10 distinct academic themes** from THB’s module handbooks.
- **Departmental Alignment**: Key themes aligned with specific departmental focuses, such as "Computer Science Education" in the Informatics Department and "Economics and Information Systems" in the Business Department.
- **Challenges**: There were difficulties in distinguishing some interdisciplinary themes like "Interdisciplinary Engineering with a Focus on IT Security," indicating potential areas for refinement in the LDA model.

### Figures for LDA Analysis:
1. **Text Data Processing Workflow**:
   ![Text Data Processing Workflow](Text%20Data%20Processing%20Workflow.png)
   _Figure 1: Overview of data collection, preprocessing, and modeling steps._

2. **Summary of LDA Topics**:
   ![Summary of LDA Topics](Summary%20of%20LDA%20Topics.png)
   _Figure 2: A summary of the 10 identified topics using LDA._

3. **LDA Topic Frequencies by Department**:
   ![LDA Topic Frequencies by Department](/Semantic%20Similarity%20Results.png)
   _Figure 3: Heatmap showing LDA topic frequencies across various departments._

## WV (Word Vectors) Directory
- **Pre-Processing Notebook**: `pre-processing-for-WV.ipynb`
  - **Purpose**: This notebook is dedicated to pre-processing steps specifically tailored for Word Vectors processing.
  - **Input**: The initial input for this notebook is `df_00.pkl`.
  - **Output**: The pre-processing in this notebook outputs a file named `df_04.pkl`.
- **FastText Model Training Notebook**: `WV.ipynb`
  - **Purpose**: This notebook uses the pre-processed data (`df_04.pkl`) to train a FastText model.
  - **Input**: The input for this notebook is the `df_04.pkl` file, which is the output from the `pre-processing-for-WV.ipynb` notebook.

### Findings from Word Vectors Analysis:
- **Semantic Relationships**: The FastText model was effective in capturing basic semantic relationships between module titles and descriptions.
- **Limitations**: While successful in identifying related words, the model faced challenges in understanding **domain-specific nuances** and broader conceptual connections, highlighting the need for further enhancements in training to capture more complex relationships.

### Figures for Word Vectors Analysis:
4. **FastText Model Results**:
   ![FastText Semantic Similarity](LDA%20Topic%20Frequencies%20Heatmap.png)
   _Figure 4: Semantic similarity results from the FastText model._

## Conclusion
The project demonstrates the effectiveness of LDA and word embeddings in analyzing academic content from THB's module handbooks. While the methods successfully identified key academic themes and captured basic semantic content, there are areas for improvement, particularly in differentiating interdisciplinary topics and capturing more nuanced semantic relationships. Future work should focus on refining the models for greater specificity and accuracy in academic discourse analysis.

## How to Use
1. Start by exploring the `df_00.pkl` file to understand the structure and content of the data.
2. For topic modeling using LDA:
   - Open `LDA-with-pre-processing.ipynb` in the LDA directory.
   - Ensure `df_00.pkl` is available as input.
   - Optionally, load the `lda_model` to view the 10 topics without retraining.
3. For Word Vectors processing:
   - Start with `pre-processing-for-WV.ipynb` in the WV directory.
   - Use `df_00.pkl` as the input to generate `df_04.pkl`.
   - Proceed to `WV.ipynb` for training the FastText model using `df_04.pkl`.
   - Optionally, directly use existing `df_04.pkl` for training the FastText model.

## Requirements
- Python 3.x
- Jupyter Notebook
- Libraries: Pandas, spaCy, FastText, etc. (Refer to individual notebooks for specific dependencies).

## References
1. David M. Blei, Andrew Y. Ng, and Michael I. Jordan. “Latent Dirichlet Allocation”. Journal of Machine Learning Research 3, Jan (2003), pp. 993–1022.
2. Piotr Bojanowski et al. “Enriching Word Vectors with Subword Information”. Transactions of the Association for Computational Linguistics 5 (2017), pp. 135–146.
