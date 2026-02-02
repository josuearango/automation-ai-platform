

# Workflow Automation (n8n)

## Production Workflow

1. Webhook triggered by backend
2. IF node checks ticket priority
3. AI endpoint analyzes ticket content
4. PATCH request updates ticket status

---

## Test Mode vs Production

### Test Mode
- Uses `webhook-test`
- Requires tickets to exist before PATCH
- Used for isolated debugging

### Production Mode
- Uses production webhook
- Tickets are always created before automation
- Fully end-to-end flow

---

## Error Handling

- PATCH failures return HTTP 404 or 502
- External API failures are translated to 502
- n8n execution logs provide traceability

---

## Why n8n?

- Visual workflow design
- Easy to modify automation rules
- Decouples business logic from backend code
