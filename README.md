# 🚀 LeanVox Mission Control

Real-time dashboard for tracking the 100-users-in-30-days mission.

## Run locally

```bash
cd mission-control
python3 -m http.server 8888
# Open http://localhost:8888
```

## State file

All agent state lives in `state/status.json`. Agents update this file to reflect:
- Their current status (active/idle/thinking/error)
- Current task
- Completed task counts
- Activity log entries

## Auto-refresh

Dashboard fetches `state/status.json` every 30 seconds automatically.
