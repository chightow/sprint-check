# sprint-check

Local kanban board for sprint tickets. Zero-dependency Python server.

## Quick start

```bash
python server.py             # starts on localhost:8423
python server.py 9090        # custom port
```

## Architecture

Single-file app (`app.html`) served by a Python stdlib HTTP server (`server.py`). No build step. All JS, CSS, and HTML are inline.

`server.py` exposes:
- `GET /api/tickets` — all tickets except `archived`; add `?all=1` to include archived
- `POST /api/ticket/<id>/status` — update ticket status
- `POST /api/ticket/<id>/body` — update ticket body
- `POST /api/tickets` — create a new ticket
- `GET /api/handoff`, `/api/git`, `/api/why?file=<path>` — sidebar data

## Ticket format

Reads `.tickets/<id>/ticket.md` (YAML frontmatter + markdown body) or flat `.tickets/<id>.md`. Companion docs like `acceptance.md`, `plan.md` are detected automatically.

## Port

Default `127.0.0.1:8423`. Auto-increment if busy. URL printed on startup.
