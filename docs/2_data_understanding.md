# Data Understanding

## 1. Data Source

The dataset used in this project is the **Mental Health Reddit Dataset**, created by Murarka et al.

The data was collected from **Reddit** using the Reddit API. The dataset contains Reddit posts associated with mental-health-related categories.



## 2. Dataset Size


* Training: **13727 samples**
* Validation/Development: **1488 samples**
* Test: **1488 samples**

The three splits therefore contain:

**13727 + 1488 + 1488 = 16703 samples**

## 3. Features


| Column                   | Description                                                                |
| ------------------------ | -------------------------------------------------------------------------- |
| `post`                   | The Reddit post/text provided as input to the NLP model.                   |
| `mental_health_disorder` | The category associated with the Reddit post and used as the target label. |


## 4. Target

The target represents the **mental-health category associated with the Reddit post**.

The task is a **multi-class text classification problem**.

The six target classes are:

* `ADHD`
* `Anxiety`
* `Bipolar`
* `Depression`
* `PTSD`
* `None`

The dataset contains all six classes.


---

## 5. Target Distribution

### Training set

The training distribution :

| Class      |      Count | Percentage |
| ---------- | ---------: | ---------: |
| ADHD       |      2,465 |     17.96% |
| Anxiety    |      2,422 |     17.64% |
| Bipolar    |      2,407 |     17.53% |
| Depression |      2,450 |     17.85% |
| PTSD       |      2,001 |     14.58% |
| None       |      1,982 |     14.44% |
| **Total**  | **13,727** |   **100%** |


### Validation / Development set

| Class      |     Count | Percentage |
| ---------- | --------: | ---------: |
| ADHD       |       248 |     16.67% |
| Anxiety    |       248 |     16.67% |
| Bipolar    |       248 |     16.67% |
| Depression |       248 |     16.67% |
| PTSD       |       248 |     16.67% |
| None       |       248 |     16.67% |
| **Total**  | **1,488** |   **100%** |

### Test set

| Class      |     Count | Percentage |
| ---------- | --------: | ---------: |
| ADHD       |       248 |     16.67% |
| Anxiety    |       248 |     16.67% |
| Bipolar    |       248 |     16.67% |
| Depression |       248 |     16.67% |
| PTSD       |       248 |     16.67% |
| None       |       248 |     16.67% |
| **Total**  | **1,488** |   **100%** |

The validation and test sets are exactly balanced.

The training set is not perfectly balanced, but the class proportions are relatively close, ranging from approximately **14.44% to 17.96%**.


## 6. Text Characteristics

The thesis does **not provide the following raw-data statistics**:

* minimum text length
* maximum text length
* average text length
* number of empty/null texts
* number of duplicated texts
* number of very short texts

The thesis states that missing and duplicated entries were checked during preprocessing, but it does not provide the resulting counts.

Therefore, these statistics must be calculated directly from the **original dataset files** before preprocessing.

They should not be estimated from the thesis.

The thesis does indicate that some posts could be excessively long, which motivated splitting tokenized posts into chunks of up to 500 tokens.



### 7.2 Missing values



### 7.3 Duplicate posts



### 7.4 Noisy user-generated text

Reddit text is user-generated and can contain:

* informal language
* contractions
* mentions
* hashtags
* URLs
* special characters
* unusually long words
* repeated characters
* other noisy text

### 7.5 Extreme text lengths

we  identifie excessively long posts as a potential issue.

### 7.6 Possible data leakage


### 7.7 Label quality

The dataset uses six categorical labels. The thesis does not provide a detailed annotation-quality analysis or explain how ambiguous cases were handled.


## 8. Initial Questions

Before preprocessing wee following questions need to be answered:

1. **What is the exact number of rows in each raw dataset file?**

2. **Why does the thesis presentation report 16,931 samples while the split table totals 16,703?**

3. **What are the exact column names in the original dataset files?**

4. **Are there any missing or null text values?**

5. **Are there duplicated posts?**

6. **Are there exact or near-duplicate posts across train, validation, and test sets?**

7. **Are all labels valid and consistent with the six expected classes?**

8. **Are there extremely short or empty posts?**

9. **What are the minimum, maximum, median, and average text lengths?**

10. **How many posts exceed the 500-token limit used in the thesis?**

11. **Does the raw dataset contain usernames, URLs, metadata, or other fields that should not be used as model features?**

12. **Is there any information in the text or metadata that could reveal the target label and create leakage?**

13. **Were the train, validation, and test sets created before or after any preprocessing or filtering?**

14. **Are the current dataset files exactly the same version of the dataset used for the thesis experiments?**

