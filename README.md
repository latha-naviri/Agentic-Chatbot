# End to End Project Agentic AI Chatbot

# 🤖 Agentic AI Chatbot Suite

A multi-usecase AI application built with **LangGraph** and **Streamlit**, featuring intelligent chatbots and an AI news summarizer powered by state-of-the-art LLMs.

---
## 🎓 About This Project
Built while learning Agentic AI concepts including LangGraph agent orchestration, tool calling, and multi-agent workflows.
Developed independently with personal modifications and debugging through the build process.

## 🚀 Features

### 1. 💬 Basic Chatbot
A conversational AI chatbot powered by LLMs for general purpose question answering.

### 2. 🔍 Chatbot with Web Search
An AI chatbot enhanced with **Tavily Search** tool — can search the internet in real time to answer questions that require current information.

### 3. 📰 AI News Summarizer
Fetches and summarizes the latest **Artificial Intelligence news** from India and globally.
- Select frequency: **Daily / Weekly / Monthly**
- Automatically fetches relevant AI news using Tavily
- Summarizes using LLM
- Saves results as a **Markdown (.md) file**

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat&logo=python)
![LangChain](https://img.shields.io/badge/LangChain-0.3+-green?style=flat)
![LangGraph](https://img.shields.io/badge/LangGraph-latest-orange?style=flat)
![Streamlit](https://img.shields.io/badge/Streamlit-latest-red?style=flat&logo=streamlit)
![Tavily](https://img.shields.io/badge/Tavily-Search-purple?style=flat)

| Technology | Purpose |
|---|---|
| **LangGraph** | Agent graph orchestration |
| **LangChain** | LLM framework and tool integration |
| **Streamlit** | Frontend UI |
| **Tavily Search** | Real-time web search tool |
| **Groq / Gemini** | LLM inference |
| **Python** | Core programming language |
| **uv** | Package management |

---

## 🏗️ Architecture

```
User (Streamlit UI)
        ↓
   Dropdown Selection
        ↓
┌───────────────────────────────────────┐
│           LangGraph Agent             │
│                                       │
│  ┌─────────┐  ┌──────────────────┐   │
│  │  Basic  │  │ Chatbot + Tavily │   │
│  │Chatbot  │  │   Web Search     │   │
│  └─────────┘  └──────────────────┘   │
│                                       │
│  ┌──────────────────────────────┐    │
│  │      AI News Summarizer      │    │
│  │  Tavily → LLM → .md file    │    │
│  └──────────────────────────────┘    │
└───────────────────────────────────────┘
```

---

## ⚙️ Installation

### Prerequisites
- Python 3.10+
- [uv](https://docs.astral.sh/uv/) package manager
- API Keys for Groq/Gemini and Tavily

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/latha-naviri/Agentic-Chatbot.git
cd Agentic-Chatbot

# 2. Install dependencies using uv
uv sync

# 3. Set up environment variables
cp .env.example .env
# Add your API keys to .env file
```

### Environment Variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
GOOGLE_API_KEY=your_google_api_key_here  # if using Gemini
```

---

## ▶️ Running the App

```bash
uv run streamlit run app.py
```

Then open your browser at `http://localhost:8501`

---

## 📖 How to Use

### Basic Chatbot
1. Select **"Basic Chatbot"** from dropdown
2. Type your message
3. Get AI response

### Chatbot with Web Search
1. Select **"Chatbot with Tavily"** from dropdown
2. Ask anything that needs current information
3. Agent searches the web and responds with real-time data

### AI News Summarizer
1. Select **"AI News"** from dropdown
2. Choose frequency: **Daily / Weekly / Monthly**
3. Click to fetch news
4. View summarized AI news
5. Summary is saved as a `.md` file automatically

---

## 📁 Project Structure

```
Agentic-Chatbot/
├── app.py                         # Entry point
├── pyproject.toml                  # Dependencies (uv)
├── uv.lock                         # Lock file
├── .env                            # API Keys (not committed)
├── .gitignore
└── src/
    └── langgraphagenticai/
        ├── main.py                 # App entry (Streamlit)
        ├── graph/
        │   └── graph_builder.py    # LangGraph graph setup
        ├── LLMs/
        │   └── groqllm.py          # LLM initialization
        ├── nodes/
        │   ├── ai_news_node.py         # AI News summarizer
        │   ├── basic_chatbot_node.py   # Basic chatbot
        │   └── chatbot_with_tavily_node.py  # Chatbot + web search
        ├── state/
        │   └── state.py            # LangGraph state definition
        ├── tools/
        │   └── search_tool.py      # Tavily search tool
        └── ui/
            ├── uiconfigfile.ini    # UI configuration
            ├── uiconfigfile.py     # UI config loader
            └── streamlitui/
                ├── display_result.py   # Result display logic
                └── loadui.py           # Streamlit UI loader
```

---

## 🔑 Getting API Keys

| Service | Link |
|---|---|
| Groq (Free) | [console.groq.com](https://console.groq.com) |
| Tavily (Free tier) | [tavily.com](https://tavily.com) |
| Google Gemini (Free) | [aistudio.google.com](https://aistudio.google.com) |

---

## 🎓 Learning Outcomes

- Building **LangGraph** agent workflows
- Integrating **real-time web search** with AI agents
- Creating **multi-usecase AI applications**
- **Streamlit** frontend for AI apps
- Working with **LLM tool calling**
- Managing Python projects with **uv**
