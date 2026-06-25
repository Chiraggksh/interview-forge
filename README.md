<div align="center">

# InterviewForge : AI-Powered Interview Intelligence Platform

<p align="center">
  <img src="./assets/banner.png" alt="InterviewForge Banner" width="100%" />
</p>

> **Turn any job description into a personalized interview battle plan within seconds.**

[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com)
[![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Google Gemini](https://img.shields.io/badge/Gemini_2.0_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)
[![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io)
[![Zod](https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white)](https://zod.dev)

[Report a Bug](../../issues) · [Request a Feature](../../issues)

</div>

---

## Table of Contents

- [About the Project](#-about-the-project)
- [Demo & Workflow](#-demo--workflow)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture Overview](#-architecture-overview)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
  - [Authentication Flow](#1-authentication-flow)
  - [AI Analysis Pipeline](#2-ai-analysis-pipeline)
  - [Structured Output with Zod](#3-structured-output-with-zod)
  - [PDF Resume Generation](#4-pdf-resume-generation)
  - [Session History](#5-session-history)
- [API Reference](#-api-reference)
- [Screenshots](#-screenshots)
- [Roadmap](#-future-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 About the Project

**PrepIQ** is a full-stack MERN application that acts as your personal AI interview coach. You feed it a job description, your resume, and a short self-description — and it gives you back a complete, actionable prep kit:

- 📊 A **match score** between your profile and the role
- 🛠️ A list of **skills you need to acquire or strengthen**
- ❓ Curated **technical interview questions** tailored to the role
- 🤝 **Behavioural questions** based on your background
- 🗺️ A **4–5 day personalised prep roadmap** with daily goals
- 📄 A **generated PDF resume** from your details — ready to submit

All sessions are **persisted in MongoDB**, so you can revisit any previous prep session with a single click — no re-entry needed.

---

## 🎬 Demo & Workflow

<!-- 
  📌 MEDIA PLACEMENT GUIDE
  ─────────────────────────────────────────────────────────────────────────
  1. HERO BANNER (top of README)
     → assets/banner.png  |  1280×640px  |  app name + tagline + UI preview
     
  2. FULL WORKFLOW VIDEO (below this section)
     → Record a 2–3 min screen recording covering:
        Login → Input form → AI result cards → Roadmap → History → Resume PDF
     → Host on YouTube (unlisted) and embed with the thumbnail trick below
     → assets/demo-thumbnail.png  |  1280×720px  |  screenshot of the video

  3. FEATURE GIFS (one per major feature section further below)
     → assets/gif-auth.gif        — login / register flow (5–8 sec)
     → assets/gif-analysis.gif    — filling the form + results loading (10–15 sec)
     → assets/gif-roadmap.gif     — scrolling through the 4-5 day roadmap (5–8 sec)
     → assets/gif-history.gif     — clicking a past session to restore it (5–8 sec)
     → assets/gif-resume.gif      — resume generation + PDF download (5–8 sec)

  4. SCREENSHOT GRID (Screenshots section near the bottom)
     → assets/ss-dashboard.png    — main dashboard / landing after login
     → assets/ss-form.png         — input form (JD + resume + self-description)
     → assets/ss-results.png      — AI result cards (match score, skills, Qs)
     → assets/ss-roadmap.png      — 4-5 day roadmap view
     → assets/ss-history.png      — previous sessions sidebar / list
     → assets/ss-resume.png       — generated resume preview

  5. ARCHITECTURE DIAGRAM
     → assets/architecture.png    — system design diagram (draw on Excalidraw / Figma)
  ─────────────────────────────────────────────────────────────────────────
-->

<p align="center">
  <a href="YOUR_YOUTUBE_LINK_HERE">
    <img src="./assets/demo-thumbnail.png" alt="Watch Full Demo" width="80%" />
    <br/>
    <strong>▶ Watch Full Workflow Demo (2 min)</strong>
  </a>
</p>

---

## ✨ Features

### 🔐 Authentication
- Secure **JWT-based authentication** with HTTP-only cookies
- Register / Login / Logout with full session management
- Protected routes — all analysis features are gated behind auth

### 🤖 AI-Powered Interview Analysis
- Paste any **job description** + your **resume** + a short **self-description**
- Powered by **Google Gemini 2.0 Flash Preview** for fast, high-quality generation
- Outputs are **schema-validated** using Zod before being stored or displayed — no hallucinated or malformed JSON ever reaches your frontend

### 📊 Match Score & Skill Gap Analysis
- Percentage-based **compatibility score** between your profile and the role
- Detailed list of **skills to learn or brush up on** before the interview

### ❓ Interview Question Bank
- **Technical questions** scoped to the specific tech stack and role requirements
- **Behavioural questions** tailored to your experience and the role's soft-skill demands

### 🗺️ Personalised 4–5 Day Prep Roadmap
- Day-by-day breakdown of what to study, practice, and revise
- Structured to be realistic and achievable before a typical interview timeline

### 📁 Persistent Session History
- Every analysis is **saved to MongoDB** under your account
- Click any past session from the history panel — all inputs and results are instantly restored
- No duplicate effort — pick up exactly where you left off

### 📄 AI Resume Generator (PDF)
- Input your details and let the app build a clean, structured resume
- Uses **Puppeteer** to render an HTML template and export a professional **PDF**
- Download-ready in seconds

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React, React Router, Axios, TailwindCSS |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB Atlas + Mongoose |
| **AI Model** | Google Gemini 2.0 Flash Preview |
| **Schema Validation** | Zod + `zod-to-json-schema` |
| **Auth** | JWT + HTTP-only Cookies |
| **PDF Generation** | Puppeteer |
| **Deployment** | (e.g. Vercel / Render / Railway) |

---

## 🏗️ Architecture Overview

<!-- 📌 Replace with your actual architecture diagram at assets/architecture.png -->
<p align="center">
  <img src="./assets/architecture.png" alt="PrepIQ Architecture" width="85%" />
</p>

The high-level flow:

```
User (Browser)
    │
    ▼
React Frontend  ──── Axios ────▶  Express REST API
                                       │
                          ┌────────────┼────────────────┐
                          ▼            ▼                 ▼
                      MongoDB      Gemini API         Puppeteer
                    (sessions,   (AI analysis,       (Resume →
                     users,       structured           PDF)
                     history)     output via Zod)
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js `v18+`
- npm or yarn
- MongoDB Atlas URI
- Google Gemini API Key

### Installation

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/prepiq.git
cd prepiq

# 2. Install backend dependencies
cd server
npm install

# 3. Install frontend dependencies
cd ../client
npm install
```

### Environment Variables

Create a `.env` file inside the `/server` directory:

```env
# Server
PORT=5000
NODE_ENV=development

# MongoDB
MONGO_URI=your_mongodb_atlas_connection_string

# JWT
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRES_IN=7d

# Cookies
COOKIE_SECRET=your_cookie_secret

# Google Gemini
GEMINI_API_KEY=your_gemini_api_key
```

### Running Locally

```bash
# Start the backend (from /server)
npm run dev

# Start the frontend (from /client)
npm run dev
```

The app will be running at `http://localhost:5173` (Vite default).

---

## 📁 Project Structure

```
prepiq/
├── client/                     # React frontend
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   ├── pages/              # Route-level pages
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Dashboard.jsx   # Main analysis page
│   │   │   ├── History.jsx     # Previous sessions
│   │   │   └── Resume.jsx      # Resume generator
│   │   ├── context/            # Auth context / global state
│   │   └── utils/              # Axios config, helpers
│   └── package.json
│
├── server/                     # Express backend
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── analysisController.js
│   │   ├── historyController.js
│   │   └── resumeController.js
│   ├── models/
│   │   ├── User.js
│   │   └── Session.js          # Stores full analysis results
│   ├── routes/
│   │   ├── auth.routes.js
│   │   ├── analysis.routes.js
│   │   ├── history.routes.js
│   │   └── resume.routes.js
│   ├── middleware/
│   │   └── authMiddleware.js   # JWT verification
│   ├── schemas/
│   │   └── analysisSchema.js   # Zod schema + JSON schema export
│   ├── services/
│   │   ├── geminiService.js    # Gemini API integration
│   │   └── pdfService.js       # Puppeteer PDF generation
│   └── server.js
│
└── README.md
```

---

## 🔍 How It Works

### 1. Authentication Flow

<!-- 📌 Place gif-auth.gif here -->
<p align="center">
  <img src="./assets/gif-auth.gif" alt="Auth Flow" width="70%" />
</p>

- User registers/logs in via a form
- Server validates credentials, signs a **JWT**, and sets it as an **HTTP-only cookie**
- All subsequent API requests automatically carry the cookie
- A middleware on every protected route verifies the token before proceeding

---

### 2. AI Analysis Pipeline

<!-- 📌 Place gif-analysis.gif here -->
<p align="center">
  <img src="./assets/gif-analysis.gif" alt="AI Analysis" width="70%" />
</p>

1. User submits **job description**, **resume text**, and **self-description**
2. Backend constructs a structured prompt and calls **Google Gemini 2.0 Flash Preview**
3. The model returns a JSON object conforming to our Zod schema
4. The validated result is stored in **MongoDB** and sent to the frontend
5. React renders match score, skill gaps, questions, and the roadmap

---

### 3. Structured Output with Zod

The core of PrepIQ's reliability is its use of **Zod** for schema-first AI output validation.

```js
// server/schemas/analysisSchema.js
import { z } from "zod";
import { zodToJsonSchema } from "zod-to-json-schema";

const analysisSchema = z.object({
  matchScore: z.number().min(0).max(100),
  skillsNeeded: z.array(z.string()),
  technicalQuestions: z.array(z.string()),
  behaviouralQuestions: z.array(z.string()),
  roadmap: z.array(
    z.object({
      day: z.number(),
      title: z.string(),
      tasks: z.array(z.string()),
    })
  ),
});

// Convert Zod schema → JSON Schema and inject into Gemini prompt
export const jsonSchema = zodToJsonSchema(analysisSchema, "analysisSchema");
export { analysisSchema };
```

The JSON schema is embedded in the Gemini prompt, instructing the model to return output that matches it exactly. The response is then parsed and validated with `.parse()` before any further processing — guaranteeing type-safe, predictable data on every call.

---

### 4. PDF Resume Generation

<!-- 📌 Place gif-resume.gif here -->
<p align="center">
  <img src="./assets/gif-resume.gif" alt="Resume PDF" width="70%" />
</p>

1. User fills in their details on the Resume page
2. Backend renders a styled **HTML template** with the user's data
3. **Puppeteer** launches a headless browser, loads the HTML, and exports it as a PDF
4. The PDF buffer is streamed back to the client as a downloadable file

```js
// server/services/pdfService.js (simplified)
const browser = await puppeteer.launch({ headless: "new" });
const page = await browser.newPage();
await page.setContent(renderedHTML, { waitUntil: "networkidle0" });
const pdfBuffer = await page.pdf({ format: "A4", printBackground: true });
await browser.close();
return pdfBuffer;
```

---

### 5. Session History

<!-- 📌 Place gif-history.gif here -->
<p align="center">
  <img src="./assets/gif-history.gif" alt="Session History" width="70%" />
</p>

Every time you run an analysis, a **Session document** is saved in MongoDB:

```js
// server/models/Session.js (simplified)
{
  userId: ObjectId,          // linked to authenticated user
  jobDescription: String,
  resumeText: String,
  selfDescription: String,
  result: {                  // full Zod-validated AI output
    matchScore: Number,
    skillsNeeded: [String],
    technicalQuestions: [String],
    behaviouralQuestions: [String],
    roadmap: [...]
  },
  createdAt: Date
}
```

The history panel lists all your past sessions. Clicking one **pre-populates the form and results** — no re-generation needed.

---

## 📡 API Reference

| Method | Endpoint | Auth | Description |
|---|---|---|---|
| `POST` | `/api/auth/register` | ❌ | Register a new user |
| `POST` | `/api/auth/login` | ❌ | Login + set JWT cookie |
| `POST` | `/api/auth/logout` | ✅ | Clear JWT cookie |
| `POST` | `/api/analysis` | ✅ | Run AI analysis |
| `GET` | `/api/history` | ✅ | Get all sessions for user |
| `GET` | `/api/history/:id` | ✅ | Get a specific session |
| `POST` | `/api/resume/generate` | ✅ | Generate + return PDF resume |

---

## 📸 Screenshots

<!-- 📌 Use a 2-column grid for screenshots -->

<table>
  <tr>
    <td><img src="./assets/ss-dashboard.png" alt="Dashboard" /></td>
    <td><img src="./assets/ss-form.png" alt="Input Form" /></td>
  </tr>
  <tr>
    <td align="center"><em>Dashboard after login</em></td>
    <td align="center"><em>Analysis input form</em></td>
  </tr>
  <tr>
    <td><img src="./assets/ss-results.png" alt="Results" /></td>
    <td><img src="./assets/ss-roadmap.png" alt="Roadmap" /></td>
  </tr>
  <tr>
    <td align="center"><em>AI-generated results</em></td>
    <td align="center"><em>4–5 day prep roadmap</em></td>
  </tr>
  <tr>
    <td><img src="./assets/ss-history.png" alt="History" /></td>
    <td><img src="./assets/ss-resume.png" alt="Resume PDF" /></td>
  </tr>
  <tr>
    <td align="center"><em>Session history panel</em></td>
    <td align="center"><em>Generated PDF resume</em></td>
  </tr>
</table>

---

## 🔮 Future Roadmap

- [ ] LinkedIn profile import instead of manual resume paste
- [ ] Mock interview mode with timed responses and AI feedback
- [ ] Email reminders aligned with the daily roadmap
- [ ] Multi-language support for JD and output
- [ ] Shareable prep sessions via public links
- [ ] Analytics dashboard — track improvement across sessions

---

## 🤝 Contributing

Contributions are welcome! If you'd like to improve PrepIQ:

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'feat: add your feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

Please follow the existing code style and add comments where the logic is non-trivial.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

Made with ❤️ and way too much Gemini API quota

**[⬆ Back to top](#-prepiq--ai-powered-interview-intelligence-platform)**

</div>
