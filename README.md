# Resume Parser using spaCy RoBERTa

This is a **Streamlit web application** designed to parse resumes and extract key information using a **spaCy NER model** trained on top of the `roberta-base` transformer. The app supports PDFs, Word docs, images, and raw text input. It outputs structured JSON data, tabular insights, and downloadable results.

## Model Performance

| Metric           | Value         |
|------------------|---------------|
| **NER Accuracy** | **56%**       |
| **Base Model**   | `roberta-base` |
| **Framework**    | spaCy v3.x with `spacy-transformers` |
| **Training Data**| 2160 resumes |
| **Testing Data** | 541 resumes  |

The model performs moderately well and can be improved further with:

- More annotated data
- Balanced entity distribution
- Cross-validation tuning

---

## 🧠 NER Model Details

- **Transformer Backbone**: RoBERTa (`roberta-base`)
- **Pipeline Components**: `transformer`, `ner`
- **Max Training Steps**: 8000
- **Dropout**: 0.2
- **Early Stopping Patience**: 3000
- **Batch Size**: 128
- **Evaluation Frequency**: Every 100 steps

### Supported Entities

| Entity Label         | Description                          |
|------------------    |--------------------------------------|
| `PERSON`             | Candidate name                       |
| `EMAIL`              | Email address                        |
| `PHONE`              | Mobile number                        |
| `LOC`                | Residential address or city          |
| `SKILL`              | Technical and soft skills            |
| `DEGREE`             | Academic degrees                     |
| `ORG`                | Company or university                |
| `DATE`               | Duration or date                     |
| `PROJECT_TITLE`      | Project titles                       |
| `PROJECT_ORG`        | Project Organization                 |
| `PROJECT_DURATION`   | Project descriptions                 |
| `CERTIFICATION`      | Certificates, courses                |

### Rule-Based Detectors

In addition to model-predicted entities, we use regex for detecting:

- **LinkedIn**: `linkedin.com/in/…`
- **GitHub**: `github.com/…`
- **LeetCode**: `leetcode.com/…`
- **HackerRank**: `hackerrank.com/…`
- **Portfolio**: Custom domain or personal sites

---

## App Features

- 📤 Upload resumes (PDF, DOCX, PNG, JPG)
- 📝 or Paste raw text from resumes
- 🧠 Uses trained NER model to parse information
- 🧾 Cleaned and structured text
- 📊 View results in JSON and table format
- 📁 Download parsed data as CSV
- ⏱️ Shows processing time per file

---
