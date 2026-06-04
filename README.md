# Saksham Jain

> CS undergrad at Bennett University · building things that actually work · interested in the gap between research and production

I work on real-time AI systems, RAG pipelines, and assistive technology. Most of my projects start from a problem I find genuinely interesting — Gestura started because live meetings have no accessibility layer for deaf users. The RAG analyzer started because I wanted a financial doc reader that works fully offline.

Published researcher. AWS Certified ML Engineer. Currently in my 3rd year.

---

## what i'm working on

**Gestura v2** — ASL-to-caption desktop app for live video calls  
Real upgrade from v1. Switched from a 16-word CNN+BiLSTM classifier to a full GestureTransformer (Conv1D + multi-head Transformer Encoder, ~3.5M params) trained on WLASL-300 — 3,667 videos, 300 word classes. Added a fingerspelling fallback layer and an LLM correction layer that turns raw predicted word streams into grammatical English. Multi-threaded architecture with virtual camera output — plugs directly into Zoom, Teams, Meet.

`PyTorch` `MediaPipe` `PyQt6` `pyvirtualcam` `OpenCV` `TensorFlow`

**RAG-based financial report analyzer** — fully local, no external API  
PDF ingestion → chunking → embedding → Qdrant vector store → LLM inference via Ollama (Llama 3.2). Async FastAPI backend with multi-PDF support and stateful chat history. Dockerized. Streamlit frontend. Tuned chunking strategy specifically for dense financial text.

`LangChain` `Qdrant` `Ollama` `FastAPI` `Docker` `Streamlit` `PyMuPDF`

---

## project history — gestura

The two versions are pretty different in scope and ambition.

**v1 — proof of concept** *(2024)*  
Single-threaded loop: capture → MediaPipe landmark extraction → Conv1D + BiLSTM + Attention → subtitle overlay → virtual camera output. Supported 16 ASL words. Worked, but the threading model blocked inference on every frame, causing lag in meetings. Model was a fixed 60-frame window classifier — no continuous signing support.

**v2 — production rewrite** *(Jan 2025 → present)*  
Three separate threads: `CaptureThread` / `InferenceThread` / `VirtualCamThread` — nothing blocks anything else. Model replaced with GestureTransformer on WLASL-300 (300 classes, 39.6% top-1 / 60.2% top-5). Added fingerspelling fallback triggered by confidence threshold. LLM correction layer at the end of the pipeline converts raw ASL word sequences into readable sentences. Temporal smoother prevents subtitle flicker on noisy frames.

```
Webcam → MediaPipe landmarks → sliding window buffer
  → GestureTransformer → confidence check
  → [high confidence] word prediction
  → [low confidence] fingerspelling fallback (A–Z)
  → LLM correction layer
  → subtitle overlay → VirtualCam → Zoom / Teams / Meet
```

---

## other projects

**HearTone Analyzer** — audiometry platform  
Automated hearing threshold testing for air conduction across all age groups. Reduces manual intervention in the test workflow. Built with ML models (logistic regression, SVM, linear regression) for hearing loss classification and threshold prediction.

`Python` `Scikit-learn` `PyQt6`

**Zomato EDA** — exploratory data analysis  
Data cleaning, missing value handling, cuisine distribution analysis, rating vs review volume correlations. Built for storytelling, not just numbers.

`Pandas` `NumPy` `Matplotlib` `Seaborn`

---

## research

**"Hybrid CNN–LSTM with Soft Attention for Real-Time ASL Recognition Using MediaPipe Landmarks"**  
*Published — International Conference on Future of Computer Science with AI, Agra*

Designed a CNN-LSTM architecture to capture spatial and temporal patterns from sequential MediaPipe landmark data. Introduced a custom soft attention mechanism to improve robustness across signing speeds and hand sizes. This was the research foundation that Gestura v1 was built on.

---

## stack

```
languages     Python · C++ · SQL
deep learning PyTorch · TensorFlow/Keras · CNN-LSTM · Transformers · Attention · CUDA
genai / llm   LangChain · LangGraph · RAG · Prompt Engineering · Ollama · HuggingFace · Qdrant
backend       FastAPI · Docker · Streamlit · REST APIs · Git
data / cv     Scikit-learn · Pandas · NumPy · OpenCV · MediaPipe · Matplotlib
systems       Multithreading · Concurrent Programming · Virtual Camera Integration
```

---

## certifications

- **AWS Certified Machine Learning Engineer – Associate** (2026)  
  SageMaker pipelines · feature engineering · model deployment
- **Data Analytics Job Simulation — Deloitte Australia / Forage** (2025)  
  Statistical analysis · Tableau

---

## numbers

- 180+ DSA problems on LeetCode → [Saksham_jain0110](https://leetcode.com/u/Saksham_jain0110/)
- CGPA: 8.46 / 10.0
- 1 published paper

---

## links

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/saksham-jain-6a74b128a/)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=flat&logo=leetcode&logoColor=white)](https://leetcode.com/u/Saksham_jain0110/)
[![Email](https://img.shields.io/badge/email-jsaksham677@gmail.com-grey?style=flat&logo=gmail)](mailto:jsaksham677@gmail.com)
