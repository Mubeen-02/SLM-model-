# **Small Language Model for Question Answering**

## **Project Overview**  
This project implements a **Small Language Model (SLM)** designed for **question answering (QA) based on a given book**. It processes a **PDF or text file**, retrieves the most relevant content, and generates precise answers using a pre-trained transformer model.

---

## **Features**  
- Extracts text from **PDF** and **TXT** files  
- Splits text into smaller chunks for efficient retrieval  
- Converts text into embeddings using **Sentence-BERT**  
- Stores embeddings in **FAISS** for fast similarity search  
- Retrieves the most relevant context for answering  
- Uses a **pre-trained QA model** for generating answers  

---

## **Project Structure**  
The project is organized as follows:  

```
📁 SLM_QA_Project  
 ┣ 📂 data/                
 ┣ 📂 models/             
 ┣ 📂 notebooks/          
 ┣ 📜 main.py              
 ┣ 📜 requirements.txt     
 ┣ 📜 README.md            
 ┗ 📜 LICENSE              
```

---

## **Installation and Setup**  

### **Step 1: Install Dependencies**  
Ensure the required libraries are installed. The dependencies include:  

- **torch**  
- **transformers**  
- **sentence-transformers**  
- **faiss-cpu**  
- **pdfplumber**  

Use the following command to install them:  

```
pip install torch transformers sentence-transformers faiss-cpu pdfplumber
```

### **Step 2: Upload the Book File**  
Place the book file (PDF or TXT) in the **data/** directory.

### **Step 3: Run the Model**  
Execute the **main.py** script:  

```
python main.py
```

### **Step 4: Ask a Question**  
Once the model is running, input a question to retrieve an answer based on the provided book.

---

## **Model Architecture and Approach**  

### **Text Processing and Preprocessing**  
- The text is extracted from **PDF** or **TXT** files.  
- It is divided into smaller segments for improved retrieval.  

### **Embedding and Retrieval**  
- The **all-MiniLM-L6-v2** model from **Sentence-Transformers** is used to generate embeddings.  
- The embeddings are stored in a **FAISS** index for fast similarity searches.  
- Given a query, **relevant text chunks** are retrieved using similarity matching.  

### **Question Answering**  
- The retrieved text is passed to a **pre-trained transformer model** for QA.  
- The model used is **deepset/roberta-base-squad2**, optimized for extractive question answering.  

---

## **Observations and Key Learnings**  
- **Chunk size selection is critical** for effective information retrieval.  
- **FAISS indexing significantly improves retrieval speed**, making searches efficient.  
- **Pre-trained models work well but may require fine-tuning** for domain-specific documents.  
- **Performance depends on document structure**—well-formatted text improves accuracy.  

---

## **Future Enhancements**  
- Implement **BM25 hybrid search** for better retrieval accuracy.  
- Fine-tune a QA model on specific book categories.  
- Develop a web-based **interactive interface** for better usability.  
- Optimize text processing for handling **large documents efficiently**.  

---
