# AI Job Matching using Retrieval-Augmented Generation (RAG)

An intelligent job recommendation system that goes beyond keyword matching by using semantic search and large language models to understand the true context of resumes and job descriptions.

---

## 🚀 Overview

Traditional job portals rely on keyword-based matching, which often leads to irrelevant recommendations and poor personalization. This project implements a **Retrieval-Augmented Generation (RAG)** pipeline to enable **semantic job matching**.

Instead of matching exact words, the system understands the *meaning* of skills and job requirements using embeddings and ranks results intelligently.

---

## 🧠 Problem Statement

Keyword-based systems fail to:
- Capture semantic meaning of skills
- Understand synonyms (e.g., NLP vs Transformers)
- Provide personalized job recommendations

This results in:
- Poor candidate-job alignment
- Irrelevant job suggestions
- Inefficient hiring workflows

---

## 💡 Solution

This project uses a **RAG-based architecture**:
1. Convert resumes and job descriptions into embeddings
2. Store them in a vector database
3. Retrieve top-k semantically similar matches
4. (Optional) Use LLMs to refine ranking and generate explanations

---

## 🏗️ System Architecture
User Query / Resume
↓
Embedding Model (Sentence Transformers)
↓
Vector Database (FAISS)
↓
Top-K Retrieval
↓
LLM Ranking (Optional)
↓
Final Job Recommendations


---

## ⚙️ Tech Stack

- **Language:** Python  
- **ML/NLP:** Sentence Transformers  
- **Vector DB:** FAISS  
- **Backend (optional):** FastAPI  
- **LLM Integration (optional):** OpenAI / Local Models  

---

## 📂 Project Structure
ai-job-matching-rag/
│── backend/
│ ├── main.py
│ ├── embeddings.py
│ ├── retriever.py
│ └── ranker.py
│
│── data/
│ ├── sample_resumes/
│ └── sample_jobs/
│
│── notebooks/
│ └── experiments.ipynb
│
│── requirements.txt
│── README.md


---

## 🔍 How It Works

### 1. Embedding Generation
- Text (resume/job description) is converted into dense vectors using:
  - `all-MiniLM-L6-v2`

### 2. Vector Storage
- Embeddings are stored in FAISS for efficient similarity search

### 3. Retrieval
- Given a query, the system retrieves top-k similar results using cosine similarity

### 4. Ranking (Optional)
- LLM refines ranking and generates contextual explanations

---

## ▶️ How to Run

```bash
# Clone the repository
git clone https://github.com/yourusername/ai-job-matching-rag.git

# Navigate into the project
cd ai-job-matching-rag

# Install dependencies
pip install -r requirements.txt

# Run the application
python backend/main.py

```
## Example Output
Input: "Python Backend Developer"

Top Matches:
1. Backend Engineer (Score: 0.89)
2. API Developer (Score: 0.85)
3. Software Engineer (Score: 0.81)
