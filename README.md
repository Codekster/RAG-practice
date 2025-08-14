# RAG with LangChain, Chroma, and Google Gemini

This project demonstrates a basic Retrieval-Augmented Generation (RAG) system built using the LangChain framework, Chroma vectorstore, and the Google Gemini API. The system loads content from a specified URL, creates embeddings of the content, stores them in a vector database, and uses a large language model (LLM) to answer questions based on the relevant retrieved information.

## Features

*   Loads document content from a URL.
*   Splits document content into manageable chunks.
*   Creates vector embeddings using Google Gemini Embeddings.
*   Stores embeddings in a Chroma vectorstore.
*   Uses a Google Gemini LLM for generating responses.
*   Implements a RAG chain to retrieve relevant context and generate answers.

## Prerequisites

Before running this project, you need to have the following:

*   A Google Cloud Project and a Google Gemini API key. You can obtain one from [Google AI Studio](https://aistudio.google.com/).
*   Python 3.7 or higher installed.
*   Access to a Google Colab environment or a local Python environment.

## Setup

1.  **Clone the repository (Optional):** If you are working in a local environment, clone this repository. If you are in Google Colab, you can work directly in the notebook.

2.  **Install dependencies:** Install the required Python libraries using pip.

    ```bash
    pip install langchain_community langchainhub chromadb langchain langchain-openai langchain_google_genai langchain-core
    ```
    (Note: Some of these might already be installed in Colab.)

3.  **Set up your Google Gemini API Key:**

    *   **In Google Colab:** Go to the "🔑" icon in the left sidebar, select "Manage secrets", and add your Gemini API key with the name `GOOGLE_API_KEY`.
    *   **In a local environment:** Set the `GOOGLE_API_KEY` environment variable with your API key before running the script. You can do this in your terminal:
        ```bash
        export GOOGLE_API_KEY='YOUR_API_KEY'
        ```
        (Replace `'YOUR_API_KEY'` with your actual key)

## Usage

1.  **Open and run the notebook:** If you are in Google Colab, open the notebook and run the cells sequentially. If you are in a local environment, you can adapt the code into a Python script.

2.  **Specify the URL:** In the code cell that uses `WebBaseLoader`, update the `page_url` list with the URL(s) of the document(s) you want to load.

3.  **Run the RAG chain:** After setting up the embeddings, LLM, and RAG chain, you can invoke the chain with a question:

    ```python
    question = "Your question here"
    response = rag_chain.invoke(question)
    print(response)
    ```
    Replace `"Your question here"` with the question you want to ask about the loaded document content.

## Project Structure

The core logic is contained within the notebook cells. The key steps include:

*   Loading data using `WebBaseLoader`.
*   Splitting text using `RecursiveCharacterTextSplitter`.
*   Creating embeddings using `GoogleGenerativeAIEmbeddings`.
*   Initializing the vectorstore (`Chroma`).
*   Setting up the retriever.
*   Initializing the LLM (`ChatGoogleGenerativeAI`).
*   Constructing the RAG chain using LCEL.

## Contributing

This is a basic example. Feel free to extend it by:

*   Adding support for different document loaders (e.g., PDF, TXT).
*   Experimenting with different chunk sizes and overlaps.
*   Trying different embedding models or vectorstores.
*   Implementing more advanced RAG techniques.


copyright @Codekster

