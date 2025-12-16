#  StudyTrack-AI

**Smart Study Habit Tracking & AI-Based Test Generation System**

---

## Project Overview

StudyTrack-AI is a smart web application designed to help students **track their study habits**, **analyze performance**, and **generate AI-based tests** from study notes.
The system provides personalized insights using dashboards and integrates **Generative AI** to create quizzes automatically.

---

##  Features

*  User Authentication (Student / Admin)
*  Study Activity Dashboard with Analytics
*  Study Log Management (per user email)
*  AI-Based Test Generator (using Groq LLM)
*  Performance Visualization (Charts & Stats)
*  Secure Database Storage (SQLite)

---

##  Tech Stack

### Frontend

* **Streamlit** – Interactive UI & dashboard
* **HTML / CSS (inline)** – Glassmorphism cards & animations

### Backend

* **Python**
* **SQLite** – Database
* **Pandas** – Data processing
* **Matplotlib** – Charts & visualizations

### AI / ML

* **Groq API**
* **LLaMA 3.1 (8B Instant Model)** – Test generation

### Utilities

* **PyPDF2** – PDF text extraction
* **Pytesseract (OCR)** – Image text extraction
* **python-dotenv** – Secure API key handling

---

##  Groq API Key Setup (Important)

 **DO NOT hard-code your API key in the code or GitHub repository.**

###  Step 1: Create `.env` File

In the project root directory, create a file named:

```
.env
```

Add your Groq API key:

```
GROQ_API_KEY=your_groq_api_key_here
```

---

###  Step 2: Install Required Package

```bash
pip install python-dotenv groq
```

---

###  Step 3: Load API Key in Code

```python
from dotenv import load_dotenv
import os
from groq import Groq

load_dotenv()
client = Groq(api_key=os.getenv("GROQ_API_KEY"))
```

---

###  Step 4: Add `.gitignore`

Ensure your `.env` file is NOT uploaded to GitHub.

Create `.gitignore`:

```
.env
*.db
*.csv
__pycache__/
```

---

##  AI Test Generator – How It Works

1. User uploads **notes (PDF / Text / Image)**
2. Text is extracted using **PDF reader / OCR**
3. A prompt is sent to **Groq LLaMA model**
4. AI generates **MCQ questions**
5. User attempts test & gets **instant score**

---

##  Database Design

### Students Table

* `student_id`
* `name`
* `email`
* `password`
* `role`

### Study Log Table

* `log_id`
* `student_email`
* `subject`
* `hours`
* `date`
* `day`
* `method`
* `distraction_time`
* `quiz_score`

 Each user can only see **their own data** using email-based filtering.

---

##  How to Run the Project

Open this file in google colab and run project.

---
