# LLM Prompt Injection Detection Benchmark

This project is a comparative AI security benchmark for detecting malicious prompts targeting Large Language Model applications.

## Objective

The goal is to detect LLM prompt-injection attempts using machine learning and NLP-based feature extraction methods.

The project compares:

- Bag of Words
- Word-level TF-IDF
- Character-level TF-IDF
- Word + Character TF-IDF
- Word2Vec
- FastText
- GloVe
- Linguistic and security-based features
- Multiple ML classifiers with hyperparameter tuning

## Dataset

Dataset: `deepset/prompt-injections` from Hugging Face.

The official train split is used for training and hyperparameter tuning.  
The official test split is used only for final evaluation.

## Best Results

The best official test F1-score was achieved by:

| Feature Method | Model | Accuracy | Precision | Recall | F1-score |
|---|---|---:|---:|---:|---:|
| TFIDF_Char | Extra_Trees | 0.9224 | 1.0000 | 0.8500 | 0.9189 |

The strongest cross-validation model was also analyzed separately to avoid selecting only by test performance.

## Methodology

1. Load official Hugging Face train/test split
2. Apply security-preserved preprocessing
3. Extract multiple feature representations
4. Tune ML models using cross-validation on the training split
5. Evaluate final models on the official test split
6. Analyze false positives and false negatives

## Why This Is AI Security

Although the implementation uses NLP and ML, the target problem is AI security. The system detects malicious prompts before they reach an LLM application.

Detected risks include:

- Instruction override
- Prompt injection
- Role manipulation
- Jailbreak-style behavior
- Sensitive data extraction attempts
- Prompt leakage attempts

## Author

Sourav Datto
