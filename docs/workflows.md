


# n8n Workflows

## Production Workflow

- Webhook trigger
- IF priority == high
- AI analysis
- PATCH ticket status

## Test Mode Notes

In test mode, tickets must exist before PATCH operations.
Production webhooks create tickets before automation runs.
