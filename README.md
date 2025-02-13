# NLP Coursework: Patronizing and Condescending Language (PCL) Detection

## Task Overview
- **Goal:** Develop a binary classification model to predict whether a text contains patronizing and condescending language (PCL).
- **Competition:** SemEval 2022, Task 4 (Subtask 1).
- **Baseline Model:** RoBERTa-base provided by the task organizers.
- **Performance Target:** Outperform the RoBERTa-base baseline:
  - **F1 Score on Dev Set:** `0.48`
  - **F1 Score on Test Set:** `0.49`
- **Evaluation Metric:** F1 score of the **positive class** (PCL examples).

## Recommended Hugging Face Models for Fine-Tuning
| Model | Description |
|--------|------------|
| [`cardiffnlp/pcl_robertabase`](https://huggingface.co/cardiffnlp/pcl_robertabase) | RoBERTa-base fine-tuned on PCL detection (strong baseline). |
| [`bert-base-uncased`](https://huggingface.co/bert-base-uncased) | General-purpose BERT model for text classification. |
| [`roberta-large`](https://huggingface.co/roberta-large) | Larger RoBERTa model, may improve performance at higher compute cost. |
| [`distilbert-base-uncased`](https://huggingface.co/distilbert-base-uncased) | Lightweight BERT model with fewer parameters. |
| [`xlm-roberta-base`](https://huggingface.co/xlm-roberta-base) | Multilingual RoBERTa model, useful if dataset has linguistic diversity. |

## Fine-Tuning Plan

### 1. Data Preprocessing
- Load dataset: **`dontpatronizeme_pcl.tsv`**.
- Create internal dev set from training data (for hyperparameter tuning).
- Tokenize text using a transformer tokenizer (`AutoTokenizer` from `transformers`).

### 2. Baseline Model Comparison
- Implement a **Bag-of-Words (BoW) model**:
  - Example: **Logistic Regression** or **SVM**.
  - Helps compare traditional ML approaches with transformers.

### 3. Fine-Tune Transformer Model
- Load a pre-trained Hugging Face model.
- Train with **cross-entropy loss**.
- Implement:
  - **Learning rate scheduling**
  - **Early stopping**
  - **Gradient clipping** (if needed)

### 4. Data Augmentation & Sampling
- Handle class imbalance:
  - **Oversampling** minority class.
  - **Downsampling** majority class.
- Try **data augmentation**:
  - **Back-translation** (translating to another language and back).
  - **Synonym replacement** using NLP libraries like `NLTK` or `WordNet`.

### 5. Model Evaluation & Optimization
- Use the **F1-score of the positive class** as the main metric.
- Perform **hyperparameter tuning**:
  - Learning rate
  - Batch size
  - Number of epochs
  - Use **grid search** or **Optuna** for tuning.

### 6. Submission & Report Writing
- Generate predictions:
  - **`dev.txt`** (public dev set).
  - **`test.txt`** (held-out test set, evaluated by organizers).
- **GitHub/GitLab repository** must contain:
  - Model training code.
  - `dev.txt` and `test.txt` predictions.
- **Final Report**:
  - 5-page max (following the provided template).
  - Include:
    - **Data analysis**
    - **Modeling approach**
    - **Experiment results**
    - **Comparison with baseline models**
    - **Future work suggestions**

---

### Additional Notes
- **Computational considerations**:
  - RoBERTa-large requires s
