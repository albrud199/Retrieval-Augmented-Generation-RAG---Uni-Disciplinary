# 📚 Retrieval-Augmented Generation (RAG) for University Disciplinary Code

> **Ask questions about university rules — get accurate answers with exact source citations. No guessing, no hallucinations.**

![RAG Pipeline](https://img.shields.io/badge/LLM-Gemma_2B-8A2BE2?logo=huggingface)
![Vector DB](https://img.shields.io/badge/VectorDB-ChromaDB-44CC11)
![Framework](https://img.shields.io/badge/Framework-LangChain_|_LangGraph-0066CC)
![UI](https://img.shields.io/badge/UI-Gradio-EE3377)

## 🔍 What It Does

This project builds an AI assistant that answers questions about university disciplinary policies using **Retrieval-Augmented Generation (RAG)**. Instead of guessing or making up information, it:

✅ Finds **exact relevant rules** from the official PDF document  
✅ Cites **specific sections/clauses** used to answer your question  
✅ Generates answers **strictly from retrieved text** — never invents facts  

### Example Interaction
> **User asks:**  
> *"What are 'unfair or illegal means' in examinations?"*
>
> **System responds:**  
> *"According to Section 5.2 of the EWU Disciplinary Code, unfair or illegal means include:  
> (a) Bringing unauthorized materials into the examination hall  
> (b) Copying from another student's answer script  
> (c) Using programmable calculators or mobile phones  
> (d) Communicating with other students during examination"*  
>   
> *Source: Section 5, Clause 5.2*

---

## ⚙️ How It Works (Simple 4-Step Pipeline)

```mermaid
flowchart TD
    A[PDF Document] --> B[Extract & Clean Text]
    B --> C[Split into Sections/Clauses]
    C --> D[Convert to Embeddings<br><small>“Text Fingerprints”</small>]
    D --> E[Store in Vector DB<br>ChromaDB]
    F[User Question] --> G[Semantic Search<br>Find 4 Relevant Rules]
    E --> G
    G --> H[AI Generates Answer<br><small>Using ONLY Retrieved Text</small>]
    H --> I[Show Answer + Sources]
