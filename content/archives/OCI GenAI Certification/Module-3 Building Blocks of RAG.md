---
Date: 2024-07-24
Project: "[[OCI Gen AI Professional Certification]]"
Deck: "[[OCI GenAI Deck]]"
Flashcards: "[[06-Resources/Decks/OCI GenAI/Module-3 Building Blocks of RAG|Module-3 Building Blocks of RAG]]"
Confidence: Somewhat Confident
tags: 
Review: 
cssclasses:
  - list-cards
  - cards-1-1
  - cards
---
# Building Blocks of RAG

## 1. RAG - Retrieval Augmented Generation
***

> [!info]
> RAG Systems can be considered as an `Architect` and `Internal Designer` pair as the `retrieval` part `searches` and builds the `foundation` like a `architect`, while the `generation` part (the `LLM`) makes the `retrieved` (foundation) part more `appealing` to the `user` like a `internal designer`.

- **RAG:** It is a method for generating text using additional information from an external data source that are up to date or latest.

- RAG models `retrieve documents` and `pass` them to a `seq2seq` model.

### 1.1 RAG Framework
***
- 1.**Retriever**
	- **Function:** `Sources` information from a `large corpus or database`.
	- 
	- **Working:** Uses `retrieval` techniques like `vector search`...
	- 
	- **Purpose:** Provides the `generation` system with contextually relevant, accurate and up-to date `information` that might not be present in the model's pre-trained `knowledge`.
- 2.**Ranker**
	- **Function:** `Evaluates` and `prioritises` the information `retrieved` by the retriever.
	- 
	- **Working:** Uses various algorithms to evaluate the quality of the retrieved content.
	- 
	- **Purpose:** Ensures that the generation system receives is the most `pertinent` and `high-quality` input.
- 3.**Generator**
	- **Function:** Generates `human readable` like text based on the `retrieved` and `ranked` information, along with the users's `original query` it receives.
	- 
	- **Working:** Uses `LLMs` to craft or `generate` human-like text.
	- 
	- **Purpose:** Ensures that the final response is factually accurate, relevant and also coherent and styled typically like human language. 

### 1.2 RAG Techniques
***
- 1.**RAG Sequence**
	- For each input query, the model retrieves a set of `relevant documents or information`.
	- 
	- It then `considers` `all` the documents or `information` `together` to generate a `single, cohesive response` that reflects the combined information.
	- 
	- For example consider I'm studying about a civil war, then first I'll `gather` all the documents related to civil war and then `combine` it together.
- 2.**RAG Tokens**
	- For each `part` of the `response`(can be a sentence or a word), the model `retrieves` relevant `documents`.
	- 
	- The response is constructed `incrementally`, with each part reflecting the information from the documents retrieved for the specific parts.
	- 
	- For example consider I'm journalist writing about a topic, as I'm `writing` the article I keep `referring` for `documents` `incrementally`.

### 1.3 RAG Pipeline
***
![[Module-3 Building Blocks of RAG.png]]

### **1. Ingestion**
- 1. Documents
- 2. Chunks
- 3. Embedding
- 4. Index(DB)

### 2. Retrieval
- 1. User Query
- 2. Index Retrieval
- 3. Top K results

### 3. Generation
- 1. User Query + Top K results
- 2. Response to User

### 1.4 RAG Application Example
***
![[Module-3 Building Blocks of RAG-1.png]]

### 1.5 RAG Evaluation
***
![[Module-3 Building Blocks of RAG-2.png]]

There is a framework called `RAG Triad` that is used to evaluate RAG systems.

- Query -> Context 
	- We need to check for `Context Relevance`: Is the retrieved context relevant to the query?
- Context -> Response 
	- We need to check for `Groundedness`: Is the response supported by the context?
- Response -> Query 
	- We need to check for `Answer Relevance`: Is the answer relevant to the query?


## 2. Vector Databases
***
- LLMs with RAG use an `external database` `specialised` at `storing vectors` called vector databases.

![[Module-3 Building Blocks of RAG-3.png]]

