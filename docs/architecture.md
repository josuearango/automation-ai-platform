


# Architecture

## Components

- FastAPI: backend and source of truth
- SQLite: persistence layer
- n8n: workflow orchestration
- AI endpoint: decision service (mock)
- External API: simulated third-party integration

## Data Flow

1. Vendor sends webhook
2. FastAPI stores ticket
3. FastAPI triggers n8n
4. n8n evaluates priority
5. AI analyzes ticket content
6. n8n updates ticket status if required
