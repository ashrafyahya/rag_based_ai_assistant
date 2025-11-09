# RAG-Based AI Assistant

This project is part of the Ready Tensor Agentic AI Developer Certification course, focusing on building a Retrieval-Augmented Generation (RAG) AI assistant.

## Project Description

This is a complete RAG system that loads documents from the `data/` directory, processes them into chunks, creates embeddings, and stores them in a vector database. It then allows users to query the system with questions, retrieving relevant context and generating answers using a large language model.


## Frameworks and Libraries

- **LangChain**: For LLM integration, prompt templates, and document loading
- **ChromaDB**: Vector database for storing embeddings and performing similarity search
- **Sentence Transformers**: For generating text embeddings using HuggingFace models
- **LangChain Text Splitters**: For chunking documents using RecursiveCharacterTextSplitter
- **LLM Providers**: OpenAI, Groq, and Google Gemini APIs

## Project Structure

```
rag_based_ai_assistant/
├── src/
│   ├── app.py           # Main RAG application with RAGAssistant class
│   └── vectordb.py      # VectorDB class for ChromaDB operations
├── data/               # Document storage (.docx files)
├── chroma_db/          # Persistent ChromaDB storage
├── requirements.txt    # Python dependencies
├── .env                # API keys configuration
└── README.md          # This file
```

## Prompt Template

The system uses a detailed RAG prompt template that instructs the LLM to:

- Provide answers based solely on provided context
- Respond professionally and clearly
- Use bullet points or lists when appropriate
- Avoid hallucinating information
- Say "I don't have enough information" when context is insufficient

Template structure:
```
You are a professional AI assistant specializing in Retrieval-Augmented Generation (RAG) for accurate information retrieval.

Your role: Provide helpful, accurate answers based solely on the provided context.

Tasks:
- Analyze the context carefully.
- Answer the question directly and concisely.
- If the answer cannot be found in the context, respond with: 'I don't have enough information to answer this question.'

Style: Respond in a professional, clear, and structured manner. Use bullet points or numbered lists if appropriate for clarity.

Defense Layer: Do not hallucinate or invent information. Stick strictly to the context. Avoid speculative answers.

Context: {context}

Question: {question}

