## This repository contains one Jupyter Notebook and two Azure functions:

### 1. The Jupyter Notebook contains the code for creating a new index in Azure AI Search. 
To start, create an .env file containing the secrets for your Azure AI Search Service:

AZURE_SEARCH_SERVICE_ENDPOINT=""

AZURE_SEARCH_INDEX_NAME=""

AZURE_SEARCH_ADMIN_KEY=""


### 2. The first function preprocesses documents uploaded for further use in RAG
  - The function is triggered by the upload of a new document to a specified Azure storage account
  - The documents are first cleaned and chunked
  - The embeddings are calculated
  - The enriched document is loaded as json-file into the second storage account

 ### 3. The second function is triggered on upload of the newly processed documents
  - Subsequently, the documents are uploaded into an already existing index in Azure AI Search.
  - Azure AI search performs the configured search algorithms to retrieve the context matched to the prompt.
  - This context is used to Augment the Generation provided by Azure OpenAI 
