# Tuto 07 - Dynamics 365 Business Central and AI data generation
> Version 2024.04.18.1, Author : Dominique Delaire

![queryfields_1](https://github.com/nuage365/Shellbots.ai/assets/102873102/a1ee4edf-7ed2-446e-903a-00555e8ecf0f)
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
![vendorcardbusinesscentral_4](https://github.com/nuage365/Shellbots.ai/assets/102873102/a267e7cf-8900-4578-b95e-858f9dc3d3a8)

![vendorcardbusinesscentral_3](https://github.com/nuage365/Shellbots.ai/assets/102873102/88a17267-867d-41f3-868c-88cf27d93ca9)

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
  
![getobjects1](https://github.com/nuage365/Shellbots.ai/assets/102873102/1a66009d-f6d3-42e8-9168-cb3f7de1f8fe)

![getobjects2](https://github.com/nuage365/Shellbots.ai/assets/102873102/dbf660b7-2b7f-45e6-b98b-f03ead5b0146)

![getobjects3](https://github.com/nuage365/Shellbots.ai/assets/102873102/63abcf2b-27db-45b6-8583-feba581a5654)

### bc_getfields
- **Same principle as bc_getobjects but this function synchronizes all the fields of all Business Central tables.**

![getfields1](https://github.com/nuage365/Shellbots.ai/assets/102873102/cd10f67d-74f6-4fc0-bf35-61e4e1f6fa4b)

![getfields2](https://github.com/nuage365/Shellbots.ai/assets/102873102/a250f8c8-a88d-47e5-a8d3-8c6a08450545)

### bc_queryobjects
- This function allows you to query any object including BC system objects.

Here, for example, we search for all objects with the name "G/L entry" to search for objects linked to accounting entries
![queryobjects1](https://github.com/nuage365/Shellbots.ai/assets/102873102/6b364aec-3b87-4007-b22d-853c80be9d2f)

Same thing here but for vendors
![queryobjects2](https://github.com/nuage365/Shellbots.ai/assets/102873102/c9ee5bdd-fb2a-4cef-8abc-727d1eef4b6c)



`If you have any questions, feel free to send me a connection on Linkedin at` https://www.linkedin.com/in/dominiquedelaire/ `or contact us on our website` https://nuage365.ca `for our AI services or to make an appointment.`
