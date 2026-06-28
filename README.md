# sprint-check

Local kanban board for sprint tickets. Reads `.tickets/` from any project. Zero dependencies — Python stdlib only.

```
python server.py     # starts on localhost:8423
```

## API

- `GET /api/tickets` — all tickets
- `POST /api/ticket/<id>/status` — update status
- `POST /api/ticket/<id>/body` — update body
- `POST /api/tickets` — create ticket
- `GET /api/handoff` — HANDOFF.md context
- `GET /api/git` — branch, modified count, recent commits
- `GET /api/why?file=<path>` — ticket archaeology for a file

## Origin

Extracted from [canon](https://github.com/sunitghub/canon-skills) by Sunit Joshi (MIT).
