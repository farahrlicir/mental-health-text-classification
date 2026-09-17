# Data Extraction

## 1. Data Acquisition

The project uses the Mental Health Reddit Dataset used in the original thesis.

The dataset originates from Reddit and was collected using the Reddit API.

## 2. Raw Data

The raw dataset must be kept separate from processed data.

The project will use the following structure:

data/
├── raw/
├── interim/
└── processed/

The `raw/` directory contains the original dataset without modifications.

## 3. Data Loading

The pipeline should load the raw dataset programmatically rather than relying on manual copy-pasting or notebook-specific paths.

The data loading process should:

1. Locate the raw dataset.
2. Load the required dataset files.
3. Preserve the original data before any transformations.
4. Return the data in a consistent format for the validation stage.

## 4. Reproducibility

The data extraction process should be reproducible.

Another developer should be able to understand:

- where the dataset comes from
- which files are required
- how the files are loaded
- which dataset version was used

## 5. Data Privacy

The dataset contains user-generated Reddit content.

The project should not expose unnecessary personal information.

The original thesis states that usernames and URLs were removed to protect user privacy.

## 6. Open Questions

Before implementing the extraction pipeline, we need to verify:

- What are the exact raw dataset files?
- What are their exact filenames?
- What are their exact column names?
- Is the dataset already split into train, validation, and test files?
- Are the files CSV, JSON, or another format?
- Is the dataset publicly downloadable?
- Which exact dataset version was used for the thesis?
- Does the raw dataset contain any personal information that should be excluded?