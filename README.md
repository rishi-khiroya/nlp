# NLP Coursework: 

## Problem Overview
- **Goal:** Develop a classification model to predict whether a text contains patronizing and condescending language (PCL).
- **Baseline Model:** RoBERTa-base provided by the task organizers.
- **Performance Target:** Outperform the RoBERTa-base baseline:
  - **F1 Score on Dev Set:** `0.48`
  - **F1 Score on Test Set:** `0.49`
- **Evaluation Metric:** F1 score of the **positive class** (PCL examples).

## Repo Structure
- **roberta-large:**
  - visualises the data to examine for data imbalance
  - baseline finetune and evaluation of roberta-large
  - weightloss functions and weighted sampling
  - data augmentation and synonym replacement
  - hyperparameter search
  - evaluation of final model
  - generation of predictions on official dev set
- **distilbert-uncased:** contains the finetuning and evaluation for the baseline distilbert-uncased
- **bow:** contains the baseline bag of words model and evaluation
- **/models:** saved models directory
- **/data:** data set related files directory
- **/experiments:** graphs generated from experiments in roberta-large directory
