# Release Notes

## Python Task Manager App

---

## v0.5 — Sprint 1 Release
**Release Date:** April 24, 2026  
**Tag:** `v0.5`  
**Branch:** `dev`

---

### ✅ New Features

- **Task Creation** — Users can create tasks with a title and optional description
- **View All Tasks** — Retrieve a full list of all tasks in the system
- **Complete Tasks** — Mark any pending task as completed with a timestamp
- **Delete Tasks** — Remove tasks from the manager by ID
- **Search Tasks** — Search tasks by keyword across title and description fields
- **Filter by Status** — Filter tasks by `pending` or `completed` status

---

### 🐛 Bug Fixes

- **BUG-01:** Fixed empty/whitespace-only task titles being accepted. `add_task()` now raises `ValueError` for invalid titles.

---

### 🧪 Testing

- 15 unit tests written using **Pytest**
- All 15 tests passing ✅
- Test coverage covers: task creation, completion, deletion, filtering, and search

---

### 📁 Files Added

| File                        | Description                            |
|-----------------------------|----------------------------------------|
| `src/task_manager.py`       | Core Task and TaskManager classes      |
| `tests/test_task_manager.py`| 15 unit tests using Pytest             |
| `docs/backlog.md`           | Product backlog with 10 user stories   |
| `docs/sprint-1-plan.md`     | Sprint 1 planning document             |
| `docs/team-roles.md`        | Team member roles and responsibilities |
| `docs/risk-register.md`     | 8 identified risks with mitigation     |
| `docs/qa-plan.md`           | QA strategy and test plan              |
| `docs/defect-log.md`        | Defect tracking log                    |
| `docs/release-notes.md`     | This file                              |

---

### ⚠️ Known Limitations (v0.5)

- No persistent storage (data is in-memory only)
- No user authentication yet (planned for v1.0)
- No due date overdue alerting in UI (in backlog)

---

### 🔜 Planned for Next Release (v0.6)

- US-006: Delete task with confirmation
- US-007: Edit task title and description
- US-008: Set task due date with overdue detection
- Persistent storage with SQLite
