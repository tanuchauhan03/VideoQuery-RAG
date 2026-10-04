# 🎥 VideoQuery – AI-Powered Video Intelligence System

VideoQuery is an AI-powered video intelligence system that uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from a video's transcript and generate context-aware answers using an LLM.

The project combines **LangChain, Hugging Face, FAISS, NLP, and Generative AI** to build an end-to-end RAG pipeline.

---

## 🚀 How It Works

The system follows these steps:

```text
YouTube Video
      ↓
Transcript Extraction
      ↓
Text Splitting
      ↓
Hugging Face Embeddings
      ↓
FAISS Vector Store
      ↓
Similarity Search / Retriever
      ↓
Relevant Context
      ↓
Dynamic Prompt
      ↓
Hugging Face LLM
      ↓
Final Answer

🔍 Key Features
Extracts transcripts from YouTube videos
Splits transcripts into smaller meaningful chunks
Generates semantic embeddings using Hugging Face
Stores embeddings in a FAISS vector database
Retrieves the most relevant transcript chunks using similarity search
Uses retrieved context to augment the prompt
Generates context-aware answers using a Hugging Face LLM
Uses LangChain to connect the complete RAG pipeline
Answers questions based on the available video transcript context

🧠 RAG Pipeline
1. Transcript Extraction
The transcript of the selected YouTube video is extracted using:

youtube-transcript-api
2. Text Splitting
The transcript is divided into smaller chunks using:
RecursiveCharacterTextSplitter
Chunk size: 1000
Chunk overlap: 200
The overlap helps preserve context between consecutive chunks.

3. Embeddings
The text chunks are converted into numerical vector representations using:
Embedding Model: BAAI/bge-small-en-v1.5
The embeddings are generated through the Hugging Face Inference API.

4. Vector Store
The generated embeddings are stored in:
FAISS (Facebook AI Similarity Search)
FAISS allows efficient similarity-based retrieval of relevant transcript chunks.

5. Retrieval
For a user's question, the retriever searches the FAISS vector store and retrieves the most relevant chunks.
The system currently retrieves the top 4 relevant chunks.

6. Augmentation
The retrieved transcript context is combined with the user's question using a dynamic prompt.
The prompt instructs the model to answer using the provided transcript context.

7. Generation
The retrieved context is passed to a Hugging Face LLM to generate the final response.
LLM: Qwen/Qwen2.5-Coder-3B-Instruct
The model is accessed through the Hugging Face Inference API, so the model does not need to be downloaded and run locally.

🛠️ Tech Stack
Technology	Purpose
Python	Programming language
LangChain	RAG pipeline and orchestration
Hugging Face	Embeddings and LLM inference
BAAI/bge-small-en-v1.5	Text embeddings
Qwen/Qwen2.5-Coder-3B-Instruct	LLM
FAISS	Vector database / similarity search
YouTube Transcript API	Transcript extraction
NLP	Text processing
RAG	Retrieval-Augmented Generation
Google Colab	Development environment

📁 Project Structure
VideoQuery-RAG/
│
├── rag-using-langchain.ipynb
├── README.md
└── requirements.txt
🔑 Environment Setup

This project uses the Hugging Face API.
Create a Hugging Face access token and store it securely as:
HF_TOKEN
Do not hard-code your API token in the notebook or upload it to GitHub.
For Google Colab, the token can be stored using Colab Secrets.

▶️ Running the Project
Clone the repository.
git clone https://github.com/tanuchauhan03/VideoQuery-RAG.git
Open the notebook:
rag-using-langchain.ipynb
Add your Hugging Face API token securely.
Install the required dependencies.
Run the notebook cells sequentially.
Enter a question related to the video transcript.

💡 Example Questions
You can ask questions such as:
What is DeepMind?
Can you summarize the video?
What topics are discussed in the video?
Is nuclear fusion discussed in the video?
What was discussed about artificial intelligence?
The system retrieves relevant transcript sections before generating the answer.

🎯 Learning Outcomes

Through this project, I explored and implemented:

Large Language Models (LLMs)
Retrieval-Augmented Generation (RAG)
LangChain
Prompt Engineering
Text Chunking
Embeddings
Semantic Search
Vector Databases
FAISS
Retrievers
Hugging Face Inference API
LCEL / LangChain chains
🔮 Future Improvements

Some possible improvements include:
Support for multiple videos
Metadata-based filtering
Better conversational memory
Improved retrieval strategies
Hybrid search
Streaming responses
User interface for easier interaction
Deployment as a web application
