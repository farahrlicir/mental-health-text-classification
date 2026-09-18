## Validation Results

The initial validation was performed on the available raw train and validation CSV files.

### Dataset Structure

| Check           |  Train | Validation |
| --------------- | -----: | ---------: |
| Rows            | 13,727 |      1,716 |
| Columns         |      4 |          4 |
| Missing values  |      0 |          0 |
| Empty posts     |      0 |          0 |
| Duplicate rows  |      0 |          0 |
| Duplicate posts |      6 |          0 |
| Unique IDs      | 13,727 |      1,716 |

### Schema

Both datasets contain:

* `ID`
* `post`
* `class_name`
* `class_id`

The `post` column contains text and the target is represented by `class_name` and `class_id`.

### Label Validation

The six observed classes are:

* ADHD
* Anxiety
* Bipolar
* Depression
* PTSD
* None

The mapping between `class_id` and `class_name` is consistent across train and validation:

* `0` → ADHD
* `1` → Anxiety
* `2` → Bipolar
* `3` → Depression
* `4` → PTSD
* `5` → None

### Text Validation

No empty or extremely short posts were found.

Train text length:

* Minimum: 123 characters
* Maximum: 38,168 characters
* Mean: approximately 1,065 characters
* Median: 658 characters

Validation text length:

* Minimum: 144 characters
* Maximum: 14,273 characters
* Mean: approximately 1,056 characters
* Median: 658 characters

Some posts contain non-ASCII characters. This is not considered an error by itself and requires further investigation before preprocessing.

### Duplicate and Leakage Check

Six duplicate posts were found within the training dataset.

No duplicate posts were found within the validation dataset.

One exact post occurs in both the training and validation datasets.

This represents a potential data leakage issue and must be investigated before model training.

No overlapping IDs were found between the training and validation datasets.

### Validation Issues Identified

The following issues require investigation:

1. The validation file contains 1,716 rows, while the thesis reports 1,488 validation samples.
2. Six duplicate posts exist in the training data.
3. One post appears in both training and validation.
4. Text lengths vary considerably and include some very long posts.
5. The meaning and appropriateness of non-ASCII characters require investigation before preprocessing.

These issues should be resolved or documented before proceeding to preprocessing and model training.
