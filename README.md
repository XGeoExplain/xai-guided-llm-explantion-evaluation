# Explainable Remote Sensing Classification using XAI-Guided Large Language Models

## Overview

This project investigates whether Explainable Artificial Intelligence (XAI) methods can improve the quality of Large Language Model (LLM)-generated explanations for remote sensing image classification.

A convolutional neural network (CNN) is used to classify satellite images from the EuroSAT dataset. The model predictions are then explained using three XAI techniques: **Grad-CAM**, **LIME**, and **SHAP**. The visual outputs from these XAI methods are converted into textual descriptions and provided as additional context to an LLM to generate human-readable explanations.

The repository includes:

- CNN-based remote sensing image classification
- XAI generation using Grad-CAM, LIME, and SHAP
- Textual conversion of XAI outputs
- LLM-based explanation generation
- LLM-as-a-Judge evaluation framework
- Quantitative and qualitative analysis

<p align="center">
  <img width="4956" height="2056" alt="Framework-fig" src="https://github.com/user-attachments/assets/0d48de14-43a9-4835-86be-5696dad2c933" />
</p>

---

## Research Objective

Deep learning models achieve strong performance in remote sensing image classification but often behave as black-box systems. Although XAI methods can highlight important image regions, these visual explanations are difficult for non-technical users to interpret.

This work aims to bridge the gap between visual explainability and human-readable reasoning by integrating XAI-guided information into LLM-generated explanations.

The project evaluates whether XAI guidance improves:

- Specificity of explanations
- Usefulness of explanations
- Overall explanation quality

---

## Methodology

The proposed framework consists of the following stages:

1. CNN-based image classification using the EuroSAT dataset
2. XAI generation using:
   - Grad-CAM
   - LIME
   - SHAP
3. Conversion of XAI outputs into textual descriptions
4. LLM-based explanation generation
5. Evaluation using an LLM-as-a-Judge framework

---

## Experiments

The following experimental settings are evaluated:

| Experiment | Description |
|---|---|
| Exp1 | Image + predicted class, baseline setting |
| Exp2 | Image + predicted class + Grad-CAM text |
| Exp3 | Image + predicted class + LIME text |
| Exp4 | Image + predicted class + SHAP text |
| Exp5 | Image + predicted class + combined XAI text |

---


## Evaluation Metrics

The generated explanations are evaluated using **GPT-4.1-mini** as an LLM judge.

The evaluation uses the following metrics:

| Metric | Description |
|---|---|
| Specificity | Score from 0 to 5 measuring whether explanations describe concrete visual characteristics such as shapes, textures, colors, and spatial arrangements |
| Usefulness | Score from 0 to 5 measuring how effectively the explanation helps users understand the CNN prediction |
| Total Score | Sum of specificity and usefulness scores, ranging from 0 to 10 |
| Win Rate | Percentage of samples for which an XAI-guided explanation outperforms the baseline explanation |
| Tie Rate | Percentage of samples where the XAI-guided explanation and baseline explanation receive equal scores |
| Percentage Improvement | Relative improvement of the XAI-guided explanation over the baseline |

---

## Key Findings

- Grad-CAM provides only marginal improvement over the baseline.
- LIME improves explanation quality and outperforms the baseline.
- SHAP does not improve explanation quality in this setting.
- Combined XAI achieves the best performance across all experiments.

---

## Qualitative Results

Sample generated explanations for six land-cover classes are included in the `qualitative_results/` folder.

The folder contains sample figures with:

- Original remote sensing images
- XAI visualizations
- XAI textual descriptions
- Generated explanations

---

## Dataset

This project uses the **EuroSAT** dataset for remote sensing image classification.

Dataset repository:

- [EuroSAT](https://github.com/phelber/EuroSAT)

---

## Models and Tools

### CNN Model

- ResNet50

### XAI Methods

- Grad-CAM
- LIME
- SHAP

### LLM Models

- GPT-4o for explanation generation
- GPT-4.1-mini for evaluation and judge scoring

---

## Prompts

All prompts used for LLM explanation generation and LLM-as-a-Judge evaluation are provided in the `prompts/` folder for reproducibility.

The folder includes:
- Baseline explanation prompt
- Grad-CAM-guided explanation prompt
- LIME-guided explanation prompt
- SHAP-guided explanation prompt
- Combined XAI explanation prompt
- Pairwise judge prompts

---

## Usage

Run the notebooks in the following order:

- 01_generate_xai_guided_llm_explanations.ipynb
- 02_llm_judge_evaluation.ipynb


## Notes
- API keys are not included in this repository.
- Large datasets and model checkpoints are excluded.
- Generated results and evaluation outputs are included for reproducibility.
