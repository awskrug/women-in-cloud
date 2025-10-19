---
title: "🌐 Chapter 4: Planar Portals - MCP Integration (Model Context Protocol)"
weight: 40
---

![Header Image](/static/images/header_4.png)

_"Opening portals to distant realms..."_

Welcome to the arcane arts of planar connections, brave traveler! In this chapter, you'll learn the mystical art of the [Model Context Protocol (MCP)](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/mcp-tools/) - the magic that allows your agents to connect to external services and invoke powers from distant realms.

## 🎯 Quest Objective

Master the art of MCP portals by creating a two-component system:
1. **An MCP Server** (`4_mcp_integration/dice_roll_mcp_server.py`) - That exposes the dice rolling service
2. **An MCP Client** (`4_mcp_integration/gamemaster_mcp_client.py`) - That connects to the server and uses its tools

## 🔮 The MCP Philosophy

The Model Context Protocol allows separation of tools from agents:
- **🏰 MCP Servers**: Expose specialized tools via a standardized protocol
- **🧙‍♂️ MCP Clients**: Connect to servers to use their tools
- **🌉 Benefits**: Reusability, scalability, separation of concerns

## 📜 Part 1: Forging the MCP Server (`dice_roll_mcp_server.py`)

### Step 1: Invoke the Necessary Modules 📚
**TODO**: Import `FastMCP` from `mcp.server`.

You need to import the `FastMCP` class to create your MCP server. The `random` and `logging` modules are already imported for you. Check out the [documentation](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server).

### Step 2: Create the MCP Server 🏰
**TODO**: Create an MCP server with the name "D&D Dice Roll Service" on port 8080.

Create a `FastMCP` instance with the specified `name`, and `port` 8080. Check out the [documentation](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server).

### Step 3: Run the Server 🚀
**TODO**: Run the MCP server.

In the main, add the line to start the MCP server with a transport defined as `streamable-http` like in this [example](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server)
The `@mcp.tool()` decorator is already implemented for you!


## 📜 Part 2: Create the MCP Client (`gamemaster_mcp_client.py`)

For this part, refer to this example in the [documentation](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server).

### Step 1: Import Connection Tools 🔗
**TODO**: Import `Agent`, `MCPClient` and `streamablehttp_client`

### Step 2: Establish the Planar Connection 🌉
**TODO**: Create a streamable http MCPClient connecting to "http://localhost:8080/mcp"

Create an MCPClient instance that connects to the dice server. Use a lambda function that returns `streamablehttp_client("http://localhost:8080/mcp")`.

### Step 3: Use the Context Manager 🔒
**TODO**: Use the `MCPClient` in a context manager (with statement)

Wrap your agent code in a `with` statement using the `MCPClient` to ensure proper connection management.

### Step 4: Get Available Tools 
**TODO**: Get available tools from MCP server using `list_tools_sync()`

Call the `list_tools_sync()` method on your `MCPClient` to retrieve available tools from the server.
Put the list in a variable called `mcp_tools` if you want to use the print statement.

### Step 5: Add Tools to Agent 🤖
**TODO**: Add the MCP tool to the gamemaster agent

## 🎲 Testing Your MCP System

### Step 1: Launch the Server
```bash
python dice_roll_mcp_server.py
```
You should see: "Starting D&D Dice Roll MCP Server on port 8080..."

### Step 2: Launch the Client (in another terminal)
```bash
python gamemaster_mcp_client.py
```

### Step 3: Test Dice Rolling
Try these commands:
- "Roll a d20"
- "Roll a d6" 
- "Roll a d100"
- "Roll 4d6 for ability scores"

## 🌟 Benefits of MCP Architecture

**🔄 Reusability**: The dice server can be used by multiple clients
**📈 Scalability**: Easy to add new tools to the server
**🛡️ Isolation**: Services are separated and independent
**🔧 Maintenance**: Update one service without affecting others

## 🎉 Quest Complete!

Congratulations, Portal Master! You've mastered the mystical art of the Model Context Protocol. Your system can now:

**What you've mastered:**
- ✅ Creating MCP servers that expose tools
- ✅ Connecting MCP clients to remote services
- ✅ Integrating MCP tools into Strands agents
- ✅ Distributed architecture for agent systems

**Loot Acquired:**
- 🌐 MCP dice rolling server
- 🧙‍♂️ MCP client with Lady Luck
- 🔗 Distributed architecture skills
- 🎲 Centralized and reusable dice system

**Next Adventure**: Head to Chapter 5 where you'll discover Agent-to-Agent (A2A) communication and learn to orchestrate teams of specialized agents!

---

_"A well-opened portal is worth a thousand local tools!"_ 🌐✨