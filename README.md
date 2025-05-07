Tariff News MCP Server
A specialized server for retrieving and analyzing tariff-related news using the Machine Conversation Protocol (MCP).

Overview
The Tariff News MCP Server provides a robust interface for AI agents to access up-to-date tariff news and reactions. It supports both stdio and Server-Sent Events (SSE) transport methods, making it versatile for different integration scenarios.

Features
Dual transport support (stdio and SSE)

Specialized get_tariff_reaction_news tool for retrieving tariff-related news

Integration with DuckDuckGo search for current news retrieval

Configurable time limits for news searches

Installation
Clone the repository and install dependencies:

bash
git clone https://github.com/shanscar/Tariff-News-MCP-Server.git
cd Tariff-News-MCP-Server
pip install -r requirements.txt
pip install -e .
Usage
Running with stdio transport (default)
bash
python -m tariff_news_server.server
Running with SSE transport
bash
python -m tariff_news_server.server --transport sse
Configuration
Add the following to your mcp_settings.json file:

json
"mcpServers": {
  "tariff-news-server": {
    "command": "python",
    "args": [
      "-m",
      "tariff_news_server.server"
    ],
    "env": {},
    "disabled": false,
    "alwaysAllow": []
  }
}
Architecture
The server follows a structured workflow:

Receives tool requests from MCP clients

Processes requests through the appropriate transport layer

Executes the requested tool function (e.g., get_tariff_reaction_news)

Queries DuckDuckGo for relevant news articles

Processes and formats the results

Returns structured data to the client

Solution Diagram
![MCP solution diagram](https://github.com/user-attachments/assets/a6ce6bb0-e4e0-473e-912d-f129f6a945df)

Development Stack
Language: Python

IDE: VS Code with Roo Code

Framework: MCP Python SDK

AI Integration: Google Gemini 2.5 Pro

Search Engine: DuckDuckGo News Service

Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
