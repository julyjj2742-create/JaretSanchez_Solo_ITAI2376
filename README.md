# DocuHelp: Intelligent Document Assistant
### ITAI 2376
### Student: Jaret Sanchez (Solo Project)

DocuHelp is an intelligent document‑processing agent that can read a PDF, break it into meaningful chunks, classify its topic, retrieve the most relevant sections, and generate a clean summary using an LLM. The project combines embeddings, vector search, a local ML classifier, and a LangGraph agent to create a simple but effective retrieval‑augmented system.

## Problem and Target User
Many students and professionals work with long PDF documents that are time‑consuming to read and summarize. DocuHelp solves this by automatically extracting text, identifying the document’s topic, retrieving the most relevant sections, and generating a concise summary.

Target users:
- Students reviewing academic PDFs
- Professionals reading reports or policy documents
- Anyone who needs quick, accurate summaries of long documents

## Option Chosen
### Option A — Single Agent  
This matches my Midterm plan (no change).

The agent uses a simple two‑step workflow: retrieve → summarize.

## Architecture Overview
DocuHelp processes a PDF through several stages:

1. Extract text from the PDF
2. Split the text into overlapping chunks
3. Convert chunks into embeddings
4. Store embeddings in a FAISS vector index
5. Classify the document topic using a local ML model
6. Use a LangGraph agent to retrieve relevant chunks
7. Summarize the retrieved content using an LLM

This creates a lightweight retrieval‑augmented system that produces grounded summaries.
### Architecture Diagram
<img width="321" height="1031" alt="architecture" src="https://github.com/user-attachments/assets/39e81ac8-b390-4a4a-96bd-637d22f47f21" />

## Framework and Tools Used
- LangChain – document loaders, text splitting
- LangGraph – agent workflow (retrieve → summarize)
- FAISS – vector store for semantic search
- SentenceTransformers (MiniLM) – embeddings
- scikit‑learn – local AG News classifier
- OpenAI GPT‑4o‑mini – summarization
- Python 3.12
- Google Colab

## Installation Instructions
### Python Version
`Python 3.12+`
### Install Dependencies
`!pip install langchain langgraph faiss-cpu sentence-transformers pypdf python-dotenv openai transformers torch langchain-community langchain-huggingface langchain-openai scikit-learn pandas`
### Environment Variables
`OPENAI_API_KEY=your_key_here`

## How to Run the Agent
Open agent.ipynb in Google Colab and run the cells in order:
1. Install dependencies
2. Enter your OpenAI API key
3. Upload a PDF
4. Let the notebook extract text, embed chunks, classify topic
5. Run the LangGraph agent
6. View the final summary

No command‑line steps required.

## Example Usage
### Example 1
Input PDF: “A Definition of AI”

Output Topic: Business

Summary: A concise explanation of AI capabilities, rationality, and system components.

### Example 2
Input PDF: “Climate Policy Overview”

Output Topic: World News

Summary: Key climate policy goals, international agreements, and environmental challenges.

### Example 3
Input PDF: “Introduction to Neural Networks”

Output Topic: Technology

Summary: Overview of neural network structure, training, and common applications.

## Know Limitations
- The classifier is simple (TF‑IDF + Logistic Regression) and may mislabel niche documents.
- Summaries depend on retrieved chunks; if the PDF is poorly formatted, retrieval may miss key sections.
- Only supports one PDF at a time.
- No user interface — notebook only.
- Requires an OpenAI API key for summarization.

## Demo Video
### Demo video Link: (will be added soon)
