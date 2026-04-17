# 📃 AI Resume Critiquer

An AI-powered Streamlit web app that analyzes your resume and provides constructive, role-specific feedback using the Grok AI model.

---

## Features

- Upload your resume in **PDF** or **TXT** format
- Optionally specify a **target job role** for tailored feedback
- Receive structured feedback covering:
  - Content clarity and impact
  - Skills presentation
  - Experience descriptions
  - Role-specific improvement suggestions

---

## Prerequisites

- Python 3.8+
- An **xAI API key** (for Grok model access)

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/ai-resume-critiquer.git
   cd ai-resume-critiquer
   ```

2. **Install dependencies**
   ```bash
   pip install streamlit PyPDF2 requests
   ```

3. **Configure your API key**

   Create a `.streamlit/secrets.toml` file in the project root:
   ```toml
   XAI_API_KEY = "your-xai-api-key-here"
   ```

---

## Usage

1. **Run the app**
   ```bash
   streamlit run main.py
   ```

2. Open your browser and go to `http://localhost:8501`

3. Upload your resume (PDF or TXT), optionally enter a target job role, and click **Analyze Resume**

---

## Project Structure

```
ai-resume-critiquer/
├── main.py                  # Main Streamlit application
├── .streamlit/
│   └── secrets.toml         # API key configuration (do not commit)
└── README.md
```

---

## Configuration

| Secret | Description |
|--------|-------------|
| `XAI_API_KEY` | Your xAI API key for accessing the Grok model |

> ⚠️ Never commit your `secrets.toml` file. Add `.streamlit/secrets.toml` to your `.gitignore`.

---

## Deploying to Streamlit Cloud

1. Push your code to a GitHub repository (without `secrets.toml`)
2. Go to [streamlit.io/cloud](https://streamlit.io/cloud) and connect your repo
3. Under **App Settings → Secrets**, add:
   ```
   XAI_API_KEY = "your-xai-api-key-here"
   ```

---

## Limitations

- PDF text extraction may not work well with image-based or scanned resumes
- Analysis quality depends on the clarity and completeness of the resume content
- API response is capped at 1000 tokens per request
