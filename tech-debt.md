# Technical Debt Register

## Project: Python Task Manager App

---

## What is Technical Debt?

Technical debt refers to shortcuts or suboptimal decisions made during development that need to be addressed later. Ignoring technical debt leads to slower development, more bugs, and harder-to-maintain code.

---

## Technical Debt Items

### TD-001 — In-Memory Storage (No Persistence)
- **Description:** All tasks are stored in a Python dictionary in memory. Data is lost when the app restarts.
- **Impact:** High — users lose all data on every restart
- **Effort to Fix:** Medium
- **Plan:** Replace in-memory storage with SQLite using Python's built-in `sqlite3` module

---

### TD-002 — No Input Sanitization Beyond Title Validation
- **Description:** Only task title is validated. Description, due date, and other fields have no input validation.
- **Impact:** Medium — invalid data can be stored silently
- **Effort to Fix:** Low
- **Plan:** Add validation functions for all input fields; raise `ValueError` for invalid formats

---

### TD-003 — No Logging System
- **Description:** The app has no logging. Errors and events are not recorded anywhere.
- **Impact:** Medium — debugging production issues is very difficult
- **Effort to Fix:** Low
- **Plan:** Integrate Python's `logging` module; log key events (task created, deleted, errors)

---

### TD-004 — No User Authentication
- **Description:** There is no login system. All tasks belong to a single unnamed user.
- **Impact:** High — cannot be used as a multi-user system
- **Effort to Fix:** High
- **Plan:** Implement user registration and login with hashed passwords (bcrypt)

---

### TD-005 — Hardcoded Task ID Counter
- **Description:** The `_next_id` counter in `TaskManager` resets on every restart, which could cause ID collisions when persistence is added.
- **Impact:** Medium — will cause bugs when database is introduced
- **Effort to Fix:** Low
- **Plan:** Use database-generated IDs (auto-increment) or UUIDs instead of a manual counter

---

## Selected Debt to Fix This Sprint

### ✅ TD-002 — No Input Sanitization Beyond Title Validation

**Why selected:** Low effort, high impact on data integrity. Directly caused BUG-01 and may cause similar bugs in other fields.

**Refactoring done:**
- Added `ValueError` for empty/whitespace task titles in `add_task()`
- Added unit tests confirming validation works
- Code is cleaner and more defensive

**Before:**
```python
def add_task(self, title, description="", due_date=None):
    task = Task(self._next_id, title, description, due_date)
    ...
```

**After:**
```python
def add_task(self, title, description="", due_date=None):
    if not title or not title.strip():
        raise ValueError("Task title cannot be empty.")
    task = Task(self._next_id, title.strip(), description, due_date)
    ...
```

**Status:** ✅ Fixed and tested
