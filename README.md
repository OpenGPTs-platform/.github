OpenGPTs is an open-source initiative with the goal of replicating the OpenAI "GPTs" product by creating open-source replicas of the several components that "GPTs" consist of. The successful execution of this project entails a fully observable and configurable GPTs alternative that can be deployed in a siloed environment, which can interface with any LLM, and can be extended to use unique tools.

To replicate "GPTs" we will develop a series of services which can be categorized into the following layers (top-down):

1. A client to serve as a user interface (forked from HuggingFace assistants client)
2. A GPTs-to-assistants API layer to manage the storage of "GPTs" then mediate the requests to the assistants api.
3. Assistants API which will be a python based OpenAI assistants API clone (will follow OpenAI Assistants API's OpenAPI spec).
4. Cognitive Architecture Language Agents will execute the models runs by utilizing the tools available and the infrastructure inference according to the prompt. 
5. Infrastructure to host the LLMs will include pre and post processing to standardize features across any LLM (Will follow OpenAI completions API standard, will also be forking LiteLLM).

Layers #3,4 will be highly modular so that they can serve a variety of other purposes while #1,2 are more interdependent and built specifically for the "GPTs" use case.
This is a large project; you are welcome to contribute to as much or as little as you want.

This project just recently was put into motion by a team of experienced developers, and we strive to make it fully open-source and will thus be following best practices to ensure an efficient development process. Hosting will be provided by Agent Artificial (an organization ran by a subset of these developers).

By joining this team you can expect the following:

- Learn to effectively contribute to a large scale open-source project
- Work on a cutting-edge AI application.
- Become familiar with the AI ecosystem and pipeline.
