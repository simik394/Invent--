---
page-title: Home · your-papa/obsidian-Smart2Brain Wiki
url: https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file
date: 2024-04-10 13:04:03
tags:
  - A/sw/plugin
  - P/
  - M/⭐
  - F/wiki
  - C/architecture
about:
  - "[[Obsidian]]"
  - "[[RAG]]"
aliases:
  - 38c83c48-8364-49f2-82df-4414ce42dbb7
  - Home · your-papa/obsidian-Smart2Brain Wiki
by: 
length: 10112
dir:
---

## Architecture

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#architecture)

  ![smart second brain architecture](https://github.com/your-papa/obsidian-Smart2Brain/assets/103033288/aa8945d1-dab2-4942-b6d5-6e0a6d3733cc)

The architecture depicted in the image represents a sophisticated solution approach for a smart second brain, designed to enhance knowledge management and retrieval using a combination of multiple LLMs, a vector store, and processes to prepare the passed-through content. The term ’smart second brain’ comes from the idea of turning Obsidian, which functions as a second brain, into a smart second brain by infusing AI capabilities. This RAG architecture can be categorized as a naive RAG. A naive architecture follows a traditional process that includes indexing, retrieval, and generation. It is also characterized as a “Retrieve-Read” framework.

## Knowledge Base Indexing

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#knowledge-base-indexing)

Obsidian exposes the `getMarkdownFiles()` function which returns all markdown files for a specific Obsidian vault, providing us with the entire knowledge base. To chunk the knowledge base we created the `obsidianDocumentLoader(obsidianApp: App, files: TFile[])` function. This function takes markdown files as input and splits each file into smaller segments. We decided to segment the markdown files based on the headings contained within the document. With more specific units of meaning the embeddings will also be more precise and lead to better retrievals later on. The size of the chunks cannot be larger than the maximum token size of the embedding model. Otherwise, the model is not able to create a vector representation of this chunk. To address this case we decided to check the size of each heading and its corresponding paragraph. If the chunk is larger than the maximum token size of the embedding model, we split the chunk again and provided those chunks with an ID to indicate that they belong together.

After the chunking process, the chunks are processed by the `embedDocuments(documents: Document[], indexingMode: IndexingMode = 'full')` function. It aggregates the chunks into batches, with the batch size acting as a hyperparameter that determines the number of chunks to be embedded in a single execution. Opting for smaller batch sizes tends to reduce the efficiency of the process. However, it enhances the robustness as any errors encountered necessitate the re-execution of the entire batch. Each batch runs through two stages.

The first stage involves passing the chunks to a record manager. This record manager is a database designed to track the chunks that have been converted into vector representations within the vector database. This tracking capability provided by the record manager allows for the identification of chunks that have already been embedded. Consequently, embeddings are generated solely for those segments that have not yet been processed. In the event that the content of a chunk has been modified, only the corresponding entries in both the chunk embedding and the record manager are updated accordingly. If a chunk is already present in the record manager, the embedding process is skipped. This method significantly enhances the efficiency of the embedding process and, crucially for this project, conserves computing resources.

The second stage involves the embedding process where the chunks are passed into the embedding model and turned into a vector representation of its content. The vectors are then stored in the Orama vector store with a hash of the chunk as a key and the vector itself as a value. Embedding models vary in the size of their embedding dimensions and in the manner they represent the meaning of the embedded text. Hence the dimensions of the Orama vector store have to be adjusted dynamically depending on which embedding model is used. Consequently, this necessitates the usage of distinct vector stores for each embedding model utilized to accommodate the unique dimensional specifications and representation methodologies of different models. This ensures that the retriever can always pull the relevant documents for each specific user query.

## Large Language Models

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#large-language-models)

Our goal with this application is to give the user as much freedom in choosing the model they want to employ as possible. As stated previously we chose Ollama to satisfy this requirement. As Ollama is a separate application we connect over the Ollama-provided REST API to Obsidian. The connection is only locally exposed and does not need an internet connection. The endpoints include but are not limited to generating a response from an input prompt with a provided model as well as generating embeddings for the provided text.

LangChain provides an integration for Ollama allowing us to seamlessly integrate these models into our application. An issue that arose was that LangChain uses the `fetch()` API as Ollama only allows cross-origin requests from 127.0.0.1 and 0.0.0.0 by default and Obsidian as an electron application uses its own URL. This resulted in constant CORS errors. To address this issue it is possible to add allowed origins to the Ollama application. However, this creates more overhead for the user as he has to change this variable manually.

LangChain provides three distinct components associated with LLMs which are encapsulated by abstract classes: the `BaseLLM` class represents LLMs, the `BaseChatModel` class is designated for Chat Models, and the `Embedding` class is allocated for Text Embedding Models. Ollama implements all three of these classes, enabling the utilization of instruct, chat, and embedding models within the LangChain framework. In the context of our current use cases, only the chat and embedding models are relevant.

To implement those we use the provided class extensions `OllamaEmbeddings` and `ChatOllama` respectively. By providing the port on which the Ollama application is running and the model to be used we can create an instance of each class. The user is able to choose from all models installed with Ollama on his local machine which model he would like to use as an Embedding model or as a Chat model respectively. Employing distinct models for embedding and chatting, respectively, underpins our strategy to favor smaller, specialized expert models over larger, more generalized ones. Although this approach requires more storage space, it reduces the need for computational memory. This trade-off is particularly beneficial for the local usage requirement since storage space tends to be more affordable than computational resources.

Furthermore, a LangChain `VectorStoreRetriever` is created, wherein the chosen embedding model along with the corresponding Orama vector store is designated. The retriever processes an input string by embedding it using the given embedding model and then leverages Oramas vector search engine to perform a cosine similarity search on the vectorized query and stored vectors. Subsequently, it retrieves and returns the 'top k' documents that have the highest similarity to the input query.

## RAG Pipeline

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#rag-pipeline)

The LangChain Expression Language (LCEL) enables the construction of complex AI applications with features like optimized parallel execution for reduced latency and advanced mechanisms for retries and fallbacks to enhance system resilience. It also facilitates access to intermediate results, improving the transparency and debuggability of processes. Consequently, LCEL simplifies the orchestration of the aforementioned components into a cohesive and robust RAG pipeline.

The chain is configured to accept as input parameters the user's query and a history of previous messages, both provided as strings, along with the instantiated retriever and the chosen chat model. Concurrently, the user query and the message history are stored as parameters and the retriever fetches the most relevant documents related to the user's query. Additionally, we implemented the `docsPostProcessor()`function. Its purpose is to reassemble document chunks into their original structure when multiple chunks from the same document are retrieved. This process involves sorting related chunks according to their original headings structure and merging overly lengthy paragraphs based on their previously given index, ensuring the context provided is coherent and not merely a loose collection of retrieved information.

Depending on the length of the query, the length of the chat history as well as the value of 'k' used for the retriever, this can amount to a lot of tokens. Tokens in LLMa are the basic units of text, such as words or parts of words, depending on the tokenization method. If the text exceeds the maximum input token size of the embedding model we implement the `docsReducePipe()` function which uses hierarchical tree summarization to reduce the size of the fetched context.

Hierarchical tree summarization is a naive approach to reduce the size of the retrieved context with minimal information loss. For this purpose, the retrieved documents are split again into smaller chunks to fit into the maximum input token window. The model is then prompted to summarize the chunks to reduce the token size of the content. Subsequently, the summarized documents are merged and we check the amount of tokens. If the reduction was enough we are done but if the input size is still exceeded we repeat the process until the content fits into the token window.

The three parameters are passed to the next component, which utilizes a prompt template designed through prompt engineering techniques to encourage the production of relevant and coherent responses based on the provided parameters. The quality of the response generated by the chat model is directly proportional to the precision and structure of the prompt formulation, which augments the original user query with the retrieved documents and chat history, thereby enhancing the contextual relevance of the generated response. This prompt is subsequently passed to the chosen chat model which then generates its response. The prompt template further guides the chat model to disregard irrelevant augmented information and honestly state if lacks the information to address the query. The generation of the response is streamed to the user so that he can witness the creation of the answer in real-time.