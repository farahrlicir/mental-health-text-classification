# Feature Engineering

## Objective

Convert the cleaned text into representations that can be consumed by the NLP model.

The primary predictive feature is the Reddit post text.

## Feature Strategy

This project uses text as the main input rather than relying on manually engineered numerical features.

The original thesis investigates deep learning architectures including:

* BiLSTM
* DistilBERT
* RoBERTa

For transformer-based models, the text is transformed into model-specific token representations using the corresponding tokenizer.

## Text Representation

The feature pipeline should:

1. Receive preprocessed text.
2. Tokenize the text using the tokenizer associated with the selected model.
3. Convert tokens into numerical representations.
4. Apply the required attention masks and sequence-length handling.
5. Produce model-ready inputs.

## Sequence Length

The original thesis describes chunking text to a maximum of 500 tokens.

The production implementation must explicitly define how texts exceeding the model's supported sequence length are handled.

Possible strategies should be evaluated rather than silently applied.

## Target

The target variable is the mental-health category:

* ADHD
* Anxiety
* Bipolar
* Depression
* PTSD
* None

The target should be encoded consistently for model training and decoded back to the original class name for predictions.

## Feature Engineering Principles

Feature engineering should:

* be deterministic
* be reproducible
* avoid using information from the target
* avoid data leakage
* be identical during training and inference
* preserve useful information from the original text

## Output

The feature engineering stage should produce:

* tokenized model inputs
* attention masks where required
* encoded target labels

These outputs will be passed to the train/validation/test strategy.
