# 📰 News Research Tool using LangChain

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![LangChain](https://img.shields.io/badge/LangChain-Latest-green.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.0+-red.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

An AI-powered research assistant that answers user queries based on online news articles using **Retrieval-Augmented Generation (RAG)**. This tool processes news URLs, creates embeddings, and provides accurate answers with source citations.

![News Research Tool Demo](https://github.com/user-attachments/assets/985526f8-93c2-46ec-b91a-d3dcdd945d22)

## 🌟 Features

- **Multi-URL Processing**: Analyze up to 3 news article URLs simultaneously
- **RAG Implementation**: Uses LangChain's Retrieval-Augmented Generation for accurate responses
- **Source Citations**: Every answer includes source references for verification
- **FAISS Vector Store**: Fast similarity search with Facebook AI Similarity Search
- **Streamlit UI**: Clean, interactive web interface
- **Persistent Storage**: Saves embeddings for quick subsequent queries

## 🛠️ Tech Stack

- **LangChain**: LLM orchestration and RAG pipeline
- **OpenAI GPT**: Language model for answer generation
- **FAISS**: Vector database for semantic search
- **Streamlit**: Web application framework
- **Python 3.8+**: Core programming language

## 📋 Prerequisites

- Python 3.8 or higher
- OpenAI API key ([Get one here](https://platform.openai.com/api-keys))
- pip package manager

## 🚀 Installation

1. **Clone the repository**
```bash
git clone https://github.com/Yuvraj6223/News-Research-Tool-using-langchain.git
cd News-Research-Tool-using-langchain
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables**

Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

## 💻 Usage

1. **Run the Streamlit app**
```bash
streamlit run main.py
```

2. **Open your browser** to `http://localhost:8501`

3. **Enter news article URLs** in the sidebar (up to 3 URLs)

4. **Click "Process URLs"** to analyze the articles

5. **Ask questions** in the text input field

6. **Get answers** with source citations

## 📖 How It Works

```
┌─────────────┐
│  News URLs  │
└──────┬──────┘
       │
       ▼
┌─────────────────┐
│ URL Loader      │  Load content from URLs
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ Text Splitter   │  Chunk documents
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ OpenAI          │  Create embeddings
│ Embeddings      │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ FAISS Vector    │  Store & index
│ Store           │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ User Query      │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ Retrieval QA    │  Find relevant chunks
│ Chain           │  Generate answer
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ Answer +        │
│ Sources         │
└─────────────────┘
```

## 🔧 Configuration

### Adjustable Parameters in `main.py`:

```python
# LLM settings
llm = OpenAI(
    temperature=0.9,  # Creativity (0.0-1.0)
    max_tokens=500    # Response length
)

# Text splitting
text_splitter = RecursiveCharacterTextSplitter(
    separators=['\n\n', '\n', '.', ','],
    chunk_size=1000   # Characters per chunk
)
```

## 📁 Project Structure

```
News-Research-Tool-using-langchain/
│
├── main.py                    # Main Streamlit application
├── requirements.txt           # Python dependencies
├── .env                       # Environment variables (not in repo)
├── .gitignore                # Git ignore rules
├── LICENSE                    # MIT License
└── README.md                  # This file
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangChain](https://github.com/langchain-ai/langchain) for the RAG framework
- [OpenAI](https://openai.com/) for GPT models
- [Streamlit](https://streamlit.io/) for the web framework
- [FAISS](https://github.com/facebookresearch/faiss) for vector search

## 📧 Contact

**Yuvraj V A** - [yuvrajva09@gmail.com](mailto:yuvrajva09@gmail.com)

Project Link: [https://github.com/Yuvraj6223/News-Research-Tool-using-langchain](https://github.com/Yuvraj6223/News-Research-Tool-using-langchain)

---

⭐ If you find this project helpful, please consider giving it a star!