# Saksham Jain

<p align="left">
  <a href="https://www.linkedin.com/in/saksham-jain-6a74b128a/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://leetcode.com/u/Saksham_jain0110/"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=white" alt="LeetCode" /></a>
  <a href="mailto:jsaksham677@gmail.com"><img src="https://img.shields.io/badge/Email-jsaksham677%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</p>

### 🚀 Building high-performance real-time AI systems and local RAG architectures
CS Undergrad at Bennett University (Class of 2027) · Published Researcher · AWS Certified Machine Learning Engineer - Associate

---

## 🛠️ Tech Stack & Expertise

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>🧠 Deep Learning & AI</strong><br/>
      • <b>Frameworks:</b> PyTorch · TensorFlow / Keras<br/>
      • <b>Architectures:</b> GestureTransformer · CNN-LSTM · Attention Mechanisms<br/>
      • <b>GenAI / LLMs:</b> LangChain · LangGraph · RAG · Ollama · Hugging Face
    </td>
    <td valign="top" width="50%">
      <strong>⚙️ Software & Systems Engineering</strong><br/>
      • <b>Languages:</b> Python · C++ · SQL<br/>
      • <b>Backend / DBs:</b> FastAPI · Qdrant Vector Store · REST APIs<br/>
      • <b>DevOps / Tools:</b> Docker · Git · PyQt6 · Streamlit<br/>
      • <b>Computer Vision:</b> OpenCV · MediaPipe (Holistic/Pose/Hand tracking)
    </td>
  </tr>
</table>

---

## 🌟 Featured Projects

### 🤟 Gestura v2 — Real-Time ASL-to-Caption Desktop App
> **A production-oriented desktop app that translates live ASL gestures into captions and pipes them as a virtual camera for Zoom, Teams, and Google Meet.**

<p align="left">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python">
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-2.x-EE4C2C?style=flat-square&logo=pytorch">
  <img alt="MediaPipe" src="https://img.shields.io/badge/MediaPipe-0.10.14-00A58E?style=flat-square">
  <img alt="PyQt6" src="https://img.shields.io/badge/PyQt6-Desktop-41CD52?style=flat-square&logo=qt">
  <img alt="pyvirtualcam" src="https://img.shields.io/badge/pyvirtualcam-Virtual_Camera-0078D6?style=flat-square">
</p>

- **Three-Layer Recognition Architecture:** 
  1. *Gesture Recognition:* A custom **GestureTransformer (~1.66M params)** trained on the **WLASL-300 dataset** (~3,667 videos) classifying landmark windows into 300 word classes.
  2. *Fingerspelling Fallback:* Automatically falls back to an MLP letter classifier (A-Z) if word-level gesture confidence falls below a set threshold.
  3. *LLM Grammar Layer:* Integrates a pause-activated Gemini API layer that corrects raw sign-word sequences (e.g., `"you name what"` → `"What is your name?"`).
- **Multithreaded Systems Design:** Engineered a responsive PyQt6 app separating camera capture, model inference, temporal smoothing, and virtual camera output into 4 concurrent threads to prevent UI lag and maintain stable video streaming.
- **Verification & Performance:** Achieved 39.6% top-1 and 60.2% top-5 validation accuracy on WLASL-300 landmarks (a highly complex dataset).
- **Production Packaging & CI/CD Deployment:** Bundled the desktop app with PyInstaller (~2.72 GB ZIP / ~4.31 GB extracted) for zero-dependency runs. Deployed the landing site via AWS Amplify CI/CD, serving global client downloads via an Amazon CloudFront CDN distribution securely connected to a private S3 bucket using Origin Access Control (OAC).
- 🔗 **[Gestura Website](https://main.d9h6fx0138k7u.amplifyapp.com/)** | **[Demo Video](https://www.youtube.com/watch?v=-pgvQyp-oF0)** | **[Research Paper](https://drive.google.com/file/d/1zT-9kl8uMixt35fh_YmMm7v4dmrmR6jh/view?usp=sharing)**

#### 🔄 Evolution: From Prototype (v1) to Production (v2)

| Feature | Gestura v1 (2024 Prototype) | Gestura v2 (2025 Production) |
|---|---|---|
| **Vocabulary** | 16 controlled ASL words | **300 ASL words** (WLASL-300) |
| **Model** | Conv1D + BiLSTM + Attention (Keras) | **Structured Embedding + Conv1D + Transformer** (PyTorch) |
| **Architecture** | Single-threaded loop (lagged frame capture) | **4-Thread Concurrent Pipeline** (no blocking) |
| **UX Output** | Raw frame overlay subtitles | **Virtual Camera feed ("Gestura Cam")** directly into meeting apps |

---

### 📂 Local Financial Report Analyzer
> **A fully local, privacy-first RAG pipeline for processing and analyzing complex financial documents without sending data to external APIs.**

<p align="left">
  <img alt="LangChain" src="https://img.shields.io/badge/LangChain-Framework-black?style=flat-square&logo=chainlink">
  <img alt="Qdrant" src="https://img.shields.io/badge/Qdrant-Vector_Database-red?style=flat-square">
  <img alt="Ollama" src="https://img.shields.io/badge/Ollama-Local_Inference-grey?style=flat-square">
  <img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-Backend-009688?style=flat-square&logo=fastapi&logoColor=white">
  <img alt="Docker" src="https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square&logo=docker&logoColor=white">
</p>

- **Custom RAG Strategy:** Designed a recursive chunking and formatting pipeline optimized for parsing dense financial tables and multi-column PDFs using `PyMuPDF`.
- **Vector Search & Storage:** Configured a local **Qdrant vector store** with optimized similarity metrics.
- **Fully Offline Inference:** Orchestrated local LLM runs using **Ollama (Llama 3.2)** and LangChain to maintain 100% data privacy.
- **Web App Shell:** Built an async FastAPI backend serving a responsive, clean Streamlit frontend. Dockerized the entire application for single-command deployment.

---

## 📈 Other Projects

*   **HearTone Analyzer:** An automated audiometry platform for air conduction hearing threshold testing. Built with Scikit-learn (Logistic Regression, SVM, Linear Regression) and packaged as a PyQt6 desktop application.
*   **Zomato EDA:** Exploratory data analysis project focused on data cleaning, ratings correlations, and cuisine distributions. Designed around narrative storytelling using Pandas, NumPy, Matplotlib, and Seaborn.

---

## 📝 Research & Publications

📖 **"Hybrid CNN–LSTM with Soft Attention for Real-Time ASL Recognition Using MediaPipe Landmarks"**  
*Published — International Conference on Future of Computer Science with AI (Agra)*  
*   **Contribution:** Designed a spatial-temporal CNN-LSTM pipeline that processes MediaPipe skeleton landmark streams. Introduced a soft attention layer that weights key gesture moments over setup or transition noise. This research laid the technical foundation for Gestura's real-time performance.

---

## 🏅 Certifications & Education

*   **AWS Certified Machine Learning Engineer – Associate** (2026)
*   **Deloitte Australia Data Analytics Simulation** (Forage, 2025)
*   **Education:** Bennett University, B.Tech in Computer Science · **CGPA: 8.46 / 10.0**
*   **Problem Solving:** 180+ problems solved on LeetCode ([Profile Link](https://leetcode.com/u/Saksham_jain0110/))
