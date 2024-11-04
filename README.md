# Vector Store with ChromaDB

This repository provides a Python-based implementation for creating and managing a vector store using ChromaDB. This can be useful for applications that need to efficiently store, manage, and retrieve embeddings, such as search or recommendation systems. The included files (`chromadb.py` and `chromadb.ipynb`) demonstrate the basic usage of ChromaDB for handling collections of documents with embeddings.

## Project Structure

- **chromadb.py**: Script for setting up and interacting with ChromaDB in a Python environment.
- **chromadb.ipynb**: Jupyter notebook with an interactive version of the code for easier testing and modification.

## Getting Started

### Prerequisites

- Python 3.7 or higher
- `chroma-embeddings` library for managing ChromaDB and embeddings.

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/atharvapatil1210/vector-store-genai.git
    cd chromaDB
    ```

2. Install the necessary dependencies:
    ```bash
    pip install chromadb
    ```

### Usage

To get started, you can run the `chromadb.py` script or open `chromadb.ipynb` to interactively run the code in Jupyter Notebook.

#### Code Explanation

1. **Initialize a ChromaDB client**
   ```python
   chroma_client = chromadb.Client()
   ```
   - This line sets up the ChromaDB client, which serves as the main interface for managing collections and documents within ChromaDB.

2. **Create or retrieve a collection**
   ```python
   collection = chroma_client.get_or_create_collection(name="my_collection")
   ```
   - Here, we either create a new collection named "my_collection" or retrieve it if it already exists. Using `get_or_create_collection` helps avoid duplicate collections.

3. **Upsert documents**
   ```python
   collection.upsert(
       documents=[
           "This is a document about pineapple",
           "This is a document about oranges"
       ],
       ids=["id1", "id2"]
   )
   ```
   - `upsert` adds documents to the collection or updates existing ones. Each document has a unique ID to avoid duplicate entries in the vector store.

4. **Query the collection**
   ```python
   results = collection.query(
       query_texts=["This is a query document about florida"],
       n_results=2
   )
   ```
   - This line retrieves documents similar to the query text. ChromaDB automatically converts the query into embeddings, and the `n_results` parameter defines the number of documents returned based on similarity.

5. **Output results**
   ```python
   print(results)
   ```
   - Displays the documents retrieved from the query, which are the most similar to the query text based on vector similarity.

## Additional Information

ChromaDB is a high-performance, vector-based database that enables fast retrieval of similar documents. In this implementation:
- We use `upsert` instead of `add` to ensure no duplicate entries are created.
- The `get_or_create_collection` method simplifies collection management by preventing duplicate collection creation.
- Querying with `query_texts` allows for embedding generation on-the-fly, making the process flexible and efficient.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Contributing

We welcome contributions to enhance this vector store implementation. Please fork the repository and submit a pull request with your changes.

## Contact

For further questions or assistance, please contact us at [your-email@example.com].

---

Happy coding!
```
