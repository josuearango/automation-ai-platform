# Automation & AI Integration Platform

An event-driven backend automation platform that ingests external webhooks,
manages incident tickets, orchestrates workflow automation, and applies
AI-assisted decision logic to automatically escalate critical incidents.

This project reflects real-world backend systems used in **Managed Service Providers (MSPs)**,
monitoring platforms, IT operations, and service desk automation.

---

## Project Goals

- Ingest and process webhooks from external vendors
- Persist and expose ticket data through REST APIs
- Automate escalation logic using workflow orchestration (n8n)
- Integrate external APIs using API key authentication
- Apply AI-based analysis to support automated decisions
- Demonstrate clean backend architecture and best practices

---

## Tech Stack

- **FastAPI** — Backend framework
- **SQLModel** — ORM and data modeling
- **SQLite** — Local persistence layer
- **n8n** — Workflow automation (Docker)
- **httpx** — Async HTTP client
- **Pydantic** — Data validation
- **Docker Compose** — Infrastructure orchestration

---

## Architecture Overview

Vendor
|
v
FastAPI (Source of Truth)
|
+--> Database (Tickets & Events)
|
+--> n8n Workflow
|
+--> AI Analysis
|
+--> Backend Update


**FastAPI owns the data and state.**  
**n8n orchestrates automation workflows.**

---

## Features

### Vendor Webhook Ingestion
- Receives ticket events from external systems
- Creates and updates tickets
- Ensures idempotent processing

### Ticket Management (CRUD)
- Create, list, and update tickets
- Support for internal IDs and external vendor IDs
- RESTful endpoints with proper status codes

### Automated Escalation (n8n)
- Backend-triggered workflows
- Priority-based conditional logic
- Automatic escalation without manual intervention

### AI-Based Ticket Analysis (Mock)
- Analyzes ticket content
- Determines urgency and sentiment
- Easily replaceable with real LLM services

### External API Integration
- API key–protected endpoints
- Simulated third-party service consumption
- Robust error handling and timeouts

---

## Running Locally

### Backend

uvicorn app.main:app --reload
n8n (Docker)
docker compose up
n8n UI
http://localhost:5678

Health Check
Endpoint

GET /health
Response

{
  "status": "ok"
}
