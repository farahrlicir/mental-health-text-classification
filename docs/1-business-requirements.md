# Business Requirements

## Problem

Build an NLP classification system that classifies mental-health-related
Reddit text into one of the categories represented in the dataset.

## Objective

The system should predict the category associated with an input text.

## Input

User-provided text.

The original research used Reddit mental-health data and investigated
multiple deep learning architectures.

## Output

The system returns:

- predicted class
- prediction probabilities

## ML Task

Multi-class text classification.

## Classes

- ADHD
- Anxiety
- Bipolar
- Depression
- PTSD
- None

## Intended Use

The system is an NLP classification/research system.

It must not be presented as a clinical diagnostic system.

## Success Criteria

The model should be evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Per-class performance

We will additionally investigate model errors and operational
requirements before selecting a production model.

## Risks

Potential risks include:

- noisy user-generated text
- ambiguous labels
- class imbalance
- duplicate or highly similar samples
- data leakage
- distribution shift
- incorrect interpretation of predictions

## Engineering Requirements

The final system should be:

- reproducible
- testable
- version controlled
- documented
- deployable
- accessible through an API
- maintainable