# Deploy LogSearch Alert Rules in Azure using Azure DevOps Pipeline
## Step 1
### Architecture
- When you want to deploy Alerts into Azure, you might want to take a centralized approach so that management of the monitoring resources is easy plues you adhere to the https://learn.microsoft.com/en-us/azure/architecture/framework/devops/principles
- Keeping this in mind the pipeline and the ARM template is designed to input only necessary parameter.
![image](https://user-images.githubusercontent.com/118750597/203406927-afde7e20-d74c-41e8-81fd-c2fa0688a76b.png)
- As outlined in the design above, the alerts, action groups and log analytics all remain in the same resource group.
### Step 2
#### Download the 3 files from the repo.
- DeployLogSearchAlertRules.json: The ARM template to deploy multiple alert rules in a client environment
- Parameter.json: Passes the parameters unique to your environment
- azure-pipelines.yml: Provides you the instruction of running a devops pipeline to run these 2 json files
### Step 3
- Make sure you replace the values of the variables in the DeloyLogSearchAlert.json file and the values in the resources appropriate to your environment.
- Make sure you you provide the values in the parameters files
- Upload the yml file to your AzureDevops and replace the values with information appropriate to your environment
- Note: Since my environment already had a service connection so it used the same one. But in your case you might use your existing service connection or create a new one.
### Step 4
 Run the pipeline
### Step 5
 Once the pipeline runs successfully, you can check the alerts deployed in the azure portal.
