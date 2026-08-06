# 🚀 Deploy a Python Website on Streamlit Community Cloud

A step-by-step guide for deploying a **Python Streamlit application** to **Streamlit Community Cloud** using **GitHub**.

---

## 📚 Learning Objectives

After completing this tutorial, students will be able to:

- Build and run a Streamlit application locally
- Create a GitHub repository
- Upload a project using Git
- Deploy a Streamlit application
- Update an existing deployment

---

## 📋 Prerequisites

Before starting, install the following:

- Python 3.9 or later
- Git
- A GitHub account
- A Streamlit application

---

# 📁 Project Structure

```

my-streamlit-app/
│
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
└── assets/

````

---

# 🖥️ Step 1 – Install Streamlit

```bash
pip install streamlit
````

Verify installation:

```bash
streamlit hello
```

---

# ▶️ Step 2 – Run the Application Locally

Start your app:

```bash
streamlit run app.py
```

Open:

```
http://localhost:8501
```

Example application:

```python
import streamlit as st

st.title("My First Streamlit App")
st.write("Hello World!")
```

---

# 📦 Step 3 – Create `requirements.txt`

Automatically generate:

```bash
pip freeze > requirements.txt
```

Example:

```text
streamlit
pandas
numpy
matplotlib
scikit-learn
```

---

# 🌐 Step 4 – Create a GitHub Repository

1. Login to GitHub.
2. Click **New Repository**.
3. Enter a repository name.
4. Choose **Public**.
5. Click **Create Repository**.

---

# 📤 Step 5 – Upload Project to GitHub

Initialize Git:

```bash
git init
```

Add files:

```bash
git add .
```

Commit:

```bash
git commit -m "Initial commit"
```

Rename branch:

```bash
git branch -M main
```

Connect repository:

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

Push code:

```bash
git push -u origin main
```

Replace:

* **USERNAME** → Your GitHub username
* **REPOSITORY** → Repository name

---

# ✅ Step 6 – Verify GitHub Repository

Your repository should contain:

```
app.py
requirements.txt
README.md
.gitignore
```

---

# ☁️ Step 7 – Deploy on Streamlit Community Cloud

Visit:

> https://share.streamlit.io

Login with GitHub.

Click:

**New App**

Select:

* Repository
* Branch → `main`
* Main File → `app.py`

Click:

**Deploy**

After a few minutes, Streamlit generates a public URL.

Example:

```
https://your-app-name.streamlit.app
```

---

# 🔄 Updating Your Application

Whenever you modify the project:

```bash
git add .
git commit -m "Updated application"
git push origin main
```

Streamlit automatically redeploys your application.

---

# 💻 Essential Git Commands

| Command                   | Description             |
| ------------------------- | ----------------------- |
| `git init`                | Initialize repository   |
| `git status`              | Check status            |
| `git add .`               | Stage files             |
| `git commit -m "message"` | Commit changes          |
| `git push origin main`    | Upload code             |
| `git pull`                | Download latest changes |

---

# ❌ Common Deployment Error

### Error

```
Unable to deploy

The app’s code is not connected to a remote GitHub repository.
```

### Cause

Your project exists only on your computer.

### Solution

Upload the project to GitHub.

```bash
git add .
git commit -m "Project update"
git push origin main
```

Then redeploy.

---

# 🛠️ Troubleshooting

## ModuleNotFoundError

Update requirements:

```bash
pip freeze > requirements.txt
```

Commit and push:

```bash
git add requirements.txt
git commit -m "Updated requirements"
git push
```

---

## App Does Not Start

Check:

* `app.py` exists
* No Python errors
* Application runs locally

---

## Main File Not Found

Verify the deployment configuration uses the correct file:

```
app.py
```

or

```
streamlit_app.py
```

---

## Deployment Failed

Check:

* Repository is Public
* Branch is `main`
* `requirements.txt` exists
* App works locally

---

# 📌 Best Practices

* ✅ Test locally before deployment
* ✅ Keep `requirements.txt` updated
* ✅ Use meaningful commit messages
* ✅ Never upload passwords or API keys
* ✅ Create a `.gitignore`
* ✅ Keep project files organized

---

# 📚 Deployment Workflow

```text
Develop App
      │
      ▼
Test Locally
      │
      ▼
Create requirements.txt
      │
      ▼
Create GitHub Repository
      │
      ▼
Push Project to GitHub
      │
      ▼
Connect Streamlit Cloud
      │
      ▼
Deploy
      │
      ▼
Share Public URL
```

---

# 🎓 Student Exercise

1. Create a simple Streamlit application.
2. Test it locally.
3. Generate `requirements.txt`.
4. Upload the project to GitHub.
5. Deploy it using Streamlit Community Cloud.
6. Share the deployed URL with your instructor.

---

# 📖 Resources

* GitHub: https://github.com
* Git Documentation: https://git-scm.com/docs
* Streamlit Documentation: https://docs.streamlit.io
* Streamlit Community Cloud: https://share.streamlit.io

---
