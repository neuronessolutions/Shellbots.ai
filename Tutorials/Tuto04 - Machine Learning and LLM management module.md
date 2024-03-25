# Tuto 04 - Machine Learning and LLM management module
> Version 2024.03.24.3, Author : Dominique Delaire


This module **is part of a series of 4 other modules which constitute the Shellbots OS and framework for creating innovative AI services.**

In this tutorial, we will detail the operation of **the second module and which concerns the management of machine learning and LLM in shellbots framework and os**.

## Representative diagram of the second module in shellbots (click to expand) :
![module2machinelearningshellbots](https://github.com/nuage365/Shellbots.ai/assets/102873102/675f5503-066f-419b-b88c-867726fbb6cf)

**We have integrated market best practices into the Shellbots framework. When we use it to build AI services for customers, we use all or part of the integrated functions and tools on the market.**

## Data sources
* Functions to manage connections to different Cloud or on-premises data sources
* Data sources is for all shellbots context
* Accessibility of data via Python libraries or via APIs
* Functions for doing data processing and transformation
* Query creation independent of the data source
* Data refresh function linked to your ML models
    
## Integration of market ML Engine
* The market ML engine integrated into the framework are available for all shellbots contexts, therefore for all AI projects and services.
* We have integrated the most used and common ML engines such as TensorFlow, Pytorch, Keras, and more 10 ML engines.
* When a new ML engine is available, we can quickly integrate it into the framework with basic functions from the shellbots environment.
* Functions are available to create ML models regardless of the engine
* Python libraries to manage market models are provided by default and new ones are added regularly to create different AI services.

## Definition of Model process
* Basic functions are available to manage the different stages of an ML model in shellbots
* **Feature engineering** :
  * **Feature Selection** : This involves selecting the most relevant variables for the prediction. The goal is to choose the features that have the greatest predictive power and eliminate those that are redundant or uninformative. This helps reduce dimensionality, improve model performance, and reduce training time.
  * **Feature Extraction** : This step involves transforming raw data into a set of features that can be understood and exploited by a machine learning model. For example, this could mean converting raw text into word or phrase vectors (as is the case with language models).
  * **Feature Construction (Creation of characteristics)** : New characteristics are created from existing data. This could involve mathematical operations such as taking the logarithm of a variable, or creating interaction variables that combine two or more variables.
  * **Feature Transformation** : Data can be normalized or standardized so that different features contribute equally to the model. For example, we could scale the values ​​so that they are all equally important to the model.
  * **Feature Encoding** : Some models only work well with numeric data. Therefore, one must encode categorical features (like country names) into numbers, using techniques like one-hot encoding or frequency encoding.
  * **Time Feature Engineering** : For temporal data, feature engineering could involve extracting trends, seasonality, and other temporal patterns that could be predictive.
* **Model training** :
  * Model training is the step where a machine learning model learns from the data provided
  * **Choice of model** : This can be a linear model, a decision tree, a neural network, or any other machine learning algorithm. The choice depends on the problem to be solved (classification, regression, clustering, etc.) and the nature of the data.
  * **Data preparation** : Before starting training, the data must be divided into a training set and a test set (and sometimes a validation set). The training set is used to train the model, while the test set is used to evaluate its performance.
  * **Definition of loss function** : The loss function measures how far the model's predictions are from reality. For example, the quadratic loss function is often used for regression problems.
  * **Optimization** : The objective is to minimize the loss function. To do this, we use optimization algorithms such as gradient descent or its variants (such as the Adam optimizer for neural networks). Optimization adjusts the parameters (or weights) of the model to minimize prediction error.
  * **Validation and hyperparameters** : It is important to tune the hyperparameters, which are the configuration parameters of the model and the training algorithm. This is often done through grid search or random search and requires testing the model on the validation set to ensure that it is not overfitting.
  * **Training** : During the actual training, the model makes predictions on the training set, calculates errors using the loss function, and adjusts its parameters. This process is repeated for many cycles, known as epochs, until the model performs well or a stopping criterion is reached.
  * **Evaluation** : After training, the model is evaluated on the test set to check its ability to generalize to new data. We use performance metrics such as accuracy, precision, recall, and F1 score for classification problems, or RMSE (Root Mean Square Error) for regression problems.
  * **Iteration** : Training the model may require several iterations of adjustment and evaluation to improve its performance.
* **Model evaluation** :
  * Model evaluation is the step in the machine learning process where you measure the performance of the model on data that was not used for training.
  * Model evaluation is an iterative step, which may lead to going back to previous steps to adjust the model or data preparation process to improve results.
  * **Test Data Set** : This set is separate from the training data and is not used during model training. The idea is to test the model in realistic conditions with data it has never seen.
  * **Performance Metrics** : Depending on the type of problem (classification, regression, etc.), different metrics are used to evaluate the performance of the model. For example :
     * For classification: accuracy, precision, recall, F1 score, AUC-ROC, etc.
     * For regression: mean square error (MSE), root mean square error (RMSE), mean absolute error (MAE), etc.
  * **Cross-validation** : To obtain a more reliable measure of model performance, cross-validation is often used. It involves dividing the data into several subsets and training and evaluating the model several times, with each subset serving once as a test set.
  * **Confusion matrix** : In classification problems, the confusion matrix is ​​a table that allows you to visualize the performance of a classification algorithm, notably showing false positives and false negatives.
  * **Error analysis** : This involves looking at cases where the model made errors to understand why it made them and to identify if a pattern emerges.
  * **Model selection** : If several models have been trained, the evaluation is used to compare their performance to select the best one.
  * **Generalization** : It is crucial to assess whether the model is able to generalize well to new data. A model that performs well on the test set but poorly in the real world could suffer from overfitting.
  * **Deployment decision** : If the model meets the expected performance criteria, it can be deployed to a production environment for use with real incoming data.
* **Model deployment** :
  * Model deployment marks the transition of a machine learning model from its development/test environment to a production environment where it can begin making predictions on new data in real-time or in operational applications.
  * **Integration** : The model is integrated into the existing production environment. This may involve integrating it into an existing application, a data management system, or setting up a specific API so that other services can interact with the model.
  * **Containerization** : Models are often packaged, which include all the necessary libraries and dependencies for the model to work consistently in different environments. We use a virtual machine for that, cloud dedicated virtual machine or container as docker.
  * **Orchestration** : Tools can be used to manage container deployment, including scaling and distributing load across multiple model instances.
  * **Updating and Maintenance** : Models may drift or become obsolete as data changes. Procedures must be in place to update, re-train and maintain models to ensure they remain performant and relevant.
  * **Security and Privacy** : Machine learning models can process sensitive data, so it is essential to ensure that the deployment meets data security and privacy standards.
  * **Scalability** : The system must be able to handle the increase in the volume of requests and data without losing performance.
  * **Feedback Loop** : A feedback system where the performance of the model is regularly evaluated and new data is used to continually improve the model is often implemented.
* **Monitoring & logging** :
  * Implementing robust monitoring and logging practices is essential to ensure that machine learning models continue to perform optimally and securely after deployment.
  * **Model performance** : Monitoring provides real-time tracking of the accuracy of model predictions and other performance metrics. This helps to quickly detect if the model is starting to perform poorly (a phenomenon known as “model drift”).
  * **Logging predictions** : Every prediction made by the model is recorded, allowing decisions made by the model to be reviewed and analyzed if problems arise.
  * **System Health** : Monitoring also checks the health of the system hosting the model, including CPU usage, memory, disk space, and network latency.
  * **Errors and exceptions** : Logs should record errors and exceptions that occur during the operation of the model to enable diagnosis and correction of problems.
  * **Audit and Compliance** : Logs can also be used for auditing purposes, ensuring that the model is used ethically and complies with applicable regulations.
  * **Log Analysis** : Analytics tools and platforms are often used to review and analyze logs, which can help understand model behavior and identify areas that need adjustments.
  * **Alerts** : Alert systems can be configured to notify technical teams if certain performance metrics exceed predefined thresholds, indicating that intervention may be necessary.
  * **Feedback Loop** : Logging predictions and performance helps create feedback that can be used to improve the model over time.
  * **Version management** : Monitoring must take into account the different versions of the deployed model, keeping track of the performance of each version for effective update management.
  * **Retraining and A/B Testing** : Monitoring can indicate when a model needs to be retrained with newer data, and logging can help evaluate the performance of new models in A/B experiments.
* **Continuous Integration and deployment** :
  * Continuous Integration (CI) and Continuous Deployment (CD), often grouped together as CI/CD, are practices in software development designed to improve software delivery speed and quality.
  * These practices are increasingly applied in machine learning projects to streamline the process of integrating machine learning models into production systems.
  * Here’s how CI/CD applies for machine learning :
    * **Continuous Integration (CI)**
      * **Automated Testing** : Whenever new code or models are committed to a repository, automated tests are run. This includes code quality checks, unit tests, integration tests, and sometimes lightweight model training and evaluation to ensure changes don't break existing functionalities.
      * **Version Control** : All code, including data processing and model training scripts, is versioned in a source control system. This facilitates collaboration among team members and ensures changes are tracked and reversible.
      * **Merge Requests (MRs) and Pull Requests (PRs)** : Changes are reviewed through MRs or PRs, promoting code quality and knowledge sharing within the team.
      * **Automated Build** : The CI system automatically builds the software (or model artifacts) required for deployment, ensuring the build process is repeatable and free from manual errors.
    * **Continuous Deployment (CD)**
      * **Automated Deployment** : Once the model and associated software pass all automated tests, the CD process automatically deploys them to production. This reduces manual intervention and speeds up the deployment process.
      * **Feature Flags and Rollback** : Advanced CD setups can use feature flags to enable or disable features dynamically without redeploying. Rollback mechanisms allow quick reversion to previous versions if issues are detected in production.
      * **Monitoring and Performance Tracking** : After deployment, the system continuously monitors the model's performance, logging metrics and anomalies. This feedback loop is crucial for identifying when a model might need retraining or when a deployment may have introduced issues.
      * **Automated Retraining and A/B Testing** : CD pipelines can include automated retraining of models with new data and A/B testing to compare model versions before fully rolling out a new model to all users.    

## Market LLM
* Integration of market LMs such as Transformers library, LLaMA, OpenAI, Bert, Roberta, T5, XLNet, M2M-100, ...
* The interconnection between LLM and specific data models opens a wide range of possibilities to improve the performance, flexibility, and usability of machine learning systems, by exploiting the power of advanced language processing and contextual understanding offered by LLMs.
* **Data Preprocessing and Enrichment** :
  * An LLM can be used to preprocess or enrich a dataset before training a specific model. For example, an LLM can generate automatic annotations for an unlabeled dataset or enrich text data with additional contextual information, making the dataset richer and potentially improving the performance of the trained model.
* **Automated Feature Engineering** :
  * LLMs can help with feature engineering by analyzing and transforming textual data into a set of features that can be exploited by traditional machine learning models. For example, by extracting entities, key concepts, or relationships from texts, or by converting text into embeddings (vector representations) that capture semantic aspects of the language.
* **Improving Models with Pretrained Knowledge** :
  * Domain-specific data models can benefit from the knowledge and context learned by an LLM when training it on large corpora of text. For example, by initializing a model with weights from an LLM, one can transfer some of this general knowledge of the language, which can be particularly useful for tasks requiring a deep understanding of the language or for limited data sets.
* **Natural Language Processing (NLP) Pipeline** :
  * In a complex NLP pipeline, an LLM can be used at multiple stages, such as initial text understanding, intermediate processing (e.g., text classification or clustering), and generation of answers or summaries. These outputs can then be used as inputs for other machine learning models specialized in specific tasks.
* **User-Model Interaction** :
  * An LLM can act as an interface between the user and a more specialized data model, translating natural language queries into actions or queries understandable by the model and vice versa. This helps abstract the complexity of the model and provides a more intuitive user experience.
* **Feedback Loop and Continuous Learning** :
  * Responses or predictions from a data model can be submitted to an LLM for evaluation, generation of feedback, or to create new training data. This can form a feedback loop where the LLM helps to continually adjust and improve the data model.

**The next tutorial will talk about a new AI service created with shellbots for restaurants and hotels for the creation of innovative recipes**

If you have any questions, feel free to send me a connection on Linkedin at https://www.linkedin.com/in/dominiquedelaire/
