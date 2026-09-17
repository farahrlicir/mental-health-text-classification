# Data Validation

## Objective

Verify that the extracted raw dataset is structurally valid, complete, consistent, and safe to use for model development.

## Validation Checks

### 1. Schema Validation

Verify:

* expected columns exist
* column names are correct
* data types are appropriate
* no unexpected columns are present

Expected fields:

* `post`
* `mental_health_disorder`

### 2. Missing Values

Check for:

* missing text
* missing labels
* empty strings
* whitespace-only text

Missing values must be identified before preprocessing.

### 3. Label Validation

Verify that every target value belongs to the expected set:

* ADHD
* Anxiety
* Bipolar
* Depression
* PTSD
* None

Unexpected labels must be investigated.

### 4. Duplicate Validation

Check for:

* exact duplicate posts
* duplicate rows
* duplicates between train, validation, and test sets

Duplicates across splits could cause data leakage.

### 5. Text Validation

Inspect:

* empty or extremely short posts
* unusually long posts
* repeated characters
* abnormal text
* non-English text
* potentially corrupted records

These checks should identify problematic samples without modifying the raw dataset.

### 6. Split Validation

Verify:

* train, validation, and test sets exist as expected
* samples are assigned to the correct split
* target distributions are consistent with the dataset documentation
* there is no overlap between splits

### 7. Privacy Validation

Verify that unnecessary personal information is not present in the data.

The original thesis states that usernames and URLs were removed.

## Validation Outcome

Each validation check should produce a measurable result.

Examples:

* number of missing posts
* number of missing labels
* number of duplicate rows
* number of duplicate posts
* number of unexpected labels
* number of empty posts
* number of suspicious text samples
* number of overlapping samples between splits

The raw dataset must remain unchanged during validation.

## Open Questions

The following values are measured from the dataset :

* exact number of rows
* exact column names
* missing-value counts
* duplicate counts
* empty-text counts
* text-length statistics
* unique labels
* cross-split overlap
* unexpected records
