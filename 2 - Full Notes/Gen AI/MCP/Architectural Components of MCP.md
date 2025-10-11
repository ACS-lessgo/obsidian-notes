**Date**: 2025-10-11 18:58

**Topics**: [[Generative AI]]  [[MCP]]

**Category**: #gen-ai #mcp-architecture

## Notes :

#### Host, Client, and Server

![[Pasted image 20251011185939.png]]

1. **User Interaction**: The user interacts with the **Host** application, expressing an intent or query.
    
2. **Host Processing**: The **Host** processes the user’s input, potentially using an LLM to understand the request and determine which external capabilities might be needed.
    
3. **Client Connection**: The **Host** directs its **Client** component to connect to the appropriate Server(s).
    
4. **Capability Discovery**: The **Client** queries the **Server** to discover what capabilities (Tools, Resources, Prompts) it offers.
    
5. **Capability Invocation**: Based on the user’s needs or the LLM’s determination, the Host instructs the **Client** to invoke specific capabilities from the **Server**.
    
6. **Server Execution**: The **Server** executes the requested functionality and returns results to the **Client**.
    
7. **Result Integration**: The **Client** relays these results back to the **Host**, which incorporates them into the context for the LLM or presents them directly to the user.

#### The Communication Protocol

At its core, MCP uses **JSON-RPC 2.0** as the message format for all communication between Clients and Servers.

### 1. Requests

Sent from Client to Server to initiate an operation. A Request message includes:

- A unique identifier (`id`)
- The method name to invoke (e.g., `tools/call`)
- Parameters for the method (if any)

Example Request:

```
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "tools/call",
  "params": {
    "name": "weather",
    "arguments": {
      "location": "San Francisco"
    }
  }
}
```
### 2. Responses

Sent from Server to Client in reply to a Request. A Response message includes:

- The same `id` as the corresponding Request
- Either a `result` (for success) or an `error` (for failure)

Example Success Response:

```

{
  "jsonrpc": "2.0",
  "id": 1,
  "result": {
    "temperature": 62,
    "conditions": "Partly cloudy"
  }
}

Example Error Response:

Copied

{
  "jsonrpc": "2.0",
  "id": 1,
  "error": {
    "code": -32602,
    "message": "Invalid location parameter"
  }
}
```

### 3. Notifications

One-way messages that don’t require a response. Typically sent from Server to Client to provide updates or notifications about events.

Example Notification:

```
{
  "jsonrpc": "2.0",
  "method": "progress",
  "params": {
    "message": "Processing data...",
    "percent": 50
  }
}
```
## References :

- https://huggingface.co/learn/mcp-course/unit1/architectural-components