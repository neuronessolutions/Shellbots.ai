# Tuto 08 - Scoring of Ai engines with shellbots
> Version 2024.05.02.1, Author : Dominique Delaire

## Introduction
**This tutorial helps to `understand how we can score between different AI engines to compare them and see where they excel in a specific area`**

**For some of our clients, and before developing specific AI services with the shellbots framework and accelerator platform, we can determine which are the best AI engines on the market depending on the client's domain or need.**

**To perform scoring or matches between AI engines in shellbots, we have 2 methods, a `manual` method and a `method controlled by our internal inference engine`**

## Scoring AI engines using the manual method

The manual method involves building AI shellbot models to manually evaluate the results of different AI engines following prompts in the client's specialized areas. For example, for dietetics, we could hire a nutritionist for a few weeks to evaluate the results on different specific prompts for the client.

**In this tutorial, we have a manual and automatic model to perform a basic fight between the Mistral (7b model), OpenAI (GPT 4), and Google Gemini (pro) AI engines with a very simple prompt.**

In first, we change the context (customer project) for tutorial. We created a context for these simple models.   
**Go to the "scoring test" context :**

![print1](https://github.com/nuage365/Shellbots.ai/assets/102873102/bc3b77a6-dcdb-4d78-a158-2965f293cfed)

![print2](https://github.com/nuage365/Shellbots.ai/assets/102873102/34bea790-c023-4027-8fab-a949268ffdd3)

**After, we get the ai models for current context :**

![print3](https://github.com/nuage365/Shellbots.ai/assets/102873102/9d4bb39f-3dfe-4eb9-9f5c-2abc052b85dd)

**Then, we execute the manual model in first with ai_modelexec function :** 

![print4](https://github.com/nuage365/Shellbots.ai/assets/102873102/97964c4e-c746-48e0-8512-e1fb4b0f3fd0)

**This model ask a prompt and we will evaluate it in the field of poetry for example.**   
With the prompt in french : "Génère moi un poème de 4 lignes" (Generate me a 4 line poem)   
**This example is very simple but we will see that there are more or less good results.**

![print5](https://github.com/nuage365/Shellbots.ai/assets/102873102/60c5c3ae-945c-401f-8f01-d1cf1319ad07)

**At the end of the execution of the manual model for this fight between the different engines, we obtain the results and we are ready to evaluate them.**

![print6](https://github.com/nuage365/Shellbots.ai/assets/102873102/f64c22c8-652a-425c-a0f7-e8e067dea028)

**This simple example shows that even if my prompt is in French, the Mistral 7b model on this domain responds in English. So we won't give it the best rating :) And the other 2 look okay.**   
**At the end, the results and scores for each engine are recorded in the context vector database. The objective for manual mode is to run different prompts in the area where the client's AI service will be built for weeks and evaluate it to have an average of each AI engine.**   
**This can make it possible to recommend to the customer the best engine(s) for their service.**

![print8](https://github.com/nuage365/Shellbots.ai/assets/102873102/ea783c80-c464-4b87-81e2-38af8d41f075)

## Scoring AI engines using the automatic method
**So, we created another simple model but this time we submit the prompt to our internal AI engine to evaluate the results of each engine and log its comments on each result to also get an average after a certain number training. For the example, here, it is a manual prompt but we can easily automate different prompts of a domain for the client and can execute hundreds of thousands of prompts. We can also manually check certain results for quality control.**   
**Our model being for French, we decided in the model to indicate that the automatic evaluations must be in French.**

![print9](https://github.com/nuage365/Shellbots.ai/assets/102873102/8af006f8-8cd7-4fbc-813e-2124e071b427)

**So for this example, we will be more specific and indicate that we want the result in French for the same prompt as our manual model.**   
With the prompt in french : "Génère moi un poème de 4 lignes en français" (Generate me a 4 line poem in french) :  

![print10](https://github.com/nuage365/Shellbots.ai/assets/102873102/b0e70958-2533-4b2b-80de-1f236c889a1b)

**And we can observe that the engine has put comments and put a rating by default. Here, it's very simple and the prompt too, but we could give indications to the model to differentiate the motors much better, by using a lot of parameters for each motor.**

![print11](https://github.com/nuage365/Shellbots.ai/assets/102873102/7420700d-a07d-47fd-ba1e-0d02e0f93e50)

**We can combine manual and automatic assessments for the client depending on the sector. This can also work for models that use image generation.**

**Thanks to its framework, its accelerator functions and the Python language, `we can create battles between dozens of specialized engines from the client's domain and create specific models very quickly! before starting an AI project for a client :)`**

`If you have any questions, feel free to send me a connection on Linkedin at` https://www.linkedin.com/in/dominiquedelaire/ `or contact us on our website` https://nuage365.ca `for our AI services or to make an appointment.`

