# Data Preprocessing

## Objective

Transform raw Reddit posts into clean and consistent text suitable for NLP model training while preserving information that may be useful for classification.

The raw dataset must remain unchanged.

## Preprocessing Pipeline

The original thesis describes the following preprocessing operations:

1. Language detection
2. Keep English-language posts
3. Filter words that are excessively long
4. Filter excessive repeated characters
5. Filter words without vowels
6. Convert text to lowercase
7. Remove mentions
8. Remove hashtags
9. Remove digits
10. Remove special characters
11. Remove extra spaces
12. Tokenization
13. Stopword removal
14. Chunk text to a maximum of 500 tokens

## Important Engineering Rule

Preprocessing must be implemented as a reproducible pipeline rather than performed manually.

The same preprocessing logic must be usable during:

* training
* validation
* testing
* inference through the API

## Raw Data Protection

The raw dataset must never be modified directly.

Data transformations should produce intermediate or processed data under:

```text
data/
├── raw/
├── interim/
└── processed/
```

## Preprocessing Decisions To Revisit

The thesis preprocessing pipeline was designed for the original experiments.

For the production-oriented version of this project, each transformation should be evaluated before implementation.

In particular, we need to determine whether removing:

* digits
* special characters
* hashtags
* mentions
* stopwords

could remove information useful for classification.

The preprocessing strategy should also account for very long Reddit posts identified during data validation.

## Output

The preprocessing stage should produce text that is:

* consistent
* reproducible
* suitable for tokenization
* compatible with the selected model
* available through the same transformation logic during inference
