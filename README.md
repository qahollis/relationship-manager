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

    User → Vercel (static site)
         → Cloudflare Worker (proxy)
              → Notion API (contacts & interactions database)
              → Anthropic API (journal entry parsing)

## Setup

### Prerequisites
- Notion account with API integration configured
- Anthropic API key (console.anthropic.com)
- Cloudflare account (free tier)
- Vercel account (free tier)

### Notion Databases Required

**Contacts** — Fields: Name, Category, Status, How We Met, Met On, Location Met, Company/Org, Role/Title, Industry, Email, Phone, LinkedIn, Shared Interests, Notes, Next Outreach Date, Outreach Cadence, Last Contact Date, Relationship Score, Referred By, Related Contacts, Interactions, Interaction Count, Tags

**Interactions** — Fields: Interaction Title, Contact, Date, Type, Direction, Summary, Follow-Up Needed, Follow-Up Action, Follow-Up By, Sentiment, Outreach Draft

### Cloudflare Worker
Deploy the worker script to proxy API calls and resolve CORS restrictions. Routes `/notionapi/*` to Notion and `/claudeapi/*` to Anthropic.

### Configuration
Enter the following in the app's configuration panel:
- Notion API key
- Anthropic API key
- Contacts database ID
- Interactions database ID
- Cloudflare Worker URL

## Usage

### Adding a New Contact
1. Describe the person to Claude in chat and request a contact card JSON
2. Copy the JSON output
3. Paste into the Contact intake tab and click Parse
4. Review the card and click Save to Notion

### Journal Entry Logging
1. Write naturally about your day in the Journal entry tab
2. Click Parse journal entry
3. Review extracted relationship moments
4. Click Log to Notion or Save all to Notion

### Logging an Interaction
1. Ask Claude to generate an interaction log JSON
2. Paste into the Log interaction tab
3. Parse and save to Notion

## Project Context
Built as part of a data engineering portfolio to demonstrate API integration, serverless architecture, and AI-powered application development.

## Author
Quentin Hollis — [github.com/qahollis](https://github.com/qahollis)