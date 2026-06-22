# FDA Medical Device Classification System

## Project Overview

This project develops an FDA medical device classification system that automatically predicts the corresponding FDA Regulation Number and Product Code from a free-text medical device description.

The system adopts a Hybrid Retrieval + GPT Classification architecture, combining FDA CFR knowledge-base retrieval with large language model reasoning to perform regulatory classification.

---

## Repository Contents

### code

Main notebook: `fda_device_classifier.ipynb`

The notebook implements the complete classification pipeline, including:

* CFR data parsing
* Embedding-based retrieval
* Query rewriting
* GPT classification
* Consistency checking
* Performance evaluation

---

### data

FDA CFR structured knowledge base: `medical_device_CFR_PCDV.json`

100-device evaluation dataset: `dataset100.zip`

---

### results

Final classification results: `classification_results.xlsx`

Complete prediction outputs: `results.json`

---

### report

Project final report: `FDA_Device_Classifier_Final_Report.pdf`

This report is the primary project documentation and is strongly recommended for anyone reviewing or extending the project.

The report provides detailed information on:

* Project objectives and background
* End-to-end workflow design
* System architecture and implementation
* Description of each pipeline component
* Experimental results and evaluation
* Error analysis and bottleneck identification
* Potential future improvements

For a complete understanding of the project design, methodology, results, and future directions, please review this report first.

---

## Main Results

### Overall Accuracy

| Category                                    | Correct | Total | Accuracy |
| ------------------------------------------- | ------- | ----- | -------- |
| Overall                                     | 64      | 100   | 64.0%    |
| Path A (has device description)             | 61      | 97    | 62.9%    |
| Path B (description extracted from summary) | 3       | 3     | 100.0%   |

---

## Reproduction Steps

Place the following data files in the same working directory as the notebook:

* `medical_device_CFR_PCDV.json`
* `dataset100.zip`

Open `fda_device_classifier.ipynb`.

In **Cell 2**, provide your OpenAI API key and verify that the file paths are correctly configured.

Then execute all notebook cells sequentially from top to bottom.

The notebook will automatically:

* Build the CFR knowledge base
* Generate CFR embeddings
* Perform Top-40 candidate retrieval
* Run GPT classification
* Produce prediction and evaluation outputs

---

## Notes

The embedding cache file

`cfr_embeddings.json`

is not included in this repository due to its large file size.

It can be regenerated automatically by running the notebook.