# Dental Clinic - AI Receptionist Web Interface

A premium, modern web interface for the Dental Clinic AI Receptionist. This application integrates directly with the Vapi Voice AI SDK to allow patients to have real-time voice conversations with an AI receptionist to book appointments, check slot availability, and request callbacks.

## Features
- 📞 **Direct Voice Call Integration:** Start and end real-time voice calls with the Vapi Assistant.
- 🎙️ **Live Volume Visualization:** A dynamic volume bar showing microphone levels during calls.
- 💬 **Live Transcript Display:** Real-time text transcription of what the patient and the assistant say.
- ⚡ **Highly Responsive UI:** Custom animations and status notifications (Connecting, Listening, Speaking).
- 🌐 **Responsive Design:** Completely optimized for both mobile and desktop viewports.

## Tech Stack
- **Frontend:** HTML5, Vanilla CSS3 (modern styling, clean visual hierarchy)
- **SDK:** `@vapi-ai/web` (loaded via ES Modules)

## Getting Started

### 1. Configuration
Open `index.html` and configure your Vapi credentials:
```javascript
// index.html (Lines 261-262)
const VAPI_PUBLIC_KEY = "your-vapi-public-key";
const VAPI_ASSISTANT_ID = "your-vapi-assistant-id";
```

### 2. Local Hosting (Mandatory for Microphone Access)
Due to browser security protocols, features like **microphone access** and **AudioWorklets** (used for voice noise filtering) are blocked on direct local files (`file://`). You must host this on a local or remote web server.

#### Option A: Node.js (npx)
Run the following command in the folder:
```bash
npx http-server -p 8080
```
Then visit `http://localhost:8080` in your browser.

#### Option B: VS Code Live Server
1. Install the **"Live Server"** extension in VS Code.
2. Right-click `index.html` and select **"Open with Live Server"**.

#### Option C: Python
Run:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000`.

## Production Deployment
You can deploy this static interface for free on platforms like **Netlify**, **Vercel**, or **GitHub Pages**. Ensure the hosted URL uses `https://` so the browser permits microphone permissions.
