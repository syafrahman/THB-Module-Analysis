# Project Documentation

## Overview
This project involves advanced text processing and analysis using Python and Jupyter Notebooks. The primary data source for this project is stored in a pickled DataFrame file, and various notebooks are used for different aspects of text analysis, including Latent Dirichlet Allocation (LDA) and Word Vectors (WV) processing.

## Data Source
- **df_00.pkl**: This is the main data file for the project. It is a pickled DataFrame containing essential information in the following columns: `Title`, `Subject`, `Author`, `Creation Date`, `ExtractedText`. This file serves as the input for various processing notebooks.

## LDA Directory
- **Notebook Name**: `LDA-with-pre-processing.ipynb`
  - **Purpose**: This Jupyter Notebook handles all the pre-processing required for Latent Dirichlet Allocation (LDA) and models topics using LDA techniques.
  - **Input**: Takes `df_00.pkl` as the input.
  - **Description**: In this notebook, the data from `df_00.pkl` undergoes various pre-processing steps to prepare it for topic modeling using LDA.
- **Pre-trained LDA Model**: `lda_model`
  - **Purpose**: This is a pre-trained LDA model on the given dataset, trained to identify 10 distinct topics.
  - **Usage**: You can directly load this model to print or analyze the 10 topics identified in the training phase without having to retrain the model from scratch.

## WV (Word Vectors) Directory
- **Pre-Processing Notebook**: `pre-processing-for-WV.ipynb`
  - **Purpose**: This notebook is dedicated to pre-processing steps specifically tailored for Word Vectors processing.
  - **Input**: The initial input for this notebook is `df_00.pkl`.
  - **Output**: The pre-processing in this notebook outputs a file named `df_04.pkl`.
- **FastText Model Training Notebook**: `WV.ipynb`
  - **Purpose**: This notebook uses the pre-processed data (`df_04.pkl`) to train a FastText model.
  - **Input**: The input for this notebook is the `df_04.pkl` file, which is the output from the `pre-processing-for-WV.ipynb` notebook.

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

