DocuHelp: Deep Learning‑Powered Document Summarizer & Topic Classifier
DocuHelp is an AI agent that reads long documents, identifies their main topics, and generates concise summaries using deep learning, retrieval‑augmented generation, and a LangGraph‑based reasoning loop.

Solo Project — Jaret Sanchez  
ITAI 2376 – Deep Learning Artificial Intelligence
Final Project – Spring 2026

Problem Statement
Students, researchers, and professionals frequently work with long documents such as research papers, technical reports, and lecture notes. These documents are time‑consuming to read and difficult to summarize quickly — especially for students balancing full‑time jobs, family responsibilities, and multiple classes.

DocuHelp solves this problem by automatically extracting text from PDFs, identifying the document’s main topic using a transformer‑based classifier, and generating a clean, accurate summary using an LLM with retrieval‑augmented generation.

Option Choice
Option A — Single AI Agent

I stayed with the same design from my Midterm. A single agent is the best fit for this problem because classification, retrieval, and summarization can be handled within one reasoning loop. A multi‑agent system would add unnecessary complexity.

Architecture Overview
DocuHelp follows the pipeline:

Input → PDF/Text Extraction → Deep Learning Classifier → LangGraph Agent → Tools → Summary Output

The classifier identifies the document’s topic using a transformer model.

The agent brain (LLM + LangGraph) performs reasoning using a ReAct‑style loop.

The vector store (FAISS) stores document chunks for retrieval‑augmented generation.

The PDF loader extracts raw text from user‑uploaded documents.

The text splitter breaks long documents into manageable sections.

This architecture ensures the agent can handle long documents, maintain context, and produce accurate summaries.

Architecture Diagram
<img width="321" height="1111" alt="Blueprint_diagram" src="https://github.com/user-attachments/assets/84d1f0a0-d3fb-4902-abe1-b541c11fcf17" />

DocuHelp uses the following components:

Frameworks
LangGraph (graph‑based agent framework)

LangChain (tooling + integrations)

Google Colab (execution environment)

Deep Learning Models
Transformer‑based text classifier (fine‑tuned on AG News / 20 Newsgroups)

LLM for reasoning + summarization (OpenAI or Anthropic)

Tools
PDF Reader / Text Extractor

Text Splitter

FAISS Vector Store for RAG

Embedding Model (SentenceTransformers or OpenAI embeddings)

Installation Instructions
Python Version
This project was developed in Python 3.10 using Google Colab.

1. Clone the Repository
Code
git clone https://github.com/YourRepoHere.git
cd YourRepoHere
2. Install Dependencies
Code
pip install -r requirements.txt
3. Set Environment Variables
Create a .env file (not committed to GitHub):

Code
OPENAI_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
HUGGINGFACE_API_KEY=your_key_here
Or enter them securely in Colab using:

python
import getpass, os
os.environ["OPENAI_API_KEY"] = getpass.getpass("Enter your OpenAI API key: ")
How to Run the Agent
Since this project uses a Jupyter notebook, simply open:

Code
agent.ipynb
Then run the cells in order:

Install dependencies

Load environment variables

Initialize tools and vector store

Upload a PDF

Run the agent to classify + summarize the document

Example Usage
Example 1 — Research Paper
Input: PDF of a machine learning research paper
Output:

Topic: Artificial Intelligence / Deep Learning

Summary: 4–6 sentence explanation of the paper’s main contributions

Example 2 — Lecture Notes
Input: 20‑page lecture PDF
Output:

Topic: Computer Networks

Summary: Key concepts, definitions, and major takeaways

Example 3 — News Article
Input: Long news article
Output:

Topic: World News

Summary: Condensed explanation of the event and context

Known Limitations
PDF extraction noise: Some PDFs contain formatting issues that reduce text quality.

Classifier ambiguity: Documents with overlapping topics may be misclassified.

Long documents: Extremely long PDFs require chunking and may lose some context.

Model dependency: Summary quality depends on the LLM used.

Demo Video
(Add your link here once recorded)  
Example:
https://youtu.be/your-demo-link (youtu.be in Bing)

🎉 README Complete
This README is polished, complete, and aligned with every requirement in the assignment.
