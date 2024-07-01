# Tuto 07 - Dynamics 365 Business Central and AI data generation
> Version 2024.04.18.1, Author : Dominique Delaire

![queryfields_1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/a1ee4edf-7ed2-446e-903a-00555e8ecf0f)
*example in shellbots os test environment*

## Introduction
**We have created an AI service to generate test sets or data for your different software. This can be useful for client test environments in particular.**

**One of our clients who has Dynamics 365 Business Central (a Microsoft ERP), and 365 Sales (a Microsoft CRM) wanted to be able to easily generate data for their environments and that this is not production data but which reflects the reality of its domain.**   

From **shellbots**, **we mixed the creation of an AI service to generate the data with an on-demand configuration to generate any type of data**, including images, etc.

**The client also wanted to be able to visualize the structures of this data directly in shellbots as an online service, query its Erp and CRM datas and generate BC code.**

In this **example**, we will **show some functions to query objects and fields from 365 Business central directly in the framework to generate dummy data for the ERP**.
Another tutorial will cover code generation and data querying via an LLM (Large language model)

## The specifications we want to achieve 
* For our Business Central customer test environment, we want to have around fifty records of new suppliers
* In particular, company names, addresses, emails, telephone numbers, etc.
* This will allow us to run tests on fictitious data but allowing us to test new features by focusing our data on our reality.

## Example of an existing supplier record in BC
- The fields in yellow are those we want to generate data from to obtain a set of approximately 50 new suppliers.
- There are also values ​​that we want to set as default and which are mandatory. We will not ask the AI ​​to generate values ​​but just to put a specific value.
![vendorcardbusinesscentral_4](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/a267e7cf-8900-4578-b95e-858f9dc3d3a8)

![vendorcardbusinesscentral_3](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/88a17267-867d-41f3-868c-88cf27d93ca9)

## Creating extension functions for Microsoft Dynamics 365 Business Central in shellbots
- For the client's needs, we created several functions to easily query ERP objects and table structures outside of Business Central.
  - **bc_addinstance** (see Tuto02)
  - **bc_getinstance** (see Tuto02)
  - **bc_removeinstance** (see Tuto02)
  - **bc_getobjects**
  - **bc_getfields**
  - **bc_queryobjects**
  - **bc_queryfields**   
### bc_getobjects
- **This function allows you to synchronize modified objects including the latest extensions developed in the vector database of the current shellbots context from a selected Business Central instance.**
- This will then make it possible to use this data on the objects in other functions, in an LLM, etc.
- If a developer adds new fields or objects via an extension, simply re-run the command (a bit like a check-in on github) to update all the objects in each of your environments.
  
![getobjects1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/1a66009d-f6d3-42e8-9168-cb3f7de1f8fe)

![getobjects2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/dbf660b7-2b7f-45e6-b98b-f03ead5b0146)

![getobjects3](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/63abcf2b-27db-45b6-8583-feba581a5654)

### bc_getfields
- **Same principle as bc_getobjects but this function synchronizes all the fields of all Business Central tables.**

![getfields1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/cd10f67d-74f6-4fc0-bf35-61e4e1f6fa4b)

![getfields2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/a250f8c8-a88d-47e5-a8d3-8c6a08450545)

### bc_queryobjects
- This function allows you to query any object including BC system objects.
  
Here, for example, we search for all objects with the name "G/L entry" to search for objects linked to accounting entries
![queryobjects1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/6b364aec-3b87-4007-b22d-853c80be9d2f)

Same thing here but for vendors
![queryobjects2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/c9ee5bdd-fb2a-4cef-8abc-727d1eef4b6c)

For our example, we therefore know that the vendors table is table 23.

Now we will list all the fields in vendor table 23 and use function **bc_queryfields**

### bc_queryfields
- **By querying the fields of this table, we will be able to quickly identify the name of these fields for which we want to generate fictitious values.**
- How it knows it's on this bc instance is that we also have the function bc_useinstancebydefault to define bc instance by default in a specific context. 
  
![queryfields_1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/9c39fc83-b932-4b53-920d-50ecd49bc3e8)

![queryfields_2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/71a868da-3a2b-4161-97ed-378777ee7052)

## Creating a dataset in shellbots
- **Creating a dataset allows one or more tables to define for each field what value it can have via a prompt or specific directives.**
- To do that, we execute **dataset_create function**
  
![dataset_create1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/aadc1bc5-7dd7-42b2-9f11-36e8a4d1eba7)

Either you set a prompt or you have the option to add directives for your data. For example, here, a constant represented by $$ and which means that the value after the $$ must be the value for this field.   
Instead of Must be the value "Domestic", you can set with Vendor_Posting_Group=$$DOMESTIC, you have the choice and multiple constants for your data generation, not just prompt technics.

![dataset_create2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/2717fc62-616c-4b80-9013-20739cf013ae)

## Creating a model and test execution
- **for our customer, we created an AI model to generate the data based on our dataset architecture**
- Customer can create unlimited dataset for several software (BC, Sales, 365 Finops, Netsuite, Salesforce, etc.) and use several models.
- To test the model, simply run the ai_modelexec function. This allows you to test the model and the result directly in the shellbots OS and framework before deploying the service, for example in an Amazon ec2, Azure or Google cloud or a Docker.

![ai_modelexec1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/ccbc2795-6126-47cc-a995-08637a6b9da7)


![ai_modelexec2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/22475741-d97c-461e-b768-f3c3baa48347)


![ai_modelresult](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/5011187e-e382-4461-aa2e-9a6b2777d3f5)

**This model, in this example, can create csv file and excel files. But we have other models to create directly datas in cloud Business central and dataverse for crm/powerapps apps via APIs.**

**So now, in this example after generating 50 vendors records in csv format, we will integrate it into Business Central via a configuration package.**

## Create configuration package and import to Business Central
**We create a new package for import Vendors in BC**     
![configpackage1](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/207d82d8-4956-48ab-8e1f-43fdb1c18dc7)

**Then, we define just our specific fields for import**   
![configpackage2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/0a7ab37a-f353-4fde-8f39-01c48dc9e9a1)

**After, we export to excel to get template file with xml map in excel for import**   
![configpackage3](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/74680a67-54ca-4529-b71a-33a156142b2a)

**We open excel file, copy paste our datas with the same column without key (BC generate vendor code automatically), save and import.**   
After, we applied package and import to get the new vendors in Business Central :)   
![vendorinbc](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/d5fc7f4f-9a9d-4942-afe0-22b1ac0f1acb)

**When we select a specific vendor, We get the data that was generated with our shellbots model**   
![vendorinbc2](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/6f63fd0b-405a-41d1-abb2-acb8791b3bca)

![vendorinbc3](https://github.com/neuronessolutions/Shellbots.ai/assets/102873102/a9ca73b2-fd5b-4ed4-a30a-ff2377a8898e)

## Next step
**The next step for the client is to have an LLM for their data but also to be able to query fields and objects in natural language and give instructions to create datasets automatically. We will see this in a future tutorial.**



`If you have any questions, feel free to send me a connection on Linkedin at` https://www.linkedin.com/in/dominiquedelaire/ `or contact us on our website` https://neuronessolutions.com `for our AI services or to make an appointment.`
