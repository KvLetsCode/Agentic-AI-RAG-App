Agentic AI RAG Project

A Retrieval-Augmented Generation (RAG) AI project using Streamlit frontend, Google Gemini LLM, and multiple tools for enhanced responses.

🚀 Features

Streamlit Chat Interface: Interactive chat with streaming AI responses.

LLM Integration: Uses Google Generative AI (gemini-2.5-flash) for natural language generation.

Tools Support: Supports multiple tools like:

Calculator

DuckDuckGo Search

Any custom tool you define

RAG Capability: Connects to your database to provide context-aware answers.

Secrets Management: Supports .streamlit/secrets.toml or environment variables for API keys.

Real-time Streaming: Displays token-by-token AI responses in the chat.

Multi-thread Support: Handles multiple conversation threads automatically.

🛠️ Technologies Used

Python 3.13

Streamlit 1.50+

LangChain

LangGraph

Google Generative AI (Gemini)

DuckDuckGo Search (ddgs)

Watchdog / OS integration for file monitoring

⚡ Installation

Clone the repository:

git clone https://github.com/yourusername/agentic-ai-rag-app.git
cd agentic-ai-rag-app


Create and activate a virtual environment:

python3 -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate      # Windows


Install dependencies:

pip install -r requirements.txt


Add API keys in Streamlit secrets:

Create .streamlit/secrets.toml:

GOOGLE_API_KEY = "your_google_api_key"


Or use environment variables:

export GOOGLE_API_KEY="your_google_api_key"   # Linux/macOS
set GOOGLE_API_KEY="your_google_api_key"      # Windows

📝 Usage

Run the Streamlit app:

streamlit run streamlit_frontend.py


Open the web interface at http://localhost:8501

Start chatting with the AI. Features include:

Real-time token streaming

Tool suggestions and execution

Multi-thread conversation handling

Add new tools by creating functions and decorating them with @tool in your tools file.

⚙️ Configuration

LLM Setup: Configure ChatGoogleGenerativeAI in streamlit_frontend.py with your API key.

Tools: Add new tools in the tools module using @tool.

Database / RAG: Configure your retrieval database in langraph_database.py.

File Watcher Issue: To avoid inotify instance limit reached errors, disable Streamlit’s file watcher:

st.set_option("server.fileWatcherType", "none")

📈 Example
User: Calculate 25 * 4
AI: 100

User: Search for latest news about AI
AI: (Uses DuckDuckGo Search tool)
AI: Here are the latest AI news headlines: ...

🧩 Notes

Streamlit is optional for local testing but provides an interactive interface.

Secrets and API keys should never be committed to GitHub.

Supports multiple threads in conversations for persistent chats.

🛡️ Security

Store secrets in .streamlit/secrets.toml or environment variables.

Never commit API keys or .streamlit/secrets.toml to version control.
