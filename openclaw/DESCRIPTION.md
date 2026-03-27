# OpenClaw Assistant

> General-purpose AI assistant powered by [OpenClaw](https://github.com/openclaw-ai/openclaw) gateway.

## Overview

OpenClaw Assistant is a versatile AI agent that runs locally via the OpenClaw CLI. It connects to OpenRouter for model access and provides a rich set of built-in tools including web search, file operations, browser automation, and multi-channel messaging.

As a company-hosted subprocess employee, it runs via `launch.sh` — no persistent server needed. Each task or conversation spawns a fresh agent session.

## Capabilities

- **Conversation** — Natural language interaction via 1-on-1 meetings
- **Web search & browsing** — Research topics, fetch web pages, extract information
- **File operations** — Read, write, and edit files in the employee workspace
- **Task execution** — Process assigned tasks autonomously with structured output
- **Multi-channel comms** — Bridge messages across 20+ platforms (WhatsApp, Telegram, Slack, Discord, etc.)

## Prerequisites

- [OpenClaw CLI](https://github.com/openclaw-ai/openclaw) installed (`npm install -g openclaw`)
- OpenRouter API key configured (set `OPENROUTER_API_KEY` in `.env`)
- Node.js >= 22.12.0

## How It Works

1. OneManCompany's `SubprocessExecutor` calls `launch.sh` for each task/conversation
2. `launch.sh` ensures OpenClaw gateway is running, then invokes `openclaw agent --local`
3. OpenClaw processes the prompt using its built-in tools and returns structured JSON
4. Results are parsed and displayed in the OneManCompany UI
