# Deployment Plan

## Project: Python Task Manager App

---

## 1. Deployment Strategy

**Selected Strategy:** Direct Deployment to a cloud platform (Railway / Render / PythonAnywhere)

The application is a Python-based task manager. It will be deployed as a web service using **Flask** as a lightweight web layer, making the task manager accessible via browser.

---

## 2. Prerequisites

- Python 3.10+
- pip / pipenv
- Git (repo must be pushed to GitHub)
- Account on deployment platform (e.g., Render.com)

---

## 3. Deployment Steps

### Step 1 — Prepare the app
- Ensure `src/task_manager.py` is production-ready
- Create a simple `app.py` Flask wrapper if needed
- Create `requirements.txt`:
  ```
  flask
  pytest
  ```

### Step 2 — Push to GitHub
```bash
git add .
git commit -m "feat: prepare app for deployment v0.5"
git push origin dev
```

### Step 3 — Deploy to Render.com
1. Go to https://render.com and sign in
2. Click **New → Web Service**
3. Connect your GitHub repository
4. Set:
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `python app.py`
5. Click **Deploy**

### Step 4 — Verify Deployment
- Open the provided Render URL
- Test all task features (create, view, complete, delete)
- Confirm the system is live and functional

---

## 4. Rollback Steps

If deployment fails or causes critical issues:

1. Go to Render dashboard → Select service
2. Click **Rollback** to previous successful deploy
3. OR re-deploy the last known good commit:
   ```bash
   git revert HEAD
   git push origin dev
   ```
4. Notify the team immediately via team chat
5. Log the incident in the defect log

---

## 5. Post-Deployment Checklist

- [ ] App is accessible via public URL
- [ ] All features work as expected
- [ ] No critical errors in logs
- [ ] Team notified of deployment success
- [ ] URL documented and shared with stakeholders
