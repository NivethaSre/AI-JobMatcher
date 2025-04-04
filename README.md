# AI-JobMatcher

## Overview
The **AI-Resume-Screener** is an intelligent system designed to automatically evaluate and classify resumes based on job descriptions. Using **Natural Language Processing (NLP)** techniques such as **TF-IDF, BERT embeddings, and XGBoost**, this tool efficiently ranks resumes for better candidate selection. The project also features a **FastAPI-based interface** for easy resume uploading and evaluation.

## Key Features
✅ **Resume Parsing** – Extracts text from resumes in PDF and DOCX formats.  
✅ **TF-IDF & BERT-based Matching** – Compares resumes with job descriptions for relevance.  
✅ **Skill Matching** – Identifies and scores skills based on predefined job requirements.  
✅ **Suitability Prediction** – Uses an XGBoost model to predict the best candidates.  
✅ **FastAPI Integration** – Provides a user-friendly API for uploading and processing resumes.  
✅ **Automated Ranking** – Assigns scores to resumes based on similarity and skills match.  

---
## Installation & Setup
### Step 1: Create a Virtual Environment
```bash
python -m venv venv
# Activate on Windows
venv\Scripts\activate
# Activate on macOS/Linux
source venv/bin/activate
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Download Necessary NLP Models
```bash
python -m spacy download en_core_web_sm
```

### Step 4: Run the FastAPI Server
```bash
uvicorn main:app --reload
```
📌 The server will run at `http://127.0.0.1:8000`

### Step 5: Access API Documentation
Navigate to `http://127.0.0.1:8000/docs` for an interactive API testing interface.

---
## API Endpoints
| Method  | Endpoint          | Description                   |
|---------|------------------|-------------------------------|
| `POST`  | `/upload`        | Upload a resume for screening |
| `POST`  | `/match`         | Match resume with job description |
| `GET`   | `/ranked_list`   | Get ranked resumes based on scores |

---
## Project Structure
```
ai-resume-screener/
├── uploads/               # Directory for uploaded resumes
├── main.py                # FastAPI application
├── resume_parser.py       # Extracts text from resumes
├── job_matcher.py         # Job matching & skill extraction
├── ml_model.py            # XGBoost-based prediction
├── requirements.txt       # Dependencies list
└── README.md              # Project documentation
```

---
## How It Works
1. **Upload resumes** – The system extracts text using `pdfplumber` and `python-docx`.
2. **Process job descriptions** – Extracts keywords using TF-IDF and BERT embeddings.
3. **Analyze skill match** – Identifies relevant skills in the resume.
4. **Predict suitability** – The XGBoost model assigns scores to resumes.
5. **Return ranked candidates** – The system provides a sorted list based on job relevance.

---
## Future Enhancements
🚀 **Expand support for more resume formats** (CSV, JSON).  
🚀 **Improve accuracy using transformer-based models** like RoBERTa.  
🚀 **Add a web-based frontend for easy interaction**.  

---
## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch (`feature-branch-name`).
3. Commit your changes.
4. Submit a pull request.

---
## License
This project is licensed under the **MIT License**.



