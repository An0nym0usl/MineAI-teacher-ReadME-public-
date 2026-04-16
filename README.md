# 🎓 MineAI Tutor

An AI-powered tutoring assistant built for students, created by a 15-year-old developer from Italy.

**Live Demo:** [mineai-teach.streamlit.app](https://mineai-teach.streamlit.app)

This README is meant for **people using the Streamlit app** (and visitors from the app link). It summarizes what MineAI offers, how it behaves, and what to watch out for — not a full technical manual.

---

## 🤖 What is MineAI?

MineAI is a web-based assistant for homework, research, writing, and problem-solving. It combines **fast Llama-class models** (via Groq), optional **extra model providers** when enabled on the server, **web search**, **URL reading**, **file and image analysis**, optional **image generation**, and **saved chat history** in one Streamlit experience.

> **Language note**
> - The UI supports **many languages** (including Italian, English, Spanish, French, German, Portuguese, Japanese, Chinese, Arabic, and more), with browser-based detection and a manual override.
> - Replies usually follow the language you write in, but **edge cases** (mixed languages, very short prompts) may still need tuning.

---

## ✨ Core Features

- **Multi-model AI**
  - **Groq:** Llama 4 Scout (top multimodal pick), Llama 3.3 70B, Llama 3.1 8B instant.
  - **Automatic routing** may pick a model by task and settings when available.
  - **Optional (deployment-dependent):** OpenRouter / DeepSeek–style providers for coding or frontier models — only if the operator configured them.
- **Response styles:** Brief / Standard / Deep.
- **Conversation UX:** Multiple **chat sessions** in the sidebar, **streaming** replies, long context with sensible limits, follow-ups like “continue” or “more detail” when context allows.
- **Focus modes:** General, technical analysis, copywriting, coding — plus **user profile** (goal, level, tone) and options such as **step-by-step planner**, **ultra-simple** answers, and **thinking mode** (short internal plan / summary before the reply, when enabled in the UI).
- **Web augmentation:** Search with **source links** (e.g. Tavily-backed where configured).
- **URL analysis:** Paste a link to summarize or extract information; **results depend on the site** (paywalls, bot blocking, heavy JavaScript pages may limit what is read).
- **File support:** Text, Markdown, JSON, CSV, Excel, PDF, DOCX, images, and more — within upload/size limits of the deployment.
- **Image understanding:** Ask questions about uploaded images.
- **Image create/edit:** Only if that capability is **turned on** for your instance (depends on server configuration).
- **Persistent chat history** tied to your account (e.g. Supabase on the hosted app), including **per-session threads** in the sidebar.
- **Optional “saved snippets” knowledge:** when the backend supports it, some uploaded content can be stored for **you** and reused as context later (if you don’t see it, that storage is not enabled on this deployment).
- **Same feature tier for registered users** on this app: after sign-in you get the full model / tool options the operator turned on (there is no separate “free vs paid” split inside the UI here).
- **BI tools:** Upload CSV/XLSX and open an interactive **Plotly** dashboard.
- **Authentication:** Login / registration so history can sync across devices.
- **Privacy & legal:** A dedicated **in-app** page (summary policy, session/cookies notice, third-party services in general — not a substitute for personalized legal advice).
- **Polish:** Gemini-like **starting screen**, **clean/focus** UI option, and bundled **CSS/JS** helpers — e.g. **Ctrl/Cmd+Enter** to send, **/** to focus the chat box, **Ctrl/Cmd+K** for chat search, **Esc** to close overlays, **copy** buttons on code blocks, smooth scroll, and a simple **offline** hint when the browser loses connectivity.

---

## 🧠 Product Highlights

- Clean starting experience before the first message.
- **Guardrails** for simple prompts (greetings, date/time, basic math, “what model am I on”, competitor comparisons, etc.) to reduce shallow or misleading answers.
- **Self-knowledge** about MineAI vs the underlying LLM when you ask “what are you?”.
- Optional **quality / safety scaffolding** in the backend (sanitization, retries, checks) — invisible to you until something fails gracefully.

---

## 🛠️ Tech Stack (high level)

| Layer | Technology |
|---|---|
| Frontend | Streamlit |
| UX | Custom CSS/JS (`static/` assets when enabled) |
| Primary AI | Groq (Llama 4 Scout, 3.3 70B, 3.1 8B) |
| Optional AI | OpenRouter / DeepSeek (OpenAI-compatible) if configured; optional **OpenAI** image APIs if configured |
| Vision | Multimodal / vision path via configured Groq (or equivalent) models |
| Web & URLs | Tavily (+ in-app fetch / fallbacks) |
| Database | Supabase (PostgreSQL) |
| Charts | Plotly |
| Hosting | Streamlit Cloud (typical) |

---

## ⚠️ Limitations & errors (read this)

AI output can be **wrong**, incomplete, or **confidently incorrect**. MineAI is **not** a replacement for teachers, doctors, lawyers, or financial advisors — verify anything critical with official sources or qualified people.

- **Facts and dates** may be outdated unless a fresh web pass succeeded.
- **Web and URLs** are not proof of truth; links may fail or return partial content.
- **Large or unusual files** may be rejected or only partially read (uploads are capped at **about 25 MB per file** in the app).
- **Generated code** should always be run and tested locally.
- **Service availability** depends on network, maintenance, and provider limits — temporary errors or empty replies can happen.

**Do not paste** passwords, API keys, full government/health identifiers, or other highly sensitive secrets into chat. Treat the chat as a **productivity tool**, not a vault.

---

## 🚀 Try It

👉 [mineai-teach.streamlit.app](https://mineai-teach.streamlit.app)

Create a free account (if required) and start chatting.

---

## 📬 Feedback & contact

There is **no public GitHub workflow** assumed here. For suggestions or problems, use whatever **contact or support channel** the service operator publishes next to the app (if any).

---

## 📄 License

This project is **closed source**. All rights reserved.

---

## 🇮🇹 Note in italiano (utenti Streamlit)

Questa parte ripete in italiano le **avvertenze** più importanti; le funzioni sono descritte nelle sezioni in inglese sopra.

**Cosa aspettarti:** l’intelligenza artificiale può **sbagliare** o inventare dettagli. Per voti, salute, leggi e soldi chiedi sempre a persone o fonti ufficiali. Date, prezzi e notizie possono essere vecchi o imprecisi. Siti e ricerche sul web non garantiscono la verità. File molto grandi possono essere rifiutati o letti in parte (limite indicativo **~25 MB** per allegato). Il codice generato va **provato**. Lingua e tono a volte non coincidono con le aspettative. Il servizio può avere interruzioni temporanee.

**Dati sensibili:** non inserire in chat password, chiavi segrete, dati sanitari o altre informazioni riservate.

**Privacy e condizioni:** consulta la sezione **Privacy e note legali** dentro l’app; l’uso del servizio è così com’è (`as is`), secondo quanto indicato lì e dai canali pubblici del gestore, se presenti.

**Extra (se li vedi in interfaccia):** modalità **thinking** (riassunto del “pensiero” prima della risposta), **knowledge** persistente sui tuoi snippet solo se il database del servizio lo supporta; dopo il login di solito hai tutte le opzioni modello/strumenti attive su questa istanza, senza livelli separati in app.
