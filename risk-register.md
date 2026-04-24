# Risk Register

## Project: Python Task Manager App

---

## Risk Scoring Guide

| Likelihood | Score | Impact   | Score |
|------------|-------|----------|-------|
| Low        | 1     | Low      | 1     |
| Medium     | 2     | Medium   | 2     |
| High       | 3     | High     | 3     |

**Risk Score = Likelihood × Impact**

---

## Risk Register Table

| ID   | Risk Description                              | Likelihood | Impact | Risk Score | Mitigation Plan                                                  | Owner    | Status  |
|------|-----------------------------------------------|------------|--------|------------|------------------------------------------------------------------|----------|---------|
| R-01 | Team member unavailable due to illness        | 2          | 3      | 6          | Cross-train team members; redistribute tasks during standup      | Member A | Open    |
| R-02 | Scope creep from added features mid-sprint    | 3          | 2      | 6          | Strict sprint planning; new items go to backlog, not current sprint | Member A | Open |
| R-03 | Database corruption or data loss              | 1          | 3      | 3          | Regular backups; use version-controlled migrations               | Member B | Open    |
| R-04 | Integration issues between frontend and backend | 2        | 2      | 4          | Define API contracts early; integration tests in CI              | Member C | Open    |
| R-05 | Deployment failure on target platform         | 2          | 3      | 6          | Test deployment in staging environment before production         | Member D | Open    |
| R-06 | Security vulnerability in user authentication | 2          | 3      | 6          | Use hashed passwords (bcrypt); follow OWASP guidelines           | Member B | Open    |
| R-07 | Low test coverage leads to undetected bugs    | 2          | 2      | 4          | Set minimum 80% code coverage requirement; enforce in CI         | Member D | Open    |
| R-08 | Third-party library deprecation or breaking change | 1     | 2      | 2          | Pin dependency versions; review changelogs before updates        | Member B | Open    |

---

## Risk Summary

| Risk Score Range | Level    |
|------------------|----------|
| 7–9              | 🔴 High   |
| 4–6              | 🟡 Medium |
| 1–3              | 🟢 Low    |

| ID   | Risk                          | Score | Level  |
|------|-------------------------------|-------|--------|
| R-01 | Team member illness           | 6     | 🟡 Medium |
| R-02 | Scope creep                   | 6     | 🟡 Medium |
| R-03 | Database corruption           | 3     | 🟢 Low    |
| R-04 | Integration issues            | 4     | 🟡 Medium |
| R-05 | Deployment failure            | 6     | 🟡 Medium |
| R-06 | Security vulnerability        | 6     | 🟡 Medium |
| R-07 | Low test coverage             | 4     | 🟡 Medium |
| R-08 | Library deprecation           | 2     | 🟢 Low    |

---

## Risk Review Schedule

- Risks reviewed at every Sprint Review
- New risks can be added at any time by any team member
- Owner is responsible for updating mitigation status
