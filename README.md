```markdown
# Mubser: Arabic Sign Language Recognition

**Mubser** is an AI-powered Arabic Sign Language recognition system designed to make everyday communication between deaf individuals and the hearing community seamless, accessible, and instant.

This repository contains the full workflow — from data preparation to model training to deployment — for two specialized deep learning models:

- **Model 1** — Arabic alphabet sign recognition  
- **Model 2** — Word-level sign recognition for essential daily vocabulary, trained on a **custom, team-built dataset** (recorded, curated, and synthetically generated)

---

## 🚀 Key Highlights

- 🎥 **Real-time sign recognition** directly from the camera  
- 🧠 **CNN-based deep learning models** tailored for Arabic Sign Language  
- 🧩 **Modular architecture**: built for sign-to-text, designed to scale later to text-to-sign and richer assistive interfaces  
- 📚 **Custom datasets**:
  - Alphabet signs from a curated external dataset
  - Word-level signs from a proprietary dataset crafted by the team, enriched with targeted augmentations for real-world robustness
- 🌐 **Full-stack implementation**: React TypeScript frontend + Python Flask backend

---

## 📂 Repository Structure

### Model 1 — Alphabet Signs

Recognizes Arabic sign alphabet letters.

**Dataset:**
- [Arabic Sign Alphabet Dataset](https://www.kaggle.com/code/manarsabrii/arsl-words-based-acc-95/input)

**Files:**
- `Model 1 - Data Prep.ipynb` — cleaning, balancing, and preparing the dataset  
- `Model 1 - Data Prep Output.zip` — ready-to-train processed data  
- `Model 1.ipynb` — model architecture, training loop, metrics, and evaluation  
- `Model 1 - output.zip` — trained weights / export files  

---

### Model 2 — Word-Level Signs

Built to recognize frequently used Arabic words and phrases.

**Dataset (Mubser-exclusive):**
- Recorded by the team in controlled settings  
- Augmented with synthetic variations:
  - different backgrounds  
  - lighting conditions  
  - hand positions  
  - multiple signers  
- Designed to improve **generalization**, **stability**, and **deployment readiness**

**Files:**
- `Model 2 - Data Prep.ipynb` — dataset assembly, augmentation strategy, preprocessing  
- `Model 2 - Data Prep Output.zip` — processed word-level dataset  
- `Model 2.ipynb` — architecture, training, evaluation, and performance tracking  
- `Model 2 - output.zip` — trained model exports  

---

## 🖥️ Backend — Flask API

The backend serves the trained models via a REST API, handling real-time inference requests from the frontend.

**Location:** `/backend`

**Structure:**
```
backend/
├── app/
│   ├── __init__.py
│   ├── __pycache__/
│   ├── database.py          # Database models and operations
│   ├── inference.py         # Model inference logic
│   ├── main.py             # Flask app routes and endpoints
│   ├── Model_Word.py       # Word model wrapper
│   ├── models.py           # Database schemas
│   └── schemas.py          # API request/response schemas
├── app.db                  # SQLite database
├── cert.pem               # SSL certificate
├── mubser_model89cls.meta.json    # Model 1 metadata (alphabet)
├── mubser_model89cls.onnx         # Model 1 ONNX format
├── mubser_model.meta.json         # Model 2 metadata (words)
├── mubser_model.onnx              # Model 2 ONNX format
└── requirements.txt        # Python dependencies
```

**Key Components:**
- **ONNX Models**: Both models exported in ONNX format for efficient cross-platform inference
- **Flask Routes**: RESTful API endpoints for sign recognition
- **Database**: SQLite for storing user interactions and translation history
- **SSL Support**: Secure HTTPS communication with `cert.pem`

**Setup:**
```bash
cd backend
pip install -r requirements.txt
python -m app.main
```

---

## 🎨 Frontend — React + TypeScript

A modern, responsive web interface for real-time sign language translation.

**Location:** `/Mubser-Frontend`

**Structure:**
```
Mubser-Frontend/
├── components/
│   ├── AccessibilityControls.tsx
│   ├── CallToAction.tsx
│   ├── FAQ.tsx
│   ├── Footer.tsx
│   ├── Header.tsx
│   ├── Hero.tsx
│   ├── HowToUse.tsx
│   ├── icons.tsx
│   ├── pages/              # Route components
│   ├── ScrollToTopButton.tsx
│   ├── SplashScreen.tsx
│   ├── Team.tsx
│   ├── Testimonials.tsx
│   ├── TextToSign.tsx
│   ├── Translator.tsx      # Core translation interface
│   └── WhyMubsir.tsx
├── contexts/
│   └── LanguageContext.tsx # i18n state management
├── hooks/
│   └── useTranslations.ts  # Translation utilities
├── App.tsx                 # Main app component
├── index.html
├── index.tsx               # Entry point
├── metadata.json
├── package.json
├── tsconfig.json
├── types.ts               # TypeScript type definitions
└── vite.config.ts         # Vite build configuration
```

**Features:**
- **Responsive Design**: Works seamlessly on mobile and desktop
- **Accessibility Controls**: Built-in accessibility features
- **Bilingual Support**: Arabic/English interface via `LanguageContext`
- **Live Camera Feed**: Real-time sign capture and recognition
- **Translation History**: Track and review past translations

---

## 🔗 System Architecture

```
┌─────────────────┐
│  React Frontend │ ← User captures sign via camera
└────────┬────────┘
         │ HTTP/WebSocket
         ↓
┌─────────────────┐
│  Flask Backend  │ ← Processes video frames
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│  ONNX Models    │ ← Inference (alphabet/word)
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│  SQLite DB      │ ← Stores results & history
└─────────────────┘
```

---

## 📊 Model Performance

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Alphabet (Model 1) | 98.3%+ | 98.3% | 98.3% | 98.3% |
| Words (Model 2) | 98.6%+ | 95.1% | 94% | 93.8% |


---

## 👥 Team

Created with ❤️ by the Mubser team — bridging communication gaps through AI and accessibility.

