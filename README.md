# My First Todo Web App

This is a simple Todo web app built with Python and Flask. It lets you add tasks, mark them as done, and delete them. Everything is saved so your todos are still there when you close and reopen the app.

---

## What We Used to Build This

- **Python** — the programming language everything runs on
- **Flask** — a Python tool that lets us build websites
- **SQLite** — a tiny built-in database that saves your todos to a file on your computer
- **HTML** — the structure of the web page (what you see)
- **CSS** — the styling of the web page (how it looks)

---

## Step 1 — Check That Python Is Installed

Before building anything, we needed to make sure Python was already on the computer.

We opened the terminal (the black command window) and typed:

```
python --version
```

It showed us: `Python 3.14.6` — that means Python is installed and ready.

We also checked pip (pip is the tool that lets you install extra Python tools):

```
pip --version
```

It showed us: `pip 26.1.2` — pip is also ready.

---

## Step 2 — Install Flask

Flask does not come with Python by default, so we had to install it. Think of it like downloading an app on your phone.

We typed this in the terminal:

```
pip install flask
```

The computer went online, downloaded Flask, and installed it automatically.

---

## Step 3 — Create the Project Folder

Our project lives in this folder on the computer:

```
C:\Users\Bahati\PROJECTS\FIRST\
```

Inside it, we created two more folders:

- **templates** — this is where the HTML file (the web page) lives
- **static** — this is where the CSS file (the styling) lives

---

## Step 4 — Create the Files

We created three files that make the app work:

### File 1: `app.py` (the brain of the app)

This is the Python file. It is the heart of the whole app. It does four things:

1. **Shows the homepage** — loads all your todos from the database and displays them
2. **Adds a todo** — when you type something and click Add, it saves it to the database
3. **Toggles done/undone** — when you click the checkmark, it marks the todo as complete or incomplete
4. **Deletes a todo** — when you click the X, it removes the todo from the database

### File 2: `templates/index.html` (the web page)

This is what you actually see in the browser. It has:

- A heading that says "My Todos"
- A text box where you type your new todo
- An "Add" button
- A list of all your current todos
- A checkmark icon next to each todo (click it to mark done)
- An X icon next to each todo (click it to delete)

### File 3: `static/style.css` (the looks)

This file makes the app look nice. Without it, the page would just be plain black text on a white background. With it, you get:

- A clean white card in the center of the page
- A purple "Add" button
- A strikethrough on completed todos
- A red X for delete

---

## Step 5 — Run the App

To start the app, open your terminal, and type:

```
python C:\Users\Bahati\PROJECTS\FIRST\app.py
```

You will see something like this in the terminal:

```
 * Running on http://127.0.0.1:5000
```

That means the app is running. Do not close the terminal — closing it stops the app.

---

## Step 6 — Open It in Your Browser

Open any web browser (Chrome, Edge, Firefox) and go to this address:

```
http://127.0.0.1:5000
```

Think of `127.0.0.1` as "this computer" and `5000` as the door number. You are visiting your own app on your own computer.

---

## How to Use the App

1. **Add a todo** — type something in the box and click the purple "Add" button
2. **Mark as done** — click the `○` circle next to a todo. It turns into a `✓` and the text gets crossed out
3. **Mark as undone** — click the `✓` again to undo it
4. **Delete a todo** — click the red `✕` next to a todo to remove it forever

---

## Your File Structure

Here is what the project folder looks like and what each file does:

```
FIRST/
│
├── app.py               ← The Python brain (runs the whole app)
├── todos.db             ← The database file (created automatically when you first run the app)
│
├── templates/
│   └── index.html       ← The web page you see in the browser
│
└── static/
    └── style.css        ← The colors, fonts, and layout styling
```

---

## How to Stop the App

Go back to the terminal where the app is running and press:

```
Ctrl + C
```

That stops the server. Your todos are still saved in the `todos.db` file and will be there next time you run the app.

---

## How to Start Again Next Time

Every time you want to use the app, just open your terminal and run:

```
python C:\Users\Bahati\PROJECTS\FIRST\app.py
```

Then visit `http://127.0.0.1:5000` in your browser. That is it!

---

## Step 7 — Putting the Project on GitHub

GitHub is a website where developers store and share their code. Think of it like Google Drive but for code. Here is exactly what we did to get this project there.

### 7a — Install Git

Git is a tool that tracks changes to your code. We checked it was installed by running:

```
git --version
```

It showed: `git version 2.54.0` — git is ready.

### 7b — Install the GitHub CLI

The GitHub CLI (command line interface) lets us talk to GitHub from the terminal without using the website. We installed it by running:

```
winget install --id GitHub.cli -e --silent
```

### 7c — Log In to GitHub

We connected the GitHub CLI to our GitHub account by running:

```
gh auth login
```

A browser window opened. We chose:
- **GitHub.com**
- **HTTPS**
- **Login with a web browser**

Then signed in and came back to the terminal.

### 7d — Initialize Git in the Project Folder

Git needs to be told which folder to track. We ran this inside the project folder:

```
git init
```

This created a hidden `.git` folder that Git uses to track everything.

### 7e — Create a `.gitignore` File

Some files should never be pushed to GitHub — like your database (it contains your personal data) and tool config folders. We created a file called `.gitignore` that tells Git to ignore these:

```
todos.db
__pycache__/
*.pyc
.env
.claude/
graphify-out/
```

### 7f — Stage the Files

Staging means telling Git "these are the files I want to save". We ran:

```
git add .gitignore README.md app.py static/style.css templates/index.html
```

### 7g — Commit the Files

A commit is like taking a snapshot of your project at this moment in time. We ran:

```
git commit -m "Initial todo web app with Flask, SQLite, HTML and CSS"
```

### 7h — Create the GitHub Repo and Push

This command created a new public repository on GitHub called `todo-app`, connected it to our local project, and uploaded everything:

```
gh repo create todo-app --public --source=. --remote=origin --push
```

### The project is now live at:

```
https://github.com/martinotim3/todo-app
```

---

## How to Push Changes in the Future

Every time you make a change to the app and want to save it to GitHub, run these three commands:

```
git add .
git commit -m "Describe what you changed here"
git push
```

That is it — your changes will appear on GitHub within seconds.
