# Automation & AI Integration Platform

Backend automation platform that processes external webhooks, stores tickets,
and automatically escalates critical incidents using workflow automation.

## Tech Stack
- FastAPI
- SQLModel
- SQLite
- n8n (Docker)
- HTTP-based integrations
- Mock AI service

## Features
- Vendor webhook ingestion
- Ticket CRUD operations
- Automated escalation using n8n
- AI-based ticket analysis (mock)
- External API integration with API key authentication

## Architecture Overview

Vendor → FastAPI → Database  
↓  
n8n → AI → Backend update

FastAPI is the source of truth.  
n8n orchestrates automation workflows.

## Run Locally

### Backend
```bash
uvicorn app.main:app --reload
