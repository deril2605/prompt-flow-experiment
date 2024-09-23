# Azure Prompt Flow

## Prerequisites

### Set up Azure Open AI connection
- Create an Azure Open AI service by selecting a resource group, name of the service and pricing tier
- Open the service and go to Azure Open AI studio
- Go to deployments -> Create new deployment -> Select a model and give it a name and create
- Go to AML studio -> prompt flow -> connections -> create new connection -> select the above deployment and add as connection
- Need to be aware of daily token limit and request limits on openAI models

### Compute Session
- Create a compute instance on AML studio (or)
- Create a flow and on top right select "Start Compute Session" and select if we want serverless or a compute instance

### Prompt flow extension for VS Code (Optional)
- Install prompt flow extension by Microsoft
- It will automatically ask to install prompt flow dependencies needed (`pip install promptflow promptflow-tools`)

#### Create a new flow using extension
- Click the extension 
- Create new flow -> select type of flow
- Enter the path and a name "my-first-flow"
- It will create a flow will all the necessary files

### Vector Index in prompt flow
- 2 types
    - AI Search
    - FAISS (https://engineering.fb.com/2017/03/29/data-infrastructure/faiss-a-library-for-efficient-similarity-search/)
- Data can be uploaded from local folder or can come from Datasets
- Needs a compute (can be serverless or compute instance)
- Needs a embedding model (text-embedding-ada-002 for faiss) deployed on Azure OpenAI service
- How to?
    - Go to prompt flow -> vector index -> create -> name, data source and type of index
- it stores the data and gives a storage uri
- Had to make the vector store open to anonymous read access
    - Go to prompt flow -> vector store -> open the vector store -> open in azure portal (bottom right) -> click index.pkl -> change access level
    - Or Might have to do this as well https://techcommunity.microsoft.com/t5/image/serverpage/image-id/475832i99F53630DB0B1A4B/image-dimensions/1000?v=v2&px=-1

## Example of QnA using own data and Faiss index
- ![image](https://github.com/user-attachments/assets/d2f4061d-98b4-4791-b941-36ef493e9601)
- ![image](https://github.com/user-attachments/assets/1f7af650-0460-4eff-9401-5084150047e0)
- Question
    - ![image](https://github.com/user-attachments/assets/ec077fe4-a89c-49eb-8b71-c5d4383f3767)
- Retrieval part
    - ![image](https://github.com/user-attachments/assets/ee9b961d-a9b0-4e2d-afba-9f795d69f6c2)
- Generation part
    - ![image](https://github.com/user-attachments/assets/39563081-a4af-46f7-ba82-5ebaa778155d)
- In the above the entire flow wasn't executed because 
