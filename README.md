# Mubser: Arabic Sign Language Recognition

**Mubser** is an AI-powered Arabic Sign Language recognition system designed to make everyday communication between deaf individuals and the hearing community seamless, accessible, and instant.

This repository contains the full workflow — from data preparation to model training — for two specialized deep learning models:

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

## 🔧 Data & Model Pipeline (Overview)

Across both models, Mubser follows a consistent, production-minded pipeline:

...
---
