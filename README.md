# ✨ Mubser: Arabic Sign Language Recognition

**Mubser** is an AI-powered Arabic Sign Language recognition system designed to make everyday communication between deaf individuals and the hearing community seamless, accessible, and instant.

This repository contains the full workflow — from data preparation to model training to deployment — for two specialized deep learning models:

- **Model 1** — Arabic alphabet sign recognition  
- **Model 2** — Word-level sign recognition for essential daily vocabulary, trained on a **custom, team-built dataset** (recorded, curated, and synthetically generated)
---

## 🚀 Key Highlights

- **Real-time sign recognition** directly from the camera  
- **CNN-based deep learning models** tailored for Arabic Sign Language  
- **Modular architecture**: built for sign-to-text, designed to scale later to text-to-sign and richer assistive interfaces  
- **Custom datasets**:
  - Alphabet signs from a curated external dataset
  - Word-level signs from a proprietary dataset crafted by the team, enriched with targeted augmentations for real-world robustness
- **Full-stack implementation**: React TypeScript frontend + Python Flask backend

---

# 📂 Repository Structure

## Model 1 — Alphabet Signs

Recognizes Arabic sign alphabet letters.

**Dataset:**
- [Arabic Sign Alphabet Dataset](https://www.kaggle.com/code/manarsabrii/arsl-words-based-acc-95/input)

**Files:**
- `Model 1 - Data Prep.ipynb` — cleaning, balancing, and preparing the dataset  
- `Model 1 - Data Prep Output.zip` — ready-to-train processed data  
- `Model 1.ipynb` — model architecture, training loop, metrics, and evaluation  
- `Model 1 - output.zip` — trained weights / export files  

---

## Model 2 — Word-Level Signs

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

# 🖥️ Backend — Flask API

The backend serves the trained models via a REST API, handling real-time inference requests from the frontend.

**Location:** `/backend`

### Folder Structure
```
backend/
├── app/
│   ├── __init__.py
│   ├── __pycache__/
│   ├── database.py          
│   ├── inference.py         
│   ├── main.py             
│   ├── Model_Word.py       
│   ├── models.py           
│   └── schemas.py          
├── app.db                  
├── cert.pem               
├── mubser_model89cls.meta.json    
├── mubser_model89cls.onnx         
├── mubser_model.meta.json         
├── mubser_model.onnx              
└── requirements.txt        
```

### Key Components
- **ONNX Models** — exported for fast inference  
- **Flask Routes** — REST API endpoints  
- **Database** — SQLite for history & interactions  
- **SSL Support** — secure communication via HTTPS  

---

# 🎨 Frontend — React + TypeScript

A modern, responsive web interface for real-time sign language translation.

**Location:** `/Mubser-Frontend`

### Structure
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
│   ├── pages/              
│   ├── ScrollToTopButton.tsx
│   ├── SplashScreen.tsx
│   ├── Team.tsx
│   ├── Testimonials.tsx
│   ├── TextToSign.tsx
│   ├── Translator.tsx      
│   └── WhyMubsir.tsx
├── contexts/
├── hooks/
├── App.tsx
├── index.html
├── index.tsx
├── metadata.json
├── package.json
├── tsconfig.json
├── types.ts
└── vite.config.ts
```


---

# 🔗 System Architecture

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

# 📊 Model Performance

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Alphabet (Model 1) | 98.3%+ | 98.3% | 98.3% | 98.3% |
| Words (Model 2) | 98.6%+ | 95.1% | 94% | 93.8% |

---

# 👥 Team

Created with ❤️ by Mubser team — bridging communication gaps through AI and accessibility.
