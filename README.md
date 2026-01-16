# Agentic RAG Chat Interface

An advanced **Agentic Retrieval-Augmented Generation (RAG)** system built with **LangGraph**, **LangChain**, and **Streamlit**. This project implements a self-correcting agent that can retrieve information from local knowledge bases or the web, evaluate the relevance of the data, and refine its search until it finds a high-quality answer.



## 🚀 Key Features
* **Adaptive Retrieval**: Intelligent routing between local knowledge bases and web search (via Tavily).
* **Self-Correction Loop**: Includes a "Grader" mechanism that evaluates retrieved documents for relevance. If the data is insufficient, the agent automatically rewrites the query for better results.
* **Multi-Model Support**: Configurable to use **Google Gemini 1.5 Flash** or **Groq (Gemma2-9b)** for high-speed inference.
* **Streamlit UI**: A clean, user-friendly chat interface for real-time interaction with the agent.
* **Stateful Workflows**: Built using LangGraph to manage complex agentic logic and decision-making cycles.

## 🛠️ Tech Stack
* **Frameworks**: LangGraph, LangChain.
* **Embeddings**: `all-MiniLM-L6-v2` (HuggingFace) or Google Generative AI Embeddings.
* **Vector Database**: ChromaDB for efficient document retrieval.
* **LLMs**: Google Gemini, Groq (Gemma2).
* **Tools**: Tavily Search API, WebBaseLoader.

## 📋 Prerequisites
Ensure you have the following API keys in a `.env` file in the root directory:
```env
GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
GROQ_API_KEY=your_groq_api_key
LANGCHAIN_API_KEY=your_langchain_api_key
```
## 💻 Setup and Project Details
# 1. Installation & Setup
```env
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
pip install -r requirements.txt
streamlit run app.py
```
# 2. Project Architecture
 The agent workflow follows this logic:
* **ROUTE** -> Decide between Vector Store or Web Search
* **RETRIEVE** -> Fetch relevant context using tools
* **GRADE** -> Check if information is relevant to the question
 
* **REWRITE** -> If irrelevant, transform query and retry
 
* **GENERATE** -> If relevant, produce final answer

# 3. Folder Structure
 ```env
 .
 ├── app.py              # Streamlit UI & Environment Config
 ├── agentic_rag.ipynb   # Core LangGraph Logic & RAG Pipeline
 ├── requirements.txt    # Project Dependencies
 └── .env                # API Keys (Local Only)
 ```
