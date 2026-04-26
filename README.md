# 🧠 PaperBrain

> Upload any PDF. Ask anything. Get answers grounded in your document — powered by RAG + Groq.

PaperBrain is an Android app that lets you chat with your PDFs using **Retrieval-Augmented Generation (RAG)**. Upload a document, ask questions in natural language, and get accurate, context-aware answers — not hallucinations.

---

## 🔍 How It Works

```
📄 PDF Upload
     ↓
🔪 Text Chunking
     ↓
🧮 Embedding Generation
     ↓
🗄️ Vector Store (similarity search)
     ↓
🔎 Relevant Chunks Retrieved on Query
     ↓
🤖 Groq LLM (context + query → answer)
     ↓
💬 Response shown in chat UI
```

---

## ✨ Features

- 📤 Upload PDF documents directly from your Android device
- 💬 Chat interface to ask questions about your document
- 🔎 RAG pipeline — answers sourced from actual document content
- ⚡ Groq-powered inference for blazing fast responses
- 🧠 Context-aware — maintains conversation history
- 🚫 No hallucinations — grounded responses only

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Mobile Frontend | React Native + Expo 54 |
| Language | TypeScript |
| Navigation | Expo Router (file-based) |
| UI | Expo Vector Icons, React Navigation |
| Animations | react-native-reanimated |
| LLM Backend | Groq API |
| RAG Pipeline | Python backend (see backend repo) |
| Embeddings | Sentence Transformers / OpenAI Embeddings |
| Vector Store | FAISS / ChromaDB |

> **Note:** This repo is the **React Native frontend only**. The RAG + Groq backend is a separate Python service.

---

## 🚀 Getting Started

### Prerequisites

- Node.js ≥ 18
- npm or yarn
- [Expo Go](https://expo.dev/go) on Android **or** Android Studio emulator
- Backend server running (see [Backend Setup](#backend-setup))

### Frontend Setup

```bash
# Clone the repo
git clone https://github.com/Krishna-Vitthal/PaperBrain.git
cd PaperBrain

# Install dependencies
npm install

# Start the dev server
npx expo start
```

Scan the QR code with **Expo Go**, or press `a` for the Android emulator.

### Backend Setup

The backend handles PDF parsing, chunking, embedding, vector search, and Groq inference.

```bash
# Install Python dependencies
pip install -r requirements.txt

# Add your Groq API key
echo "GROQ_API_KEY=your_key_here" > .env

# Run the server
python app.py
```

> Update the API base URL in the frontend constants to point to your running backend.

---

## 📁 Project Structure

```
PaperBrain/
├── app/
│   ├── (tabs)/
│   │   └── _layout.tsx       # Tab navigator
│   ├── index.tsx             # Home / Upload screen
│   ├── chat.tsx              # Chat interface
│   └── _layout.tsx           # Root layout
├── components/               # Reusable UI components
├── constants/                # API URLs, config
├── hooks/                    # Custom hooks
└── assets/
    └── images/
```

---

## 📦 Scripts

```bash
npm start          # Start Expo dev server
npm run android    # Open on Android emulator
npm run web        # Open in browser
npm run lint       # Run ESLint
```

---

## 🔐 Environment Variables

Create a `.env` file in the backend directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Never commit API keys to the repo.

---

## 🗺️ Roadmap

- [ ] Multi-PDF support
- [ ] Chat history persistence
- [ ] Highlight source chunks in the PDF
- [ ] Document management screen
- [ ] Local embedding option (on-device)

---

## 👤 Author

**Vitthal Krishna**
- GitHub: [@Krishna-Vitthal](https://github.com/Krishna-Vitthal)
- B.Tech CSE (Systems Engineering), KIIT University
