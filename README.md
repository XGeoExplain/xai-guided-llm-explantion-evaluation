# Enhancing Explainability in Remote Sensing via XAI-Guided LLM Explanations


## Notebook Structure

The experiments and evaluation are organized into separate notebooks:

- `experiments_with_eurosat.ipynb`  
  - Contains the main experimental pipeline for the EuroSAT dataset.
  - Loads and preprocesses the EuroSAT remote sensing images.
  - Selects sample images from the chosen land-use and land-cover classes.
  - Fine-tunes a pre-trained ResNet50 model for image classification.
  - Generates model predictions and confidence scores for selected images.
  - Implements Explainable Artificial Intelligence (XAI) methods, including Grad-CAM, LIME, and SHAP.
  - Converts visual XAI outputs into structured textual descriptions.
  - Uses a Large Language Model (LLM) to generate human-readable explanations.
  - Covers all five experimental settings: Exp1, Exp2, Exp3, Exp4, and Exp5.
  - Saves predictions, XAI descriptions, and LLM-generated explanations into CSV files for later evaluation.
  
- `evaluation_for_eurosat.ipynb`  
  Contains the LLM-as-a-Judge evaluation for comparing the baseline explanation with each XAI-guided explanation. The following pairwise comparisons are performed:
  - Exp1 vs Exp2
  - Exp1 vs Exp3
  - Exp1 vs Exp4
  - Exp1 vs Exp5

The pairwise evaluation results are used to analyze the impact of XAI guidance descriptions on the quality of generated explanations.
