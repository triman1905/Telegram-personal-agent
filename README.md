
# Telegram AI Assistant with Google Calendar Integration

An AI-powered Telegram assistant built using n8n, LLMs (OpenAI / Groq), and Google Calendar.  
This assistant understands natural language messages from Telegram and can fetch calendar events, create new events, and respond conversationally.

---

## Project Overview

This project connects Telegram with an AI Agent that can reason over user input and perform actions such as:
- Answering user queries
- Fetching Google Calendar events
- Creating new Google Calendar events automatically

The system is built using a multi-workflow architecture in n8n.

---

## Workflow Architecture

The project consists of two workflows:

1. Telegram AI Assistant Workflow  
2. Calendar Automation Workflow

---

## Workflow 1: Telegram AI Assistant

### Telegram Trigger
- Listens for incoming Telegram messages.
- Acts as the main entry point for the assistant.

### Switch Node
- Filters and routes valid text-based messages.
- Prevents invalid or empty inputs from reaching the AI agent.

### Edit Fields
- Cleans and formats the incoming message.
- Prepares structured input for the AI agent.

### AI Agent
- Powered by an LLM (OpenAI Chat Model).
- Uses Simple Memory to maintain conversation context.
- Uses tool calling to decide whether a calendar action is required.

### Tool Integrations
The AI agent can call:
- get_google_tasks – fetch tasks or events
- calendar_flow_agent – trigger calendar automation workflow

### Telegram Response
- Sends the AI-generated response back to the user on Telegram.

---

## Workflow 2: Calendar Automation Agent

### Triggered by Another Workflow
- Executed only when the AI agent determines a calendar action is needed.

### AI Agent (Groq Chat Model)
- Uses Groq for fast and efficient reasoning.
- Interprets structured calendar instructions.

### Google Calendar Integration
- Create an Event: Adds a new event to Google Calendar
- Get Many Events: Retrieves upcoming calendar events

### Edit Fields
- Formats the calendar response before returning it to the Telegram workflow.

---

## Example Commands

- What meetings do I have today?
- Schedule a meeting tomorrow at 4 PM
- Add a reminder for project submission on Friday
- Show my upcoming events

---

## Tech Stack

- n8n
- Telegram Bot API
- OpenAI Chat Model
- Groq Chat Model
- Google Calendar API

---

## Key Features

- Telegram-based AI assistant
- Natural language scheduling
- Google Calendar integration
- Context-aware conversations
- Multi-workflow architecture
- Tool-based AI reasoning

---

## Future Enhancements

- Voice message support
- Task management integration
- Reminder notifications
- Multi-user calendar support
- Long-term memory storage

---

## Use Cases

- Personal productivity assistant
- Smart scheduling bot
- AI-powered reminder system
- Calendar automation agent

---

## Author

Triman Kaur  
Web Developer | AI Automation Enthusiast
