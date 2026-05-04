# Relationship Manager

A personal CRM web application that connects to Notion as a database backend, enabling natural language contact management through AI-powered journal entry parsing.

This application was inspired by a new connection I made while on a trip. I wanted a system that would help me nurture new relationships without feeling like it was work. This system is designed to allow me to write free flowing journal entries about my daily interactions that are then analyzed by AI. The LLM system will extract the key points in my entry and parse it into separate fields that are then uploaded into my relationship management database for tracking. 

Built to demonstrate API integration across multiple platforms including Notion, Anthropic, and Cloudflare Workers, deployed as a production web application on Vercel. 

## Live Demo
[https://relationship-manager-beige.vercel.app](https://relationship-manager-beige.vercel.app)

## Features
- **Contact Intake** — Paste an AI-generated contact card JSON and save directly to Notion
- **Journal Entry Parser** — Write naturally about your day and the app extracts relationship moments and logs them to Notion automatically
- **Interaction Logging** — Log calls, texts, and meetings with structured data
- **Auto First Meeting** — Automatically creates a linked interaction entry when a new contact is saved
- **Password Protection** — Client-side authentication to keep your data private
- **Recent Contacts** — Quick view of recently added contacts

## Tech Stack
- **Frontend** — Vanilla HTML, CSS, JavaScript (single file, no framework)
- **Database** — Notion API
- **AI** — Anthropic Claude API (claude-sonnet-4-5)
- **Proxy** — Cloudflare Workers (handles CORS for both Notion and Anthropic APIs)
- **Deployment** — Vercel

## Architecture