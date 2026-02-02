# API Documentation

## POST /webhooks/vendor
Receives vendor ticket events.

```json
{
  "ticket_id": "INC-100",
  "status": "open",
  "priority": "high",
  "description": "Production outage"
}
