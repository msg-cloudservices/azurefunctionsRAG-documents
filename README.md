## This repository contains two Azure functions:

## 1. The first function preprocesses documents uploaded for further use in RAG
  - The function is triggered by the upload of a new document to a specified Azure storage account
  - The documents are first cleaned and chunked
  - The embeddings are calculated
  - The enriched document is loaded as json-file into the second storage account

 ## 2. The second function is triggered on upload of the newly processed documents
  - Subsequently, the documents are uploaded into an already existing index in Azure AI Search.
  - Azure AI search performs the configured search algorithms to retrieve the context matched to the prompt.
  - This context is used to Augment the Generation provided by Azure OpenAI 
