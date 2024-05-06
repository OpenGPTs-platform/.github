## Hi there 👋
### [DISCORD](https://discord.com/invite/K9hSNTTB)
### [Video Demo](https://youtu.be/yPdIEKb3jWc)

OpenGPTs is an open-source initiative with the goal of replicating the OpenAI "GPTs" product by creating open-source replicas of the several components that "GPTs" consist of. The successful execution of this project entails a fully observable and configurable GPTs alternative that can be deployed in a siloed environment, which can interface with any LLM, and can be extended to use unique tools.

To replicate "GPTs" we will develop a series of services that can be categorized into the following layers (top-down):

1. **Client**: A client to serve as a user interface ([chat-ui](https://github.com/OpenGPTs-platform/chat-ui), forked from HuggingFace assistants client)
2. **GPTs-to-assistants API layer**: An API layer (currently developed on the same [chat-ui](https://github.com/OpenGPTs-platform/chat-ui) Svelte-kit repository) to manage the storage of "GPTs" then mediate the requests to the assistants API.
3. **Assistants API**: [Assistants API](https://github.com/OpenGPTs-platform/assistants-api) which will be a python based OpenAI assistants API clone (will strictly follow OpenAI Assistants API's OpenAPI spec).
4. **Run Executor Worker**: [Run Executor Worker](https://github.com/OpenGPTs-platform/HexAmerous) will execute the model's runs against the inference infrastructure while leveraging tools and according to the prompt. 
5. **Inference Infrastructure**: Infrastructure to host the LLMs will include pre and post-processing to standardize features across any LLM (Will follow OpenAI completions API standard, will also be forking LiteLLM).

Layers #3,4 will be highly modular so that they can serve a variety of other purposes while #1,2 are more interdependent and built specifically for the "GPTs" use case.
This is a large project; you are welcome to contribute as much or as little as you want.

This project was just recently put into motion by a team open-sourcerors 🧙. We strive to make it fully open-source while following best practices to ensure an efficient development process. Hosting will be provided by Agent Artificial (an organization run by a subset of these sourcerors).
## Architecture
![image](https://github.com/OpenGPTs-platform/.github/assets/37946988/30879977-3940-401f-81a8-2b5786b6364b)
[_View full Figma spec_](https://www.figma.com/file/RBobTMUNS6EtelpTDyYqnA/Open-GPTs?type=whiteboard&node-id=0%3A1&t=Ga2G6MUOUiNjqe3l-1)

This project is organized in a way so that there is a separation of responsibilities this enables systems to be independent and easier to develop. The OpenGPTs system as a whole begins with the `Client & Business Layer API` service where a user would create and use GPTs. All requests will be sent to the `OS Assistants API` which handles persistent storage and requesting generations, it functions in the same way as [OpenAI's Assistants API](https://platform.openai.com/docs/assistants/). Finally, the request for generation is sent to `Run Executor Worker` which will handle the execution of the generation.
### [Client & Business Layer API](https://github.com/OpenGPTs-platform/chat-ui)
Monorepo containing the UI for users to create and use GPTs, it also handles the API requests (Business layer) and executes the API calls using the [assistants](https://platform.openai.com/docs/assistants) portion of the [`openai` SDK](https://platform.openai.com/docs/libraries/python-library). This repository is a fork from [huggingface/chat-ui](https://github.com/huggingface/chat-ui).
### [OS Assistants API](https://github.com/OpenGPTs-platform/assistants-api)
Python clone of the official [OpenAI Assistants API](https://platform.openai.com/docs/assistants). By leveraging the structure of the Assistants API we leapfrog the necessity to create our own system for managing tool-enabled AI chats.
### [Run Executor Worker](https://github.com/OpenGPTs-platform/HexAmerous) _(note currently in `dev` branch)_
Agent that handles the execution of AI generations (termed [`Runs`](https://platform.openai.com/docs/assistants/how-it-works/runs-and-run-steps) in Assistants API). With knowledge of the relevant details regarding the thread it utilizes tools and generates content iteratively untill completion.

## Contribute

### By joining this team you can expect the following:
- Learn to effectively contribute to a large-scale open-source project
- Work on a cutting-edge AI application.
- Become familiar with the AI ecosystem and pipeline.

### What layer is best for me?
#### Client:
- User experience obsessed.
- You love front-end.
- You can make effective win-win (between HuggingFace and OpenGPTs) proposals for system changes.
- Want to learn or improve in SvelteKit.
#### Assistants API:
- You thrive when the tasks and objectives are clearly scoped.
- Want to deeply learn the inner workings of OpenAI's AssistantAPI.
- You thoroughly test and evaluate your code by cross-checking with OpenAI's AssistantAPI.
- Want to learn and improve in FastAPI API, MinIO file storage, PostgreSQL dataabse, and Redis cache.
#### Cognitive Architecture Language Agents:
- You strive to make efficient LLM agents.
- Your LLM agents are stable and fault-tolerant. 
- You make informed system design decisions.
- You have strong intuitions on the scope of the project and need little guidance.
- You love uncharted waters.


