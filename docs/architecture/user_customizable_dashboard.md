# User Customizable Dashboard (Persistence)

## Backend Storage

Backend DB (Postgres/TimescaleDB) stores dashboard configs per user:

```json
{
  "user_id": "...",
  "dashboard_id": "...",
  "layout": [{widget: "SIEM", metrics: ["latency", "errors"], position: {...}}],
  "filters": {time: "last_24h", severity: "critical"},
  "permissions": ["view_SIEM", "edit_layout"]
}
```

## Implementation Steps

1. Implement backend CRUD endpoints for these dashboard configurations.
2. Automatically load personalized views upon login.