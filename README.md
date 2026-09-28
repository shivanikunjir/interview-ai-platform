# Interview AI Platform

An AI-powered interview preparation app. Paste a job description and describe your profile, and the app uses Google Gemini to generate a personalized interview strategy: likely interview questions, skill-gap analysis, and a preparation plan.

## Problem

Candidates often don't know what a specific job will test them on or where their skills fall short. This app turns a job description plus a candidate profile into a focused, actionable preparation plan.

## Features

- User registration and login with JWT authentication
- Protected routes (only logged-in users can generate reports)
- AI-generated interview questions tailored to the job description
- Skill-gap analysis (your skills vs. job requirements)
- Personalized preparation strategy
- Saved history of past interview plans

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React, Vite, SCSS, Axios |
| Backend | Node.js, Express |
| Database | MongoDB Atlas (Mongoose) |
| Auth | JWT, password hashing |
| AI | Google Gemini API |
| File handling | Multer, pdf-parse |

## Architecture

```
React (Vite)
   ↓ Axios API calls
Express routes → Middleware (JWT check)
   ↓
Controllers → AI service (Gemini)
   ↓
MongoDB (users, interview reports)
```

## Project Structure

```
Backend/
  src/
    config/        # database connection
    controllers/   # auth + interview logic
    middlewares/   # JWT auth middleware
    services/      # Gemini AI service
  server.js
Frontend/
  src/
    features/
      auth/        # login, register, auth context
      interview/   # home, report page, hooks, API
```

## Getting Started

### Prerequisites

- Node.js 18+
- A MongoDB Atlas cluster (free tier works)
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

### 1. Clone the repo

```bash
git clone https://github.com/shivanikunjir/interview-ai-platform.git
cd interview-ai-platform
```

### 2. Backend setup

```bash
cd Backend
npm install
```

Create a `.env` file in `Backend/` (see `.env.example`):

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=any_long_random_string
GOOGLE_GENAI_API_KEY=your_gemini_api_key
```

Start the server:

```bash
npm start
```

You should see `Server is running on port 3000` and `Connected to Database`.

### 3. Frontend setup

In a second terminal:

```bash
cd Frontend
npm install
npm run dev
```

Open http://localhost:5173.

## Usage

1. Register an account and log in
2. Paste a target job description
3. Add a short self-description of your experience
4. Click **Generate My Interview Strategy**
5. Review the generated questions, skill gaps, and preparation plan

## Known Issues

- Resume file upload (PDF) is not working reliably yet; use the Quick Self-Description field instead.

## Future Improvements

- Fix and polish resume PDF upload
- Mock interview mode with AI feedback on answers
- Deployment (frontend + backend)
- Improved UI and dashboard

## Screenshots


<img width="392" height="374" alt="Screenshot 2026-09-27 191138" src="https://github.com/user-attachments/assets/d9dec812-1ef5-471b-94e9-c60f89516459" />
<img width="197" height="224" alt="Screenshot 2026-09-27 191215" src="https://github.com/user-attachments/assets/59d40353-dda0-43b5-a69b-077a04ed82ac" />
<img width="1644" height="843" alt="Screenshot 2026-09-27 190844" src="https://github.com/user-attachments/assets/731d7a36-d496-4f19-9860-db6b8a56f465" />




