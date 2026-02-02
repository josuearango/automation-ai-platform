# API Documentation

## POST /webhooks/vendor
Receives ticket events from external systems.

### Request
```json
{
  "ticket_id": "INC-123",
  "status": "open",
  "priority": "high",
  "description": "Production outage detected"
}
Response
{
  "message": "Webhook processed"
}
GET /tickets
Returns all stored tickets.

POST /tickets
Creates a ticket manually.

PATCH /tickets/external/{external_id}
Updates a ticket using an external identifier.

Request
{
  "status": "escalated"
}
POST /ai/analyze
Analyzes ticket content and returns decision metadata.

Request
{
  "ticket_id": "INC-123",
  "text": "Critical production issue"
}
Response
{
  "ticket_id": "INC-123",
  "sentiment": "negative",
  "urgency": "high",
  "summary": "AI analysis completed for ticket INC-123"
}
GET /external-api/status
Simulated third-party API (requires API key).

Headers
X-API-Key: secret-api-key