# ContextLLM-Context-Retrieval-Chatbot-with-Large-Language-Model

## Installation and Setup
```
git clone https://github.com/AryPratap/Context-Retrieval-Chatbot-LLM.git
```
The repo contains two segments 
- Vector Database
- Chatbot pipline

### Vector Database
All the files associated with vector database creation and evaluation are present in vectorDB folder 
The repo features two different types of vector databases and their evaluation 
- Chroma Vector Database
- Custom made Vector Database

Steps to prepare vector database 
- Data Crawling 
  - use the <b>web_crawl.py</b> file with the required website URL to crawl the data of that website in txt and pdf formats.
  - <b>web_crawl.py</b> file contains detailed comments to crawl the data from website.
- Custom Vector Database
  - After crawling data in a folder, just run the <b>vectorDB/Custom_Vector_Database.ipynb</b> file by just updating the source directory variable as mentioned in the file.
  - All the dependencies and folders will be build automatically just by running the file. Use the create_context function to retrieve the context for your query
    ```
    
    question =  "What is B.Tech curriculum? "
    
    context = create_context(
      question,
      df,
    )
    context
    ```
- Chroma Vector Database
   - Similar to custom vector database just run the <b>vectorDB/Chroma_vector_database.ipynb</b> file from top till the <b>main()</b> function, by updating the source directory(where crawled data is stored), and persist_directory(folder where ChromaDB files will be stored).
   - After vector database is build, you can see and further load the vectorDB files from persist_directory. Detailed example of such is given in the notebook itself.

- Evaluation
  - For evaluation the context retrieval quality of the vector databases, run <b>vectorDB/ChromaDB_Daiict_Evaluation.ipynb</b> file with updated persist_directory in which either use the self made vectorDB or download the already build vectorDB files
  - The link to the already created VectorDB files can be found in the <b>dataset_link.txt</b> file.

### Chatbot Pipeline
The chatbot uses dolly3-b model for answer generation, 
The repo features two pipeline, 
- Custom pipeline
- langchain RetrievalQA pipeline

Just run the <b>BOT_with_custom_retrieval_chain.ipynb</b> and <b>BOT_with_langhchain_retrieval_chain.ipynb</b> file for running the piplein, refer to the comments in the notebook for setup and vectorDB path defination. 

<b> The BOT_QA_sample.txt file contains some sample question answering pair for the build chatbot. </b> 

