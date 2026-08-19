# AI-evaluator

# AI Document Analyst

An AI-powered document analysis application that uses **Retrieval-Augmented Generation (RAG)** to let users interact with their documents through natural-language questions. The application combines **LangChain, OpenAI, FAISS, and Streamlit** to process uploaded documents, retrieve relevant information, and generate context-aware responses.

The system supports both general AI conversations and document-based question answering, making it useful for analyzing reports, research papers, business documents, notes, and other unstructured content.

## Features

* **AI Chat Mode**: Interact with an OpenAI-powered assistant for general questions.
* **Document Q&A**: Upload documents and ask natural-language questions about their content.
* **RAG Pipeline**: Uses document chunking, embeddings, vector search, and LLM-based generation to provide context-aware answers.
* **Multiple File Formats**: Supports PDF, TXT, CSV, DOCX, Markdown, HTML, and JSON files.
* **Semantic Retrieval**: Uses FAISS vector search to retrieve relevant document sections before generating responses.
* **Conversational History**: Maintains previous messages to support multi-turn conversations.
* **Document Processing**: Automatically loads and processes uploaded files before indexing them for retrieval.
* **Debugging Information**: Provides document/chunk information and retrieved context to help understand the retrieval process.
* **Streamlit Interface**: Provides a lightweight browser-based interface for interacting with the AI system.
* **Error Handling**: Provides feedback for common document-processing and API configuration issues.

## Technology Stack

* **Python**
* **Streamlit**
* **LangChain**
* **OpenAI API**
* **FAISS**
* **PyPDF**
* **Unstructured**
* **DOCX2TXT**

## How It Works

The application follows a Retrieval-Augmented Generation workflow:

```text
User uploads document
        ↓
Document loading
        ↓
Text extraction
        ↓
Document chunking
        ↓
OpenAI embeddings
        ↓
FAISS vector store
        ↓
User asks a question
        ↓
Semantic similarity search
        ↓
Relevant document chunks retrieved
        ↓
OpenAI LLM
        ↓
Context-aware response
```

This approach allows the application to retrieve information from the uploaded documents before generating an answer instead of relying solely on the model's existing knowledge.

## Prerequisites

### Python

Python 3.8 or higher.

### OpenAI API Key

An OpenAI API key is required for the language model and embedding functionality.

Create an API key through the OpenAI platform and keep it private. Do not commit API keys or other credentials to the repository.

### Poppler

Poppler is recommended when working with PDF documents.

**Windows**

Install Poppler for Windows and add its `bin` directory to your system PATH.

**macOS**

```bash
brew install poppler
```

**Linux**

```bash
sudo apt update
sudo apt install poppler-utils
```

Verify the installation:

```bash
pdftotext -v
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/AI-evaluator.git
cd AI-evaluator
```

### 2. Install dependencies

```bash
pip install streamlit langchain langchain-openai langchain-community langchain-text-splitters langchainhub faiss-cpu openai pypdf docx2txt unstructured
```

For PDF processing:

```bash
pip install "unstructured[pdf]"
```

### 3. Run the application

```bash
streamlit run chatbot.py
```

The application will be available through the local Streamlit URL displayed in the terminal.

## Usage

### General AI Chat

1. Open the application.
2. Provide your OpenAI API key through the application interface.
3. Enter a question in the chat interface.
4. The AI assistant generates a response while maintaining conversational context.

Example:

```text
User:
What is Retrieval-Augmented Generation?

AI:
RAG is an architecture that combines information retrieval
with language generation to provide responses grounded in
external sources.
```

### Document Analysis

1. Upload a supported document.
2. Start the document indexing process.
3. The application processes and splits the document into smaller sections.
4. The sections are converted into vector embeddings.
5. The embeddings are stored in a FAISS vector index.
6. Ask questions about the uploaded document.
7. The system retrieves relevant sections and provides them to the language model as context.

Example:

```text
User:
What are the main conclusions of this report?

AI:
The report identifies three primary conclusions...
```

## Example Use Cases

The application can be used for:

* Research paper analysis
* Business report analysis
* Course material Q&A
* Technical documentation search
* Policy and procedure review
* Meeting document analysis
* Internal knowledge-base exploration

## Project Structure

```text
AI-evaluator/
│
├── chatbot.py
├── pyproject.toml
└── README.md
```

### `chatbot.py`

Contains the Streamlit application, document processing workflow, RAG pipeline, vector retrieval, conversational logic, and AI interaction.

### `pyproject.toml`

Contains project configuration and Python dependency information.

### `README.md`

Project documentation, setup instructions, architecture, and usage information.

## RAG Architecture

The application uses the following core components:

**Document Loader**

Loads and extracts text from uploaded files.

**Text Splitter**

Breaks large documents into smaller chunks that can be efficiently retrieved.

**Embeddings**

Converts document chunks into numerical vector representations.

**FAISS**

Stores and searches the generated vectors to identify content relevant to a user's question.

**Large Language Model**

Uses the retrieved document context to generate a natural-language response.

## Future Enhancements

Potential improvements include:

* Document summarization
* Automatic question generation
* Source citations for generated answers
* Multi-document comparison
* Persistent vector databases
* Local LLM support
* Improved document preview
* Conversation export
* User authentication
* Cloud deployment using Azure
* Integration with enterprise knowledge bases

## Acknowledgments

This project builds upon open-source technologies including **LangChain, Streamlit, FAISS, and OpenAI**.

The application was developed as a learning project focused on understanding **Retrieval-Augmented Generation, vector search, document processing, and LLM-powered applications**.