### 2.1 Vectors
***
- A vector is a `sequence of numbers`, called `dimensions` used to `capture important features` of the data.
- `Embeddings` in LLMs are essentially `high-dimensional vectors`.
- Vectors are `generated` using deep learning `embedding models` and represent the `semantic content` of data, `not` the underlying `words` or `pixels`.

### 2.2 Embedding Distance
***
- Dot Product
	- ![[Module-3 Building Blocks of RAG-4.png  | 710x300]]
	- It determines `distance` based on `both` the `direction` and `magnitude` of two vectors.
	- It ranges from `-1 to 1`
		- -1 -> `least similar` and at `opposite directions`.
		-  0 -> `not similar` but in `same directions`.
		-  1 -> `very similar` and in `same directions`.
- Cosine Distance
	- ![[Module-3 Building Blocks of RAG-5.png | 710x300]]
	- It determines `distance` based on `only` the `direction` of the two vectors.
	- It ranges from `0 to 1`
		- 0 -> `similar` & in `same directions`.
		- 1 -> `not similar` & in `different directions`.

### 2.3 Similar Vectors
***
- KNN Search Method
	- KNN can be used to perform vector or `semantic search` to obtain `nearest k vectors` in `embeddings space` to a `query` vector using the `distance` metrics.
	- 
	- KNN for vector search is very `slow` and `computationally expensive` for a `large-scale search`
- ANN Search Methods
	- Usually `ANN methods` such as HNSW, FAISS, Annoy are used to find near-optimal `neighbours` much `faster` than `KNN` searches.
	- 
	- The ANN methods `sacrifice` some `accuracy` for `efficiency` and `speed` on large-scale searches.

### 2.4 Vector DB Workflow
***
- 1.Vectors
	- Embeddings of the documents.
- 2.Indexing
	- One of the ANN methods is used to index the vectors for faster search.
- 3.Vector DB
	- Store the indexes and vectors in the vector DB.
- 4.Querying
	- Search the vector space using search methods based on the query vector.
- 5.Post Processing
	- Is usually the generation part by LLMs.

### 2.5 Vector DBs
***
There are `multiple vector DB`s in the market. The reason the vector DBs are `extensively` used for `RAG systems` because of their:
- Accuracy
- Latency
- Scalability

### 2.6 Role of Vector DBs
***
- Address the hallucination problem inherent to LLMs.
- Augment prompt with enterprise specific content to produce better responses.
- Cheaper than fine-tuning LLMs.
- Real-Time updated knowledge base.
- Cache LLM prompts/responses to improve performance and reduce costs.


## 3. Semantic Search
***
We can do semantic search by:
- Dense Retrieval
- Reranking
- Hybrid Search

### 3.1 Dense Retrieval
***
- Determines top ranking relevant documents by making use of both the query vectors and the vectors in the DB.
- Enables the retrieval system to understand and match based on the contextual similarities between query and documents.

![[Module-3 Building Blocks of RAG-6.png]]

### 3.2 ReRank
***
- Assigns the top ranking (query, response) pairs retrieved by dense retrieval a relevance score from initial search results
- High scores are given to the pairs where the response is relevant to the query, else the score given is low.
- It is implemented through a trained LLM(trained by passing query and correct response and query and negative responses)

### 3.3 Hybrid Search
***
- Hybrid search is making use of both keyword and semantic search to retrieve more relevant documents based on both the keywords present and the meaning.

![[Module-3 Building Blocks of RAG-7.png]]

- 1.Input Data
- 2.Sparse Embedding Model
	- Generates a sparse matrix of frequency of tokens
- 2.Dense Embedding Model
	- Generates a embedding based on semantics
- 3.Sparse and Dense Embedding is combined
- 4.Normalised
	- So that there are no mis interpretations in the distance
- 5.Hybrid Index
	- A hybrid index is generated and stored in Vector DB

> [!important]
> **Typical Hybrid Search Workflow:** <br>
> - The relevant vectors that match the keywords are first selected
> - Dense retrieval is done on these selected vectors


