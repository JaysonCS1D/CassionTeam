# Defect Log

## Project: Python Task Manager App

---

## Defect Log Table

| ID    | Title                          | Severity | Found By | Date Found  | Description                                                                 | Steps to Reproduce                                              | Fix Applied                                              | Status |
|-------|-------------------------------|----------|----------|-------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------|----------------------------------------------------------|--------|
| BUG-01 | Empty title accepted as task | High     | Dev B    | 2026-04-24  | TaskManager.add_task() accepted empty strings and whitespace-only titles, creating invalid tasks with no meaningful content. | 1. Call `manager.add_task("")` or `manager.add_task("   ")` 2. Observe task is created without error | Added validation in `add_task()`: raises `ValueError` if title is empty or whitespace-only. Unit test `test_add_task_empty_title_raises` confirms fix. | Closed |

---

## Defect Details

### BUG-01 — Empty title accepted as task

- **ID:** BUG-01
- **Title:** Empty title accepted as task
- **Severity:** High
- **Found By:** Dev B (during unit testing)
- **Date Found:** 2026-04-24
- **Date Fixed:** 2026-04-24
- **Fixed By:** Dev B

**Description:**  
The `add_task()` method in `TaskManager` did not validate the task title input. An empty string `""` or a whitespace-only string `"   "` was accepted and stored as a valid task, which caused data integrity issues.

**Steps to Reproduce:**
1. Create a `TaskManager` instance
2. Call `manager.add_task("")` or `manager.add_task("   ")`
3. Observe that a task is created without raising an error

**Expected Behavior:**  
A `ValueError` should be raised when the title is empty or contains only whitespace.

**Actual Behavior:**  
No error raised; invalid task stored.

**Fix Applied:**  
Added input validation at the start of `add_task()`:
```python
if not title or not title.strip():
    raise ValueError("Task title cannot be empty.")
```

**Verification:**  
- Unit tests `test_add_task_empty_title_raises` and `test_add_task_whitespace_title_raises` both pass
- Regression: all 15 unit tests pass after fix

**Status:** ✅ Closed
