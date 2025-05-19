# Warmth.Care

**Warmth.Care** is a confidential online platform for mental well-being and emotional support, featuring an AI-powered chatbot ("Miss Warmth") that provides 24/7 guidance and a safe space for users. The project is built with a React + Vite frontend and an Express + MongoDB backend.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [API Endpoints](#api-endpoints)
- [Tech Stack](#tech-stack)
- [License](#license)

---

## Features

- **Confidential Chat**: Secure, private conversations with an AI chatbot for mental health support.
- **User Authentication**: Sign up, log in, and incognito/guest access.
- **Persistent Chat History**: Authenticated users can view their chat history.
- **AI-Powered Responses**: Integrates with OpenAI for empathetic, context-aware replies.
- **Responsive UI**: Modern, mobile-friendly design using Tailwind CSS and DaisyUI.
- **Profile Avatars**: Users can upload a profile picture during sign-up.
- **404 Handling**: Friendly not-found page for invalid routes.

---

## Project Structure

```
warmth-care/
├── backend/         # Express.js API, MongoDB models, routes, controllers
├── frontend/        # React app (Vite, Tailwind, DaisyUI)
├── package.json     # Root scripts for build/start
└── README.md        # Project documentation
```

---

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- npm
- MongoDB instance (local or cloud)

### 1. Clone the repository

```bash
git clone <repo-url>
cd warmth-care
```

### 2. Install dependencies

```bash
# Install backend and frontend dependencies
npm run build
```

### 3. Set up environment variables

Create a `.env` file in `backend/` with:

```
MONGODB_URI=<your-mongodb-uri>
PORT=3000
NODE_ENV=development
OPENAI_API_KEY=<your-openai-api-key>
```

For the frontend, create a `.env` file in `frontend/` with:

```
VITE_WARMTH_CARE_BOT_ID=<bot-user-id>
```

### 4. Start the application

```bash
# Start backend server
npm start

# In a separate terminal, start the frontend (optional, for development)
cd frontend
npm run dev
```

The frontend will be available at [http://localhost:5173](http://localhost:5173) and the backend at [http://localhost:3000](http://localhost:3000).

---

## API Endpoints

### User

- `POST /api/user/signup` — Register a new user
- `POST /api/user/login` — Log in
- `POST /api/user/logout` — Log out
- `GET /api/user/auth/check` — Check authentication (requires token)

### Chat

- `GET /api/chat/` — Fetch chat (requires token)

### Message

- `GET /api/message/users` — Get users for sidebar (requires token)
- `GET /api/message/chat/:id` — Get messages for a chat (requires token)
- `POST /api/message/send/:id` — Send a message (requires token)
- `DELETE /api/message/delete` — Delete messages (requires token)

---

## Tech Stack

- **Frontend**: React, Vite, Tailwind CSS, DaisyUI, Zustand, Axios, React Router, React Toastify, Typewriter Effect
- **Backend**: Node.js, Express, MongoDB, Mongoose, JWT, bcrypt, dotenv, CORS, cookie-parser
- **AI Integration**: OpenAI API (custom model)
- **Dev Tools**: ESLint, Nodemon

---

## License

This project is licensed under the ISC License.

---

**Note:**  
- For AI features, you must provide your own OpenAI API key.
- Profile pictures are uploaded via Cloudinary (see `SignUp.jsx` for details).
- Guest/Incognito login is supported for quick access.

---
