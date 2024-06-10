---
title: "Web Novel Recommendation System"
excerpt: "Leveraging Facebook AI Similarity Search (FAISS) for advanced recommendation capabilities <br/><img src='/images/recommend.png'>"
collection: portfolio
---

I developed a Web Novel Recommendation System by scraping data from various websites, resulting in a dataset of 15,000 books (including Name, Author, Genres, Tags, and Descriptions). 

**Key Steps:**
1. **Data Preprocessing:** Cleaned and prepared the dataset for analysis.<br/>
2. **Sentence Embeddings:** Utilized [All MiniLM L6 v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) from Hugging Face for generating sentence embeddings.<br/>
3. **FAISS Integration:** Incorporated the embeddings into Facebook AI Similarity Search (FAISS) for efficient similarity search.<br/>
4. **API Development:** Created endpoints and data fetching mechanisms using FASTAPI.<br/>
5. **Deployment:** Deployed the project on Hugging Face Spaces using Docker.<br/>

**Live Project:** [Web Novel Recommendation System](https://huggingface.co/spaces/Dragneel/webnovel-recommend)

**Image:**
<img src='/images/recommend.png'>
