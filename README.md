# Shellbots.ai - Documentation and Tutorials
Os and framework ai to create custom AI services and process

## Project Management

[Link to our devops tasks and project management in GitHub to follow dev](https://github.com/users/nuage365/projects/5)

## Tutorials

[Tuto01 - Basic functions from shellbots](https://github.com/nuage365/Shellbots.ai/blob/main/Tutorials/Tuto01%20-%20Basic%20functions%20from%20shellbots.md)  
[Tuto02 - The 3 shellbots functions to manage Dynamics365 Business central instances](https://github.com/nuage365/Shellbots.ai/blob/main/Tutorials/Tuto02%20-%20The%203%20shellbots%20functions%20to%20manage%20Dynamics365%20Business%20central%20instances.md)

## Architecture
![Shellbots ecosystem english version](https://github.com/nuage365/Shellbots.ai/assets/102873102/e8d79929-7c2b-4701-88f8-53d266a1a21f)

## Primitives core functions

### adddata :
Add datas to an exist free file or structured file in vector database

### ai_modelcreate :
Define specific ai model with python code for a context. All models existing in current context are used for result' scoring

### ai_modeledit :
Edit an existing specific ai model for current context

### ai_modelget :
Get all ai model from current context

### ai_modelremove :
Remove an existing ai model from current context

### clear :
Clear shellbots terminal 

### createcontext :
Create a new context  

### createdata :
Create a new free file or structured file in vector database

### exit :
Exit shellbots terminal 

### getcontext :
Get current context  

### getobjects :
Get objects from a current vector database

### systemdb :
Manage core system database

### usecontext :
Set current context

## Primitives Market AI integration functions

### ai_engineapikeycreate :
Reference and add an API Key for AI engine

### ai_engineapikeylist :
Get list of API Keys

### ai_engineapikeyupdate :
Update an existing API Key for AI engine

### ai_engineapikeyremove :
Remove an existing API Key for AI engine

### ai_enginecreate :
Reference and integrate new AI engine from market

### ai_enginelist :
Display AI engine list present, added and/or managed by framework

### ai_engineremove :
Remove Market AI engine from shellbots

### ai_engineupdate :
Update AI engine from market

### ai_setpartialviewON :
When use ai_engineapikeylist function, key value are partial hidden for security

### ai_setpartialviewOFF :
When use ai_engineapikeylist function, key value are full displayed

## Primitives extension functions

### bc_addinstance :
Add instance from Microsoft Dynamics 365 Business Central

### bc_getinstance :
List all instance from Microsoft Dynamics 365 Business Central

### bc_removeinstance :
Remove specific instance from Microsoft Dynamics 365 Business Central

## Primitives Algorithms extension functions

## Primitives Tools extension functions
