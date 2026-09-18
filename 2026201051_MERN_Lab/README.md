# Student Notes CRUD Micro-App (MERN Stack)

A decoupled full-stack notes manager: Express + MongoDB (via Mongoose) on the backend,
React (Vite) + Axios on the frontend.

## Candidate Details
- Student Name: _fill in_
- Student ID: _fill in_
- GitHub Repository: _fill in_

## Tech Stack
- **Backend:** Node.js, Express, Mongoose, CORS
- **Frontend:** React (Vite), Axios
- **Database:** MongoDB (local, `mongodb://localhost:27017/notes_db`)

## Project Structure
```
notes-app/
├── server/          # Express + MongoDB backend
│   ├── config/db.js
│   ├── models/Note.js
│   ├── routes/noteRoutes.js
│   ├── server.js
│   └── package.json
├── client/          # Vite + React frontend
│   └── src/
│       ├── App.jsx
│       ├── main.jsx
│       └── index.css
└── screenshots/     # Proof of CRUD functionality
```

## Setup & Run Instructions

### Prerequisites
- Node.js installed
- MongoDB running locally on the default port (`27017`)

### 1. Start MongoDB
Make sure a local `mongod` process is running before starting the server.

### 2. Backend Setup
```bash
cd server
npm install
npm start
```
The API will be available at `http://localhost:5000/api/notes`.

### 3. Frontend Setup
In a separate terminal:
```bash
cd client
npm install
npm run dev
```
The app will be available at `http://localhost:5173`.

## API Endpoints
| Method | Endpoint          | Description                        |
|--------|-------------------|-------------------------------------|
| GET    | `/api/notes`      | Fetch all notes (newest first)      |
| POST   | `/api/notes`      | Create a new note                   |
| DELETE | `/api/notes/:id`  | Delete a note by its MongoDB `_id`  |

## Notes
- CORS is enabled on the server so the Vite dev server (port 5173) can call the API (port 5000).
- The client shows a loading indicator while notes are being fetched and a friendly
  empty-state message ("No notes yet — add one above!") when there are none.
- Deleting a note updates local state immediately, no full page refresh required.
