# Huntington Disease Prognosis

A machine learning-based Streamlit application for estimating Huntington disease progression stages from clinical and patient-related inputs.

> Disclaimer: This project is for educational, research, and demonstration purposes only. It is not a medical diagnostic system and must not be used as a replacement for consultation with qualified healthcare professionals.

## Table of Contents

- [Project Overview](#project-overview)
- [Application Pages](#application-pages)
- [Key Features](#key-features)
- [Prediction Inputs](#prediction-inputs)
- [Machine Learning Workflow](#machine-learning-workflow)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Model Access](#model-access)
- [Run the Application](#run-the-application)
- [Deployment](#deployment)
- [Files to Keep Private](#files-to-keep-private)
- [Limitations](#limitations)
- [Author](#author)
- [License](#license)

## Project Overview

Huntington Disease Prognosis is an educational machine learning project that helps users understand possible Huntington disease progression stages based on structured clinical inputs.

The application provides an interactive interface where users can enter patient-related values such as age, family history, HTT CAG repeat length, motor score, cognitive score, chorea score, and functional capacity score. The app then estimates a likely stage and presents supportive educational information.

The project includes a Streamlit application, supporting visual assets, and model training notebooks.

## Application Pages

| Page | Purpose |
|---|---|
| Home | Introduces the HD prognosis app and its educational purpose |
| About HD | Explains Huntington disease, symptoms, genetics, and progression stages |
| Stage Prediction Tool | Accepts clinical inputs and predicts the likely disease stage |
| Resources | Provides trusted Huntington disease learning and support links |
| Wellness & Support Tips | Shares general lifestyle and caregiver support guidance |

## Key Features

- Interactive Streamlit user interface
- Huntington disease stage prediction workflow
- Support for model loading from a private ZIP URL stored in Streamlit Secrets
- Demo mode fallback if model artifacts are unavailable
- Educational pages about Huntington disease
- Stage severity gauge using Plotly
- Responsive page layout
- Training notebooks for machine learning experiments

## Prediction Inputs

The prediction form uses the following inputs:

| Input | Description |
|---|---|
| Current Age | Patient age at the time of assessment |
| Sex | Male or Female |
| Family History | Whether Huntington disease is present in family history |
| Age of Symptom Onset | Age when symptoms first appeared |
| HTT CAG Repeat Length | Genetic repeat length associated with Huntington disease |
| Motor Score | Clinical motor symptom score |
| Cognitive Score | Cognitive function score |
| Chorea Score | Involuntary movement score |
| Functional Capacity Score | Independence and daily functioning score |

## Machine Learning Workflow

```text
Patient and Clinical Inputs
        |
        v
Feature Preparation
        |
        v
Encoded Model Input
        |
        v
Trained ML Pipeline
        |
        v
Disease Stage Prediction
        |
        v
Stage Explanation and Support Guidance
```

The app expects model artifacts in a ZIP file that contains:

```text
huntington_model_pipeline.pkl
feature_encoders.pkl
target_encoder.pkl
model_columns.json
```

## Project Structure

```text
Huntington-Prognosis/
|
├── Notebooks/                         # Model training notebooks
│   ├── DT_Training.ipynb
│   ├── LR_Training.ipynb
│   ├── MLP_Training.ipynb
│   ├── RF_Training.ipynb
│   ├── Stacked(LR+MLP+XGB).ipynb
│   └── XGB_Training.ipynb
|
├── STREAMLIT/                         # Streamlit application
│   ├── app.py                         # Main app file
│   ├── brain.png                      # Home page visual
│   ├── HD1.png                        # Huntington disease visual
│   └── HD2.png                        # Huntington disease visual
|
├── .env.example                       # Example secret variable structure
├── .gitignore                         # Git ignore rules
├── LICENSE                            # Project license
├── README.md                          # Project documentation
└── requirements.txt                   # Runtime dependencies
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/harshit04isme/Huntington-Prognosis.git
cd Huntington-Prognosis
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

For macOS or Linux:

```bash
source venv/bin/activate
```

For Windows:

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

## Model Access

The trained model artifacts are not committed to this repository. The app reads a private model ZIP URL from Streamlit Secrets.

Create this local file when running privately:

```text
.streamlit/secrets.toml
```

Add:

```toml
[model]
zip_url = "your_private_model_zip_url"
```

Never commit `.streamlit/secrets.toml` or any real model URL/token to GitHub.

## Run the Application

```bash
streamlit run STREAMLIT/app.py
```

The app will open locally at:

```text
http://localhost:8501
```

## Deployment

This project can be deployed on Streamlit Community Cloud.

Deployment checklist:

- Push the necessary project files to GitHub.
- Set the main app file as `STREAMLIT/app.py`.
- Add the private model ZIP URL in Streamlit Secrets.
- Keep local datasets, model files, virtual environments, and secret files out of GitHub.

## Files to Keep Private

Do not upload:

```text
.streamlit/secrets.toml
.env
models/
*.pkl
*.joblib
*.sav
*.zip
*.csv
*.xlsx
venv/
__pycache__/
```

## Limitations

- This app is for research and education only.
- Predictions depend on the quality and representativeness of the training data.
- It does not replace medical diagnosis, genetic counseling, or neurological assessment.
- Demo mode predictions are rule-based and should not be treated as model results.
- External validation is required before considering any clinical use.

## Author

**Harshit Yadav**

- Email: [hy.harshiyadav01@gmail.com](mailto:hy.harshiyadav01@gmail.com)
- GitHub: [harshit04isme](https://github.com/harshit04isme)

## License

This project is released for educational and research use. Dataset ownership, medical content sources, and model artifacts remain subject to their respective licenses and access permissions.
