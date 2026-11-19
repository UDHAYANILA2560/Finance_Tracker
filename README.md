# AI-Powered Personal Finance Tracker Backend

FastAPI backend featuring SQLAlchemy SQLite database, JWT authentication, Scikit-learn expense categorization and prediction, FAISS RAG, and Google Gemini 2.5 Flash integration.

## Setup Instructions

### 1. Open Terminal & Navigate to Backend Folder
```powershell
cd Backend
```

### 2. Create Virtual Environment
```powershell
python -m venv venv
```

### 3. Activate Virtual Environment (Windows PowerShell)
```powershell
.\venv\Scripts\Activate.ps1
```

### 4. Install Dependencies
```powershell
pip install -r requirements.txt
```

### 5. Create `.env` File
Copy `.env.example` to `.env`:
```powershell
copy .env.example .env
```
Edit `.env` to add your actual Google Gemini API key:
```env
GEMINI_API_KEY=YOUR_ACTUAL_GEMINI_API_KEY
GEMINI_BASE_URL=https://generativelanguage.googleapis.com
GEMINI_MODEL=gemini-2.5-flash
SECRET_KEY=supersecretjwtkey_change_in_production_12345
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=1440
DATABASE_URL=sqlite:///./data/finance_tracker.db
```

### 6. Train Expense Categorization Model
```powershell
python -m app.ml.train_model
```

### 7. Run Pytest Test Suite
```powershell
pytest tests/test_backend.py
```

### 8. Start FastAPI Server
```powershell
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

### 9. View Swagger Documentation
Open your browser and navigate to:
`http://127.0.0.1:8000/docs`
