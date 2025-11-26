# Multimodal-Sentiment-Analysis-Pipeline-for-YouTube-Videos

### **Text + Audio + Visual Fusion using Deep Learning & Machine Learning**

This repository contains a **complete multimodal sentiment analysis framework** designed to classify YouTube video segments into **Positive, Neutral, and Negative** sentiments using **text, audio, and visual** modalities.
The project evaluates multiple models per modality, applies **10-fold cross-validation**, and uses a **decision-level fusion strategy** with **ELM, SVM, and Random Forest** classifiers.

---

## ⭐ **Key Features**

* **Tri-modal processing (Text + Audio + Visual)**
* **Transformer-based sentiment models** (BERT, RoBERTa, Wav2Vec2, etc.)
* **Rule-based text models** (VADER, TextBlob)
* **Deep-learning facial emotion recognition** using **DeepFace** and **FER**
* **Acoustic emotional analysis** using Mel spectrograms, MFCCs, and prosodic features
* **Decision-level fusion** that combines probability vectors across modalities
* **Supervised classifiers**:
  ✓ Extreme Learning Machine (Best performer)
  ✓ Support Vector Machine
  ✓ Random Forest
* **10-Fold Cross-Validation** for all models
* **Designed for mental-health trend monitoring**

---

## 📁 **Project Structure**

```
├── data/
│   ├── raw_videos/
│   ├── transcripts/
│   ├── audio_segments/
│   ├── frames/
│
├── text_modality/
│
├── audio_modality/
│
├── visual_modality/
│
├── fusion/
│
├── results/
│
└── README.md
```

---

## 🧠 **Methodology**

### **1️⃣ Data Acquisition**

* YouTube videos downloaded using **yt-dlp**
* Transcripts gathered using **YouTube Transcript API**
* 10 videos → 50 segments (5 seconds each)

---

## **2️⃣ Text Modality**

**Models Used**

* DistilBERT (SST-2)
* BERT Multilingual
* RoBERTa-Twitter
* FinBERT
* VADER
* TextBlob

**Process**

* Tokenization → model inference → sentiment mapping
* **Majority voting** generates final text sentiment
* *Best performers*: **TextBlob** & **VADER**

---

## **3️⃣ Audio Modality**

**Features Extracted**

* Mel Spectrograms
* MFCCs
* RMS Energy
* Spectral Rolloff
* Zero Crossing Rate

**Models Used**

* **Wav2Vec2-XLSR-53** (Transformer model)
* **Acoustic-ML** (threshold-based classifier)

*Best performer*: **Wav2Vec2-XLSR (82.5% accuracy)**

---

## **4️⃣ Visual Modality**

**Frame Processing**

* 10 frames per segment
* OpenCV used for:
  ✓ Brightness
  ✓ Contrast
  ✓ Sharpness

**Models Used**

* **DeepFace (VGG-Face backend)**
* **FER + MTCNN**

*Best performer*: **DeepFace (85% accuracy)**

---

## **5️⃣ Multimodal Decision-Level Fusion**

Each modality outputs:

```
[ P(Positive), P(Neutral), P(Negative) ]
```

These are concatenated into a **9-dimensional decision vector**.

**Classifiers Used**

* ✓ Extreme Learning Machine (ELM) → **100% CV accuracy**
* ✓ Support Vector Machine (SVM) → **100% CV accuracy**
* ✓ Random Forest → **98% CV accuracy**
* ✓ Equal-weight averaging → **92% accuracy**

**Winner:**

### 🥇 **Extreme Learning Machine (ELM)**

Fastest, most stable, and most accurate classifier.

---

## 📊 **Results Summary**

| Modality              | Best Model       | Accuracy |
| --------------------- | ---------------- | -------- |
| **Text**              | TextBlob / VADER | 83–82%   |
| **Audio**             | Wav2Vec2-XLSR    | 82.5%    |
| **Visual**            | DeepFace         | 85%      |
| **Multimodal Fusion** | ELM              | **100%** |


Just tell me!
