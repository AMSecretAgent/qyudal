# Qyudal

**A multi-agent news intelligence engine.** Qyudal doesn't just surface the news — its agents ingest, explain, predict, debate, fact-check, and brief it for you, so you see every side of a story and decide where you stand.

Built for the **International AI Agents Hackathon**.

---

## What it does

News today gives you one headline, one angle, one implied opinion. Getting the *full* picture means manually hunting across sources, weighing conflicting viewpoints, and fact-checking as you go — slow work almost nobody actually does. Qyudal automates that workflow.

For any story, **7 AI agents work in parallel** and return a complete analysis in under 4 seconds:

| Agent | What it does |
|-------|--------------|
| **Explain** | What happened, root causes, what's next, why it matters |
| **Predict** | 3 weighted future scenarios |
| **Debate** | Opposing perspectives + a neutral synthesis |
| **Timeline** | Chronological build-up of events |
| **Visualize** | Cause-and-effect flow of the story |
| **Notes** | TL;DR, key facts, and study questions |
| **Fact-Check** | A confidence score on every story |

## Features

- **Lite Mode** — a fast, vertical, swipeable live-news feed across Geopolitics, Tech & AI, Economy, India, Climate, and more
- **Lit Mode** — tap any story to run the full 7-agent deep analysis
- **Morning Brief** — an AI-curated daily digest of the top stories
- **Confidence Score** — every story is rated for source credibility and completeness
- **Secure accounts** — Firebase email/password auth with saved sessions
- Plus learning & lifestyle sections (study, health, success stories, puzzles)

## Tech stack

- **React Native + Expo** (JavaScript)
- **Google Gemini** (primary LLM) with **Groq / Llama 3.3** fallback for fast inference
- **NewsAPI** for live multi-source story ingestion
- **Firebase** (Authentication + Firestore)

The key architectural win is running the 7 agents **in parallel** (`Promise.all`) rather than sequentially — cutting analysis from 20–30s down to under 4s.

---

## Run it locally

**Prerequisites:** [Node.js (LTS)](https://nodejs.org), and the **Expo Go** app on your phone.

```bash
git clone https://github.com/AMSecretAgent/qyudal-app.git
cd qyudal-app
npm install
```

### Add your API keys

API keys are kept out of the repo. Create a file named **`secrets.js`** in the project root:

```js
export const NEWS_API_KEY   = 'YOUR_NEWSAPI_KEY';
export const GROQ_API_KEY   = 'YOUR_GROQ_KEY';
export const GEMINI_API_KEY = 'YOUR_GEMINI_KEY';
```

Get free keys here:
- **NewsAPI** — https://newsapi.org
- **Groq** — https://console.groq.com
- **Gemini** — https://aistudio.google.com (Google AI Studio)

> The Firebase config lives in `App.js`. It works as-is for the demo; if you fork this, swap in your own Firebase project's config.

### Start the app

```bash
npx expo start
```

Scan the QR code with **Expo Go** on your phone, and Qyudal loads on your device.

---
