# AI Calendar Assistant

An autonomous AI agent that schedules real calendar meetings from natural language commands — complete with Google Meet links, guest invitations, and reminders.

## Overview
Instead of manually creating calendar events, this agent understands conversational requests like "schedule a meeting tomorrow at 5 PM" and autonomously handles the entire event creation — including inviting guests and generating video conferencing links.

## Architecture

🔹 **Trigger Layer** — Chat-based input interface for natural language commands

🔹 **Reasoning Layer** — Agentic LLM (Google Gemini) parses intent, extracts date/time, title, and attendees from unstructured text

🔹 **Action Layer** — Google Calendar API integration (via tool-calling) creates events with dynamically resolved parameters

🔹 **Enrichment Layer** — Automatic Google Meet link generation, guest invitations, and custom reminder configuration

## Tech Stack
`n8n` (self-hosted orchestration) | `Google Gemini` (agentic reasoning) | `Google Calendar API` | `Agentic AI Workflows`

## Key Engineering Challenge
The agent initially miscalculated relative dates (e.g., "tomorrow") due to lacking awareness of the current date/time context, defaulting to an incorrect year. This was resolved by injecting a dynamic date reference into the agent's system prompt, ensuring all relative date calculations anchor to the actual current date at runtime.

## Features
- Natural language date/time parsing
- Automatic Google Meet link generation
- Guest invitation via email
- Configurable reminder notifications
- Context-aware date resolution

---
#AI #Automation #n8n #AgenticAI #GoogleCalendar
