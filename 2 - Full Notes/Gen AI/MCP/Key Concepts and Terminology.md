**Date**: 2025-10-11 18:48

**Topics**: [[Generative AI]]  [[MCP]]

**Category**: #gen-ai #mcp-server

## Notes :

#### Core MCP Terminology

- **Host**: The user-facing AI application that end-users interact with directly. Examples include Anthropic’s Claude Desktop, AI-enhanced IDEs like Cursor, inference libraries like Hugging Face Python SDK, or custom applications built in libraries like LangChain or smolagents. Hosts initiate connections to MCP Servers and orchestrate the overall flow between user requests, LLM processing, and external tools.
    
- **Client**: A component within the host application that manages communication with a specific MCP Server. Each Client maintains a 1:1 connection with a single Server, handling the protocol-level details of MCP communication and acting as an intermediary between the Host’s logic and the external Server.
    
- **Server**: An external program or service that exposes capabilities (Tools, Resources, Prompts) via the MCP protocol.



![[Pasted image 20251011185059.png]]

|Entity|Name|Description|
|---|---|---|
|Tool|Code Interpreter|A tool that can execute code that the LLM writes.|
|Resource|Documentation|A resource that contains the documentation of the application.|
|Prompt|Code Style|A prompt that guides the LLM to generate code.|
|Sampling|Code Review|A sampling that allows the LLM to review the code and make further decisions.|

## References :

- https://huggingface.co/learn/mcp-course/unit1/key-concepts