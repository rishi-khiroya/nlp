# Coursework Plan: "Don't Patronize Me!" Binary Classification Task

This plan outlines the steps to analyze data, implement baselines, fine-tune models, and write your final report. We will evaluate three models: RoBERTa-large, DistilBERT-lite, and a simple Bag-of-Words (BoW) model, then select and fine-tune RoBERTa-large as our best performing model.

---

## Phase 1: Task Understanding, Data Analysis & Planning (≈9 Hours)

### 1.1 Read & Understand the Task
- **Review the Task Paper & Related Literature:**
  - Understand the binary classification objective: predicting patronizing/condescending language.
  - Note the evaluation metric: F1 score for the positive class.
  - Identify key components of the marking scheme.

### 1.2 Data Exploration & Analysis
- **Dataset Inspection:**
  - Load the full text file (`dontpatronizeme_pcl.tsv`) and the allocation files (train and dev splits).
  - Confirm the columns (e.g., `par_id`, `text`, and the 7-label array in the allocation files).

- **Label Analysis:**
  - Convert the 7-label array into a binary label (1 if any element is 1, else 0).
  - Calculate and visualize class frequencies (e.g., using histograms).
  - Explore correlations (e.g., input length vs. label).

- **Qualitative Assessment:**
  - Identify and document examples of texts with strong patronizing signals versus non-patronizing examples.
  - Note challenges such as subjectivity and ambiguity in the texts.

### 1.3 Planning & Research Questions
- Define research questions for your report, for example:
  - How does input sequence length impact performance?
  - To what extent is the model better at predicting examples with a higher level of patronizing content?
  - Does performance vary by data category (e.g., “hopeless” vs. “migrant”)?

*Deliverables:*
- Data analysis summary with graphs and tables.
- A written plan outlining challenges and research questions.

---

## Phase 2: Baseline Model Implementation & Preliminary Experiments (≈9 Hours)

### 2.1 Implement Baseline Models
- **Bag-of-Words (BoW) Model:**
  - Develop a BoW classifier (e.g., using TF-IDF and logistic regression).
  - Evaluate its performance on an internal test set and record the F1 score for the positive class.
  - Analyze misclassifications and feature importance.

### 2.2 Transformer-Based Models
- **RoBERTa-large & DistilBERT-lite:**
  - Fine-tune both models on your merged training data.
  - Use your internal train/dev split for hyperparameter tuning.
  - Record internal evaluation metrics (accuracy and F1) for each model.
  - Experiment with different hyperparameters (learning rate, number of epochs, early stopping, etc.).

### 2.3 Model Comparison & Decision Making
- **Evaluate & Compare:**
  - Compare the transformer models with the BoW baseline.
  - Create a summary table with performance metrics on your internal test set.
- **Plan Further Improvements:**
  - Consider additional enhancements (e.g., data augmentation, different sampling strategies, incorporating additional metadata).

*Deliverables:*
- Code and results (training curves, confusion matrices, performance metrics) for BoW, RoBERTa-large, and DistilBERT-lite.
- A comparative analysis table summarizing internal evaluation metrics.

---

## Phase 3: Fine-Tuning the Best Model & Final Evaluations (≈9 Hours)

### 3.1 Fine-Tuning the Best Model
- **Select the Best Model:**
  - Based on Phase 2, choose RoBERTa-large if it outperforms the other models.
- **Fine-Tuning Process:**
  - Optimize hyperparameters using your internal train/dev split.
  - Monitor training and validation losses to check for overfitting.
  - Implement early stopping if needed.

### 3.2 Final Evaluations
- **Pre Fine-Tuning Evaluation:**
  - Evaluate the pre-trained model on your internal test set to establish a baseline.
- **Post Fine-Tuning Evaluation:**
  - Evaluate your fine-tuned model on:
    - Your internal test set (for hyperparameter tuning assessment).
    - The official dev set (merged with full text data) as your final evaluation.
  - Generate confusion matrices and compute accuracy/F1 scores.

### 3.3 Analysis of Results
- **Answer Analysis Questions:**
  - How does the model perform with texts containing higher levels of patronizing content?
  - What is the impact of input sequence length on performance?
  - Does performance vary by data category (e.g., “hopeless” vs. “migrant”)?
- **Compare Against Baselines:**
  - Discuss why the transformer model outperforms the BoW baseline.
  - Provide qualitative examples and misclassification analyses.

*Deliverables:*
- Final model checkpoints and evaluation metrics.
- Predictions for the official dev and test sets in the required format (dev.txt and test.txt).
- Comparative analysis of pre and post fine-tuning performance.

---

## Report Writing & Submission

### Report Structure (Maximum 5 Pages)
- **Introduction:**
  - Explain the task, dataset, and your overall approach.
  - Include a link to your GitHub/GitLab repository.
- **Data Analysis:**
  - Present quantitative and qualitative analyses with graphs and tables.
- **Modeling & Experiments:**
  - Describe your baseline models (BoW, RoBERTa-large, DistilBERT-lite).
  - Summarize hyperparameter tuning, training details, and final model selection.
  - Report improvements from additional experiments.
- **Analysis Questions:**
  - Provide answers to the analysis questions with supporting evidence.
- **Conclusion:**
  - Summarize your key findings and propose at least one further experiment.

### Code Submission
- Upload your code to your GitHub/GitLab repository.
- Ensure your repository contains:
  - Code for generating dev.txt and test.txt predictions.
  - The final dataset preprocessing and model training scripts.

### Final Checklist
- Submit the PDF of your report via Scientia (with your repository link on the first page).
- Ensure your repository contains:
  - dev.txt and test.txt files (one prediction per line).
  - Code corresponding to your predictions and experiments.

---

## Timeline Summary

- **Phase 1 (≈9 Hours):**
  - Data analysis, literature review, and planning experiments.
- **Phase 2 (≈9 Hours):**
  - Implement and evaluate baseline models (BoW, RoBERTa-large, DistilBERT-lite).
- **Phase 3 (≈9 Hours):**
  - Fine-tune the best model (RoBERTa-large), perform final evaluations, and answer analysis questions.
- **Report & Submission:**
  - Write and finalize your report, compile your code and prediction files, and upload everything to your repository.
