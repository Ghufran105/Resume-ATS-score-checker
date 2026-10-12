# 📄 ATS Resume Checker

Upload a resume (PDF, DOCX or TXT) and get:

- An **ATS score out of 100**
- A score breakdown (formatting, keywords, impact, skills, education, readability)
- Strengths, prioritized improvements, missing keywords and before/after rewrites
- Optional: paste a **job description** for better keyword matching

Built with **Streamlit** and **Gemini 3.8 Flash** (`gemini-3.8-flash`).

> Scores are AI estimates, not output from a real ATS. Use them as guidance.

## Files

| File | Purpose |
|------|---------|
| `app.py` | The whole app (UI + AI logic) |
| `requirements.txt` | Python dependencies |
| `README.md` | This file |

## Run locally

```bash
pip install -r requirements.txt
export GEMINI_API_KEY="your-key"      # Windows PowerShell: $env:GEMINI_API_KEY="your-key"
streamlit run app.py
```

Get a free key at <https://aistudio.google.com/apikey>.
You can also skip the variable and paste the key into the app's sidebar.

## Deploy on Streamlit Community Cloud

1. Push these 3 files to a GitHub repository (root of the repo).
2. Go to <https://share.streamlit.io> and sign in with GitHub.
3. Click **Create app** → choose your repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add:
   ```toml
   GEMINI_API_KEY = "your-key"
   ```
5. Click **Deploy**.

**Never commit your API key to GitHub.** Keep it only in Secrets.

## Notes

- Scanned/image-only PDFs have no readable text; export a text-based PDF or DOCX.
- Resumes are sent to Google's Gemini API for analysis.
- To change the model, edit `MODEL_ID` at the top of `app.py`.
