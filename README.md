# 🎓 MineAI Tutor

An AI-powered tutoring assistant built for students, created by a 15-year-old developer from Italy.

**Live Demo:** [mineai-teach.streamlit.app](https://mineai-teach.streamlit.app)

---

## 🤖 What is MineAI?

MineAI is a web-based assistant designed to support students with homework, research, writing, and problem-solving.
It combines fast and advanced Llama models, web retrieval, file analysis, and persistent memory in a single app experience.

> ⚠️ **Language note**
> - The UI supports **Italian** and **English**
> - Responses adapt to user language when possible
> - Some edge cases may still need tuning

---

## ✨ Core Features

- **Multi-model AI routing**
  - Llama 4 Scout (Top)
  - Llama 3.3 70B (Stable)
  - Llama 3.1 8B (Fast)
- **Response styles**
  - Brief / Standard / Deep
- **Smart conversation memory**
  - Long context window with safety budgeting
  - Follow-up understanding (e.g. “continue”, “more details”)
- **Real-time web augmentation**
  - Tavily-backed retrieval with source links
- **Universal file support**
  - Text, markdown, JSON, CSV, Excel, PDF, DOCX, images, and more
- **Image understanding**
  - Ask custom questions on uploaded images
- **Persistent chat history**
  - Stored in Supabase per user
- **Built-in BI tools**
  - Upload CSV/XLSX and open an interactive dashboard
- **Authentication system**
  - Login/registration with Supabase-backed users

---

## 🧠 Product Highlights

- Clean, Gemini-inspired starting screen before first user message
- Focus mode UI for reduced visual noise
- Guardrails for safer AI-comparison answers (less hallucinated claims)
- Structured competitor comparison responses (short and detailed modes)
- Context-aware self-knowledge responses about MineAI itself

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Streamlit |
| AI Inference | Groq |
| Text Models | Llama 4 Scout, Llama 3.3 70B, Llama 3.1 8B |
| Vision | Llama vision model via Groq |
| Web Retrieval | Tavily API |
| Database | Supabase (PostgreSQL) |
| Charts | Plotly |
| Hosting | Streamlit Cloud |

---

## 🚀 Try It

👉 [mineai-teach.streamlit.app](https://mineai-teach.streamlit.app)

Create a free account and start using MineAI.

---

## 📬 Feedback & Contact

If you have suggestions, improvements, or collaboration ideas, open an issue in this repository.

---

## 📄 License

This project is closed source.  
All rights reserved.
