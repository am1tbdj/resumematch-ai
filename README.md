# ResumeMatch AI — Prompt Engineering C9

A runnable prototype that compares a resume with a job description, highlights skill gaps, and suggests resume improvements.

## Setup (Windows PowerShell)

```powershell
py -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m streamlit run app.py
```

The app opens at `http://localhost:8501`.

## Demo workflow

1. Leave **Demo (no API key)** selected.
2. Review the sample resume and job description (or replace them).
3. Click **Analyze match**.
4. Review the score, detected match/gap skills, suggestions, and exportable JSON.

Demo mode is deterministic dictionary-based keyword matching, **not an AI model** and not a validated ATS match. The score is the proportion of detected JD skills also detected in the resume.

## AI-powered prompt workflow

1. Select **AI-powered (OpenAI API)** in the sidebar.
2. Paste an OpenAI API key in the secure field or set `OPENAI_API_KEY` in your environment.
3. Choose a model compatible with Chat Completions JSON output (the default is `gpt-4o-mini`).
4. Click **Analyze match**.

The app uses a recruiter role prompt, evidence-grounded feedback, a 40/30/20/10 rubric, JSON output, and a rule not to invent qualifications. OpenAI API use may be billed. Never commit API keys. Avoid uploading personally identifying or sensitive resume information unless you have consent.

## Limits

- The app extracts text from text-based PDF files; scanned-image PDFs need OCR.
- Matching quality, score consistency, and hallucination rates require testing with real anonymized examples.
- AI output is still fallible; always verify claims before using resume suggestions.
