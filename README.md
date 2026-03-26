# 🌸 SheCares AI -Care for her,Care for all

### *Health Assessment & Period Tracking Web App*

**Empowering women with AI-driven insights into PCOS, pregnancy, menopause, and menstrual health — all in one secure, intelligent platform.**




 🎀 *Built with care — for every woman, at every stage of her journey.*



## 💜 About SheCares AI

SheCares AI is a machine-learning-powered health web application designed to give women meaningful, personalized insights into their reproductive and hormonal health. From tracking menstrual cycles to assessing PCOS indicators and menopause signals, SheCares AI bridges the gap between complex medical data and everyday health awareness.

With a secure multi-user backend, an intelligent ML assessment engine, and an automated period tracking module — SheCares AI makes health intelligence accessible, private, and reliable.

---

## ✨ Core Features

| 🌟 Feature | 📋 Description |
|-----------|---------------|
| 🔬 **PCOS Assessment** | ML-driven evaluation of PCOS indicators based on user health inputs |
| 🤰 **Pregnancy Signals** | Intelligent detection of early pregnancy-related health patterns |
| 🌙 **Menopause Detection** | Identifies hormonal signals associated with menopause transition |
| 🩸 **Period Tracking** | Automated cycle computation with next-period and ovulation predictions |
| 🔐 **Secure Authentication** | Multi-user login and session management via Flask |
| 🧠 **Smart Fallback Scoring** | Structured scoring system ensures uninterrupted assessments if ML model is unavailable |
| 💾 **Persistent Health Records** | All cycle data and assessments stored securely in SQLite |
| ⚡ **Real-Time Predictions** | Optimized backend workflows deliver instant health insights |

---

## 🧬 Health Assessment Modules

### 🔬 PCOS Indicator Assessment
Analyzes user-reported symptoms and health metrics through a trained ML model to assess the likelihood of Polycystic Ovary Syndrome. Provides risk levels and actionable guidance.

### 🤰 Pregnancy Status Detection
Evaluates symptom patterns and cycle data to detect early signals associated with pregnancy, offering informational insights to guide next steps.

### 🌙 Menopause Signal Analysis
Monitors hormonal and cycle-related inputs to identify signs of perimenopause and menopause transition, helping users understand their body's changes.

### 🩸 Menstruation Tracking Module

```
Last Period Date Entered
        │
        ├──▶ Cycle Length Computation
        │
        ├──▶ Next Period Prediction
        │
        ├──▶ Ovulation Window Estimation
        │
        └──▶ Stored to SQLite → History Dashboard
```

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                        USER BROWSER                              │
│  ┌─────────────┐   ┌──────────────────┐   ┌──────────────────┐  │
│  │  Auth Pages │   │ Health Assessment │   │  Period Tracker  │  │
│  │  Login/Reg  │   │ PCOS / Pregnancy  │   │  Cycle History   │  │
│  └──────┬──────┘   └────────┬─────────┘   └────────┬─────────┘  │
└─────────┼───────────────────┼─────────────────────┼─────────────┘
          └───────────────────▼─────────────────────┘
                              │  HTTP Requests
┌─────────────────────────────▼────────────────────────────────────┐
│                        FLASK BACKEND                             │
│                                                                  │
│  ┌─────────────┐  ┌──────────────────┐  ┌─────────────────────┐ │
│  │ Auth Routes │  │ Assessment Routes │  │   Tracking Routes   │ │
│  │  Sessions   │  │  /assess/pcos     │  │   /track/period     │ │
│  └─────────────┘  └────────┬─────────┘  └─────────────────────┘ │
│                            │                                     │
│             ┌──────────────▼─────────────────┐                   │
│             │       ML Assessment Engine     │                   │
│             │  ┌─────────────────────────┐   │                   │
│             │  │   ML Model  (Primary)   │   │                   │
│             │  └──────────┬──────────────┘   │                   │
│             │     if unavailable ▼            │                   │
│             │  ┌──────────────────────────┐  │                   │
│             │  │  Fallback Scoring Logic  │  │                   │
│             │  └──────────────────────────┘  │                   │
│             └────────────────────────────────┘                   │
└─────────────────────────────┬────────────────────────────────────┘
                              │
                   ┌──────────▼──────────┐
                   │   SQLite Database   │
                   │  ┌───────────────┐  │
                   │  │     Users     │  │
                   │  │  Assessments  │  │
                   │  │  Cycle Logs   │  │
                   │  │   Sessions    │  │
                   │  └───────────────┘  │
                   └─────────────────────┘
