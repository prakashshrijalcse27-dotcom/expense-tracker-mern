# Expense Tracker MERN

A simple full-stack **Expense Tracker** built with the **MERN stack** (MongoDB, Express.js, React, Node.js). The application lets you add income and expense transactions, view totals and balance, see transaction history, and delete transactions.

## Features

- Dashboard with total income, total expense, balance, and transaction chart
- Add income transactions
- Add expense transactions
- Transaction categories, dates, amounts, and references/descriptions
- View recent transaction history
- Delete income and expense records
- MongoDB persistence
- React frontend + Express/Node.js backend

## Tech Stack

- **Frontend:** React, Axios, Styled Components, Chart.js, React Datepicker
- **Backend:** Node.js, Express.js, Mongoose, CORS, Dotenv
- **Database:** MongoDB Atlas / MongoDB

## Project Structure

```text
expense-tracker-mern/
├── backend/
│   ├── controllers/
│   ├── db/
│   ├── models/
│   ├── routes/
│   ├── app.js
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
├── .gitignore
└── README.md
```

## Prerequisites

Install these before running the project:

- Node.js
- npm
- MongoDB Atlas account (recommended) or a local MongoDB server
- Git

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/prakashshrijalcse27-dotcom/expense-tracker-mern.git
cd expense-tracker-mern
```

### 2. Install backend dependencies

```bash
cd backend
npm install
```

### 3. Create the backend `.env` file

Create this file:

```text
backend/.env
```

Add:

```env
PORT=5000
MONGO_URL=mongodb+srv://YOUR_DB_USERNAME:YOUR_DB_PASSWORD@YOUR_CLUSTER.mongodb.net/expenseTracker?retryWrites=true&w=majority
```

Replace these placeholders:

- `YOUR_DB_USERNAME` → MongoDB database user name
- `YOUR_DB_PASSWORD` → MongoDB database user password
- `YOUR_CLUSTER` → your MongoDB Atlas cluster host

### MongoDB Atlas setup

1. Create a MongoDB Atlas cluster.
2. Create a **Database User** and remember its username/password.
3. In **Network Access**, allow the IP address of the machine running the backend.
4. Copy the Atlas connection string from **Connect → Drivers**.
5. Put the connection string into `MONGO_URL` in `backend/.env`.
6. Keep `backend/.env` private. **Never commit database credentials to GitHub.**

If the database password contains special URL characters such as `@`, `#`, `%`, `:`, `/`, or `?`, URL-encode the password before putting it in the MongoDB URI.

### 4. Start the backend

Open a terminal in the `backend` folder:

```bash
npm start
```

You should see messages similar to:

```text
listening on port: 5000
Db Connected
```

If PowerShell blocks `npm`, use:

```powershell
npm.cmd start
```

### 5. Install frontend dependencies

Open another terminal and go to the frontend folder:

```bash
cd frontend
npm install
```

### 6. Start the frontend

```bash
npm start
```

If PowerShell blocks `npm`, use:

```powershell
npm.cmd start
```

The frontend runs at:

```text
http://localhost:3000
```

## Running the project every time

Use **two terminals**:

### Terminal 1 — Backend

```bash
cd backend
npm start
```

### Terminal 2 — Frontend

```bash
cd frontend
npm start
```

Keep both terminals running while using the application.

## Environment Variables

The backend requires:

| Variable | Example | Description |
|---|---|---|
| `PORT` | `5000` | Port used by the Express backend |
| `MONGO_URL` | `mongodb+srv://...` | MongoDB connection string |

Do **not** put real passwords, API keys, or other secrets in this README or anywhere in the Git repository.

## Important Security Notes

- `backend/.env` must remain local and private.
- Never push MongoDB usernames/passwords to GitHub.
- If a database password is accidentally exposed, rotate/change it immediately.
- Do not use `0.0.0.0/0` in MongoDB Atlas Network Access unless you understand the security implications; allowing only the required IP address is safer.

## Data Persistence

Transaction data is stored in MongoDB, so closing the browser or stopping the frontend does **not** delete saved transactions. When the backend and frontend are started again, the application reads the stored data from MongoDB.

This project currently does **not** implement a full authentication system with separate user accounts. Data is therefore not isolated per login/user.

## Common Problems

### `listening on port: undefined`

Check that `backend/.env` exists and contains:

```env
PORT=5000
```

### `DB Connection Error`

Check:

- `MONGO_URL` is correct
- MongoDB database username/password are correct
- MongoDB Atlas Network Access allows the current machine's IP
- Special characters in the password are URL-encoded

### `npm` is not recognized in PowerShell

Try the Windows command:

```powershell
npm.cmd install
npm.cmd start
```

### Frontend shows `Infinity` or `0`

Make sure:

1. The backend is running on port `5000`.
2. MongoDB shows `Db Connected` in the backend terminal.
3. At least one valid income/expense transaction has been added.

## GitHub Workflow

After making code changes:

```bash
git status
git add .
git commit -m "Describe your changes"
git push
```

Before committing, verify that `.env` is not being tracked:

```bash
git status
```

## Original Project Credit

This repository is based on the original **Expense Tracker** project by **Darshan Jain**. The code has been set up and configured for local development and GitHub use in this repository.
