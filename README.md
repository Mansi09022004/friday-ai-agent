# Friday — Real-Time Voice AI Agent

A real-time voice assistant that listens, talks back, remembers you across sessions, uses external tools, and can send WhatsApp messages by voice.

## What it does

- **Real-time voice conversation** using LiveKit Agents with Gemini Realtime
- **Long-term memory** with mem0, so it recalls earlier conversations
- **Tool use** through function calling and **MCP** (connected to n8n workflows)
- **WhatsApp messaging by voice** through Meta's WhatsApp Business Cloud API: say "send a WhatsApp to Mansi saying I'll be late", and the agent resolves the contact name, normalizes the number to E.164, calls the Graph API and confirms by voice
- **Dockerized** for easy setup

## WhatsApp integration notes

- Uses Meta's Business Cloud API (Graph API) with a non-expiring System User access token instead of the 24-hour temporary token.
- Built and tested with Meta's test phone number: recipients must first be added and verified in the Meta developer console.
- Secrets are never committed. They are kept in environment variables locally and in LiveKit Cloud Secrets when deployed.

## Tech stack

Python · LiveKit Agents · Gemini Realtime · mem0 · MCP · n8n · LangChain · Meta WhatsApp Business Cloud API · Docker

## Project structure

| File / folder | Purpose |
|---|---|
| `agent.py` | Main voice agent entry point |
| `prompts.py` | Agent instructions and prompts |
| `tools.py` | Tools the agent can call (including WhatsApp) |
| `mcp_client/` | MCP client for external tools |
| `Dockerfile` | Container setup |

## Setup

1. Install dependencies:
```bash
   pip install -r requirements.txt
```
2. Create a `.env` file with your LiveKit, Gemini, mem0 and WhatsApp keys.
3. Run the agent:
```bash
   python agent.py dev
```

## Author

Built by [Mansi Gangji](https://www.linkedin.com/in/mansi-gangji)
