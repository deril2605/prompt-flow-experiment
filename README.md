# Azure Prompt Flow

## Prerequisites

### Set up Azure Open AI connection
- Create an Azure Open AI service by selecting a resource group, name of the service and pricing tier
- Open the service and go to Azure Open AI studio
- Go to deployments -> Create new deployment -> Select a model and give it a name and create
- Go to AML studio -> prompt flow -> connections -> create new connection -> select the above deployment and add as connection

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