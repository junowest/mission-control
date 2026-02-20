# Mission Control Dashboard — Build Brief

## What is this?
A real-time mission control dashboard for "Juno" — an AI operator managing LeanVox.com, a TTS API startup.
Juno runs a team of AI sub-agents (marketing, content, SEO, outreach, analytics).
This dashboard gives the human founder ("Boss") full visibility into what's happening.

## Tech Stack
- **Framework:** Plain HTML + Vanilla JS (NO build tools, NO npm — must run with just `npx serve` or direct file open)
- **Styling:** Tailwind CSS via CDN
- **State:** Reads from `/state/status.json` (relative path — same origin)
- **Charts:** Chart.js via CDN

## Data Format — `/state/status.json`
```json
{
  "lastUpdated": "2026-02-20T15:00:00Z",
  "mission": {
    "goal": "100 users in 30 days",
    "daysRemaining": 30,
    "currentUsers": 0,
    "targetUsers": 100,
    "startDate": "2026-02-20"
  },
  "agents": [
    {
      "id": "juno",
      "name": "Juno",
      "role": "Mission Commander",
      "emoji": "🚀",
      "status": "active",
      "currentTask": "Coordinating marketing team launch",
      "lastSeen": "2026-02-20T15:25:00Z",
      "tasksCompleted": 0,
      "tasksTotal": 0
    },
    {
      "id": "content",
      "name": "Content Agent",
      "role": "Content & Copywriting",
      "emoji": "✍️",
      "status": "idle",
      "currentTask": null,
      "lastSeen": null,
      "tasksCompleted": 0,
      "tasksTotal": 0
    },
    {
      "id": "seo",
      "name": "SEO Agent",
      "role": "SEO & Growth Hacking",
      "emoji": "📈",
      "status": "idle",
      "currentTask": null,
      "lastSeen": null,
      "tasksCompleted": 0,
      "tasksTotal": 0
    },
    {
      "id": "outreach",
      "name": "Outreach Agent",
      "role": "Dev Community Outreach",
      "emoji": "📡",
      "status": "idle",
      "currentTask": null,
      "lastSeen": null,
      "tasksCompleted": 0,
      "tasksTotal": 0
    },
    {
      "id": "analytics",
      "name": "Analytics Agent",
      "role": "Metrics & Reporting",
      "emoji": "📊",
      "status": "idle",
      "currentTask": null,
      "lastSeen": null,
      "tasksCompleted": 0,
      "tasksTotal": 0
    }
  ],
  "tasks": [
    {
      "id": "task-001",
      "title": "Define marketing strategy",
      "description": "Identify top channels: HN, Reddit, Twitter/X, ProductHunt, dev Discord servers",
      "assignedTo": "juno",
      "status": "in-progress",
      "priority": "high",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:25:00Z"
    },
    {
      "id": "task-002",
      "title": "Build Mission Control Dashboard",
      "description": "Create visibility dashboard for Boss to track agent activity and progress",
      "assignedTo": "juno",
      "status": "in-progress",
      "priority": "high",
      "createdAt": "2026-02-20T15:25:00Z",
      "updatedAt": "2026-02-20T15:25:00Z"
    },
    {
      "id": "task-003",
      "title": "Write launch blog post",
      "description": "SEO-optimized post: 'ElevenLabs alternative at 1/10th the cost'",
      "assignedTo": "content",
      "status": "todo",
      "priority": "high",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:00:00Z"
    },
    {
      "id": "task-004",
      "title": "Reddit launch post (r/selfhosted, r/MachineLearning, r/webdev)",
      "description": "Craft genuine helpful posts, not ads. Show benchmarks vs ElevenLabs.",
      "assignedTo": "outreach",
      "status": "todo",
      "priority": "high",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:00:00Z"
    },
    {
      "id": "task-005",
      "title": "Product Hunt launch preparation",
      "description": "Prepare assets, tagline, screenshots, GIF demo for PH submission",
      "assignedTo": "content",
      "status": "todo",
      "priority": "medium",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:00:00Z"
    },
    {
      "id": "task-006",
      "title": "SEO keyword research",
      "description": "Target: 'ElevenLabs alternative', 'cheap TTS API', 'voice cloning API free'",
      "assignedTo": "seo",
      "status": "todo",
      "priority": "medium",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:00:00Z"
    },
    {
      "id": "task-007",
      "title": "Set up analytics tracking",
      "description": "Track signups, API calls, conversion funnel from landing page",
      "assignedTo": "analytics",
      "status": "todo",
      "priority": "medium",
      "createdAt": "2026-02-20T15:00:00Z",
      "updatedAt": "2026-02-20T15:00:00Z"
    }
  ],
  "activity": [
    {
      "timestamp": "2026-02-20T15:26:00Z",
      "agent": "Juno",
      "emoji": "🚀",
      "message": "Mission Control Dashboard build initiated"
    },
    {
      "timestamp": "2026-02-20T15:25:00Z",
      "agent": "Juno",
      "emoji": "🚀",
      "message": "Boss approved marketing team launch — target: 100 users in 30 days"
    },
    {
      "timestamp": "2026-02-20T10:50:00Z",
      "agent": "Juno",
      "emoji": "🚀",
      "message": "Telegram channel connected — comms live"
    },
    {
      "timestamp": "2026-02-20T09:58:00Z",
      "agent": "Juno",
      "emoji": "🚀",
      "message": "Switched model to claude-sonnet-4-6 — token usage optimized"
    }
  ],
  "metrics": {
    "signupsToday": 0,
    "signupsTotal": 0,
    "apiCallsToday": 0,
    "conversionRate": 0,
    "dailySignups": []
  }
}
```

## Dashboard UI Requirements

### Layout
- Full-screen dark theme (bg: #0f0f13, accent: electric blue #3b82f6, green #22c55e)
- Fixed header: "🚀 LeanVox Mission Control" + live clock + days remaining badge
- Auto-refresh every 30 seconds (fetch status.json)

### Sections (top to bottom)

#### 1. Mission Stats Bar (top)
4 big stat cards in a row:
- 🎯 Users Progress: "0 / 100" with a progress bar
- 📅 Days Remaining: countdown
- ✅ Tasks Done: "X / Y"
- ⚡ Active Agents: count of agents with status="active"

#### 2. Agent Grid
Card per agent showing:
- Emoji + Name + Role
- Status badge: green pulse dot for "active", gray for "idle", blue for "thinking", red for "error"
- Current task (or "Standing by" if idle)
- Last seen timestamp
- Tasks completed / total mini progress bar

#### 3. Task Board (Kanban style, 3 columns)
- **TODO** | **IN PROGRESS** | **DONE**
- Each task card: priority badge (high=red, medium=yellow, low=green), title, assigned agent emoji + name, time ago
- Smooth, compact cards

#### 4. Signups Chart
- Line chart (Chart.js) showing daily signups over the mission period
- Target line at ~3.33/day to hit 100 in 30 days
- Empty/placeholder state if no data yet

#### 5. Activity Feed
- Live scrolling feed of recent activity
- Each entry: timestamp (relative "2m ago"), agent emoji+name, message
- Max 20 entries shown, newest first

## Code Style
- Single `index.html` file — everything inline (HTML + CSS + JS)
- Tailwind CSS via CDN
- Chart.js via CDN
- No external dependencies that need npm
- Fetch `/state/status.json` on load and every 30s
- Show "Last updated: X seconds ago" in header
- Handle fetch errors gracefully (show stale data warning)
- Mobile-responsive (stacks vertically on small screens)

## Files to Create
1. `index.html` — the full dashboard
2. `state/status.json` — the initial state (copy from the JSON above)
3. `README.md` — how to run: `npx serve .` or `python3 -m http.server`

## Quality Bar
This is the founder's command center. Make it look GOOD:
- Dark glassmorphism cards (bg rgba with backdrop-blur)
- Subtle animations (pulse on active agents, fade-in on load)
- Clean typography, good spacing
- Green progress fill on the mission bar
- The kind of dashboard that makes someone feel in control

When completely finished, run this command to notify:
openclaw system event --text "Done: Mission Control Dashboard built at /home/sandbox/.openclaw/workspace/mission-control/" --mode now
