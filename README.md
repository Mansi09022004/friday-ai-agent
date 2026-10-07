# Friday — Real-Time Voice AI Agent

A real-time voice assistant that listens, talks back, remembers you across sessions, and can use external tools.

## What it does

- **Real-time voice conversation** using LiveKit Agents with Gemini Realtime
- **Long-term memory** with mem0, so it recalls earlier conversations
- **Tool use** through function calling and **MCP** (connected to n8n workflows)
- **Dockerized** for easy setup

## Tech stack

Python · LiveKit Agents · Gemini Realtime · mem0 · MCP · n8n · LangChain · Docker

## Project structure

| File / folder | Purpose |
|---|---|
| `agent.py` | Main voice agent entry point |
| `prompts.py` | Agent instructions and prompts |
| `tools.py` | Tools the agent can call |
| `mcp_client/` | MCP client for external tools |
| `Dockerfile` | Container setup |

## Setup

1. Clone the repo and install dependencies:
```bash
   pip install -r requirements.txt
```
2. Create a `.env` file with your LiveKit, Gemini and mem0 keys (see the code for variable names).
3. Run the agent:
```bash
   python agent.py dev
```

## Author

Built by [Mansi Gangji](https://www.linkedin.com/in/mansi-gangji)