```

---

## 🛠️ Tech Stack

### Backend
- **Python 3.x** — Core application language
- **Flask** — Web framework, routing, session management, authentication

### AI / Machine Learning
- **Scikit-learn / ML Model** — Trained classifier for health condition assessment
- **Fallback Scoring Engine** — Rule-based structured scoring when ML model is unavailable
- **Cycle Computation Logic** — Custom algorithm for period and ovulation prediction

### Database
- **SQLite** — Lightweight, persistent database for user records, health logs, and cycle data

### Frontend
- **HTML5 / CSS3 / JavaScript** — Responsive, accessible user interface
- **Jinja2** — Server-side template rendering

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/shecares-ai.git
cd shecares-ai

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate         # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Initialize the database
python init_db.py

# 5. Run the application
python app.py
```

Open your browser and visit → `http://localhost:5000` 🌸

---

## 📦 Requirements

```txt
flask
scikit-learn
numpy
pandas
joblib
python-dotenv
```

---

## 🗂️ Project Structure

```
shecares-ai/
│
├── app.py                      # Flask application entry point
├── init_db.py                  # Database initialization
├── requirements.txt
│
├── models/
│   ├── pcos_model.pkl          # Trained PCOS ML model
│   ├── pregnancy_model.pkl     # Pregnancy signal model
│   ├── menopause_model.pkl     # Menopause detection model
│   └── fallback_scorer.py      # Rule-based fallback scoring engine
│
├── routes/
│   ├── auth.py                 # Login, signup, session management
│   ├── assessment.py           # ML health assessment routes
│   └── tracker.py              # Period tracking & cycle computation
│
├── database/
│   └── shecares.db             # SQLite database
│
├── templates/                  # Jinja2 HTML templates
│   ├── base.html
│   ├── login.html
│   ├── dashboard.html
│   ├── assessment.html
│   └── tracker.html
│
└── static/
    ├── css/
    ├── js/
    └── images/
```

---

## 🧠 ML Assessment Engine

### Model Loading with Intelligent Fallback

```python
# Primary: Load trained ML model
try:
    model = joblib.load('models/pcos_model.pkl')
    prediction = model.predict(user_inputs)

# Fallback: Structured scoring logic
except Exception:
    prediction = fallback_scorer.evaluate(user_inputs)
```

This dual-layer approach ensures **zero downtime** for health assessments — even if the ML model fails to load, users receive reliable, rule-based insights without interruption.

---

## 🩸 Period Tracking Logic

```
User Inputs: Last Period Date + Average Cycle Length
        │
        ├──▶ Next Period Date  =  Last Period + Cycle Length
        │
        ├──▶ Ovulation Window  =  Next Period − 14 days (±2)
        │
        ├──▶ Fertile Window    =  Ovulation − 5 to Ovulation + 1
        │
        └──▶ Saved to SQLite with timestamp → Displayed in History
```

---

## 🔐 Authentication & Security

- **Password hashing** for secure credential storage
- **Flask session management** for stateful multi-user access
- **Route protection** — assessment and tracking pages require authentication
- **Per-user data isolation** — every user accesses only their own health records

---

## 📸 Screenshots

> *Add screenshots of your Dashboard, Assessment Form, Period Tracker, and Results Page here.*

| Dashboard | Health Assessment | Period Tracker |
|:---------:|:-----------------:|:--------------:|
| `dashboard.png` | `assessment.png` | `tracker.png` |

---

## 🌐 Future Roadmap

- [ ] 📊 Visual cycle charts and health trend graphs
- [ ] 🔔 Email / SMS reminders for upcoming periods
- [ ] 🩺 Doctor report export as PDF summary
- [ ] 📱 Mobile-responsive PWA
- [ ] 🌍 Multilingual support for regional accessibility
- [ ] 🤖 AI chatbot for personalized health Q&A
- [ ] ☁️ Cloud deployment with encrypted user data

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

```bash
# Fork the repository, then:
git checkout -b feature/your-feature-name
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
# Open a Pull Request 🎉
```

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 💌 Acknowledgements

- [Flask](https://flask.palletsprojects.com/) — clean, powerful Python web framework
- [Scikit-learn](https://scikit-learn.org/) — the ML backbone of our health assessment engine
- Every woman who deserves better health tools — *this was built for you* 💜

---


**`♀  SheCares AI — Because every woman's health story matters  ♀`**



🌸 *Star this repo to support women's health tech!* 🌸


*Built with 💜 for She Cares AI*

