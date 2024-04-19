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

## Creating extension functions for BC in shellbots
- For the client's needs, we created several functions to easily query ERP objects and table structures outside of Business Central.
  - **bc_addinstance** (see Tuto02)
  - **bc_getinstance** (see Tuto02)
  - **bc_removeinstance** (see Tuto02)
  - **bc_getobjects**
  - **bc_getfields**
  - **bc_queryobjects**
  - **bc_queryfields**   





`If you have any questions, feel free to send me a connection on Linkedin at` https://www.linkedin.com/in/dominiquedelaire/ `or contact us on our website` https://nuage365.ca `for our AI services or to make an appointment.`
