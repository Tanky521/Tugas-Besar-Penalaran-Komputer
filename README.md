# Case-Based Reasoning (CBR) for Court Decision Analysis

## Project Overview

This project implements a **Case-Based Reasoning (CBR)** system for analyzing court decisions in Indonesia. The system utilizes historical court case data to retrieve similar cases and provide solution recommendations based on previous judicial decisions.

The dataset consists of court decisions related to:

* Sexual Violence
* Rape
* Sexual Harassment
* Non-Physical Sexual Harassment

The project follows the standard CBR cycle:

1. Case Base Construction
2. Case Representation
3. Case Retrieval
4. Case Solution Reuse
5. Model Evaluation

---

## Team Members

| Name                 | Student ID      |
| -------------------- | --------------- |
| Noval Kurniawan Kodi | 202310370311213 |
| Bintang Nazwar | 202310370311063 |

---

## Dataset

Source:

* Direktori Putusan Mahkamah Agung Republik Indonesia

Dataset Attributes:

| Column        | Description            |
| ------------- | ---------------------- |
| nomor_perkara | Case number            |
| tanggal       | Decision date          |
| jenis_perkara | Type of case           |
| pihak         | Parties involved       |
| pasal         | Legal articles applied |
| fakta         | Case facts             |
| argumen_hukum | Legal reasoning        |

---

## Project Structure

```text
CBR-Court-Decision/
│
├── data/
│   ├── raw/
│   ├── processed/
│   │   └── cases_representation.csv
│   ├── eval/
│   │   ├── queries.json
│   │   ├── retrieval_metrics.csv
│   │   └── prediction_metrics.csv
│   └── results/
│       └── predictions.csv
│
├── notebooks/
│   ├── 02_case_representation.ipynb
│   ├── 03_case_retrieval.ipynb
│   ├── 04_case_solution_reuse.ipynb
│   └── 05_model_evaluation.ipynb
│
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/username/CBR-Court-Decision.git
cd CBR-Court-Decision
```

Install required packages:

```bash
pip install -r requirements.txt
```

---

## Required Libraries

```text
pandas
numpy
scikit-learn
matplotlib
seaborn
json
```

Or install manually:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

---

## Methodology

### 1. Case Representation

Each court decision is transformed into a structured representation containing:

* Metadata extraction
* Fact summary
* Legal argument extraction
* Word count features
* Combined document representation

Output:

```text
cases_representation.csv
```

---

### 2. Case Retrieval

Document representation is generated using:

* TF-IDF Vectorization
* Cosine Similarity

The retrieval function returns Top-K most similar cases.

Example:

```python
retrieve(
    "sexual violence against minors",
    k=5
)
```

Output:

```text
Top-5 most similar cases
```

---

### 3. Case Solution Reuse

The legal argument from the most similar case is reused as the predicted solution.

Example:

```python
predict_outcome(
    "sexual harassment against a child"
)
```

Output:

```text
Predicted legal argument
```

---

### 4. Model Evaluation

Classification models used:

* Naive Bayes
* Support Vector Machine (SVM)

Evaluation metrics:

* Accuracy
* Precision
* Recall
* F1-Score

Generated files:

```text
retrieval_metrics.csv
prediction_metrics.csv
```

---

## Results

The performance of each model is evaluated using a test dataset and compared using:

* Accuracy
* Precision
* Recall
* F1-Score

Visualization is provided through bar charts and confusion matrices.

---

## Running the Project

### Step 1

Run:

```text
02_case_representation.ipynb
```

Generate:

```text
cases_representation.csv
```

### Step 2

Run:

```text
03_case_retrieval.ipynb
```

Generate:

```text
queries.json
```

### Step 3

Run:

```text
04_case_solution_reuse.ipynb
```

Generate:

```text
predictions.csv
```

### Step 4

Run:

```text
05_model_evaluation.ipynb
```

Generate:

```text
retrieval_metrics.csv
prediction_metrics.csv
```

---

## Conclusion

This project demonstrates the implementation of a Case-Based Reasoning (CBR) system for court decision analysis using TF-IDF, Cosine Similarity, Naive Bayes, and Support Vector Machine (SVM). The system is capable of retrieving similar historical cases and reusing their legal reasoning to support decision recommendations for new cases.

---

## License

This project was developed for academic purposes in the Computer Reasoning course, Department of Informatics, Universitas Muhammadiyah Malang.
