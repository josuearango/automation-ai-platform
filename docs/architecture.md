

# Architecture Documentation

## Overview

The system is designed around a clear separation of responsibilities:

- **FastAPI**: owns application state and persistence
- **n8n**: orchestrates automation workflows
- **AI service**: provides decision support
- **External APIs**: simulate third-party integrations

---

## Core Components

### FastAPI Backend
- Acts as the system’s source of truth
- Stores tickets and related events
- Exposes REST APIs for internal and external consumers

### Database (SQLite)
- Stores tickets (`Ticket`)
- Stores webhook audit logs (`Event`)
- Ensures persistence and traceability

### n8n
- Listens to backend-triggered webhooks
- Executes conditional logic
- Calls internal APIs to update state

### AI Endpoint
- Receives ticket content
- Returns structured analysis
- Enables automation decisions

---

## Data Flow (Detailed)

1. A vendor system sends a webhook
2. FastAPI validates and stores the ticket
3. FastAPI triggers n8n
4. n8n evaluates ticket priority
5. AI endpoint analyzes ticket content
6. n8n escalates ticket if required
7. Ticket status is updated in the database

---

## Design Principles

- **Single Source of Truth**: only FastAPI mutates data
- **Loose Coupling**: n8n communicates via HTTP only
- **Idempotency**: repeated vendor events do not corrupt data
- **Extensibility**: components can be swapped independently
