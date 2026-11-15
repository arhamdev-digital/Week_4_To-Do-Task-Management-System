# TaskFlow — Full Stack Task Manager

Modern task manager built with React, Vite, Node.js, Express and MySQL.

## Requirements
Install Node.js LTS, MySQL Server 8+, MySQL Workbench and VS Code.

## Step 1 — MySQL
Start the Windows MySQL service (usually `MySQL80`). Open MySQL Workbench and connect to Local instance MySQL80. No SQL commands are required: backend creates `taskflow_db`, `users` and `tasks` automatically.

## Step 2 — Backend
Open terminal in `backend`:
```bash
npm install
```
Copy `.env.example` to `.env` and enter your own MySQL password and a private JWT secret:
```env
PORT=5000
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=YOUR_MYSQL_PASSWORD
DB_NAME=taskflow_db
JWT_SECRET=CHANGE_THIS_TO_A_LONG_RANDOM_SECRET
```
Run:
```bash
npm run dev
```
Expected: `MySQL connected`, `Database and tables are ready`, `Server running on http://localhost:5000`.
Keep this terminal open.

## Step 3 — Frontend
Open a SECOND terminal in `frontend`:
```bash
npm install
npm run dev
```
Open `http://localhost:5173`.

## Step 4 — Test
Register an account. Create, edit, complete, search and delete tasks. Refresh and log in again to verify persistence.

## Troubleshooting
- `Access denied`: check DB_USER and DB_PASSWORD in `backend/.env`. Never share your password.
- `ECONNREFUSED 3306`: start MySQL80.
- `Failed to fetch`: make sure backend is running on port 5000.
- The database is automatically created. Do not drop a database containing important data.
