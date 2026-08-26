# OmniAI — Universal Multi-Industry AI Voice Receptionist Showcase

A state-of-the-art, interactive web application and demo showcase for AI Voice Receptionists across **5 major industry verticals**. Built with Vanilla JS, frosted glassmorphic UI, real-time sound-reactive 3D voice orb, live transcription stream, and n8n webhook integrations.

---

## 🌟 Demo Features

### 5 Built-in Industry Personas:
1. 🩺 **Medical & Dental Clinic**: Appointments, toothache/routine care, doctor availability.
2. 🛠️ **Home Services & Maintenance**: 24/7 Plumber, Electrician, Carpenter & HVAC technician dispatch.
3. 🍽️ **Restaurant & Lounge**: Table reservations, party sizes, outdoor seating, private event inquiries.
4. 🚗 **Car Dealership & Auto Workshop**: SUV test drive bookings, routine car service & repairs.
5. 🏢 **General Corporate Receptionist**: Universal lead qualification, FAQ response & callback booking.

### Interactive UI Highlights:
- 🎙️ **Sound-Reactive 3D AI Voice Orb**: Scaled smoothly in real-time by micro-volume input from `@vapi-ai/web`.
- 🎨 **Dynamic Industry Theming**: Instant color, logo, prompt chips, and badge transitions when switching personas.
- 💬 **Live Transcript Stream**: Chat bubbles with auto-scroll and role badges for Assistant & Caller.
- 📊 **Real-Time Intelligence Bar**: Live metric cards tracking Lead Qualification Score (`HOT 🔥`, `WARM ⚡`, `COLD ❄️`), Detected Language (English, Spanish, Hindi), Tool Executions, and Call Duration.
- 💡 **Sample Conversation Chips**: One-click sample prompt starters for client demos.
- ⚙️ **Credentials Modal**: On-the-fly Vapi Public Key & Assistant ID configuration saved in browser `localStorage`.

---

## 📁 Repository Structure

- `index.html` — The main multi-industry web application & demo showcase.
- `industry_prompts.json` — System prompt configs, themes, and quick-prompt chips for all 5 industries.
- `vapi_tools.json` — Tool schemas (`checkAvailability`, `bookAppointment`, `saveLeadInfo`) compatible with multi-industry payloads.
- `vapi_prompt.txt` — Full system prompt documentation for all 5 business personas.
- `n8n_workflow.json` — The n8n backend workflow for Google Calendar and Google Sheet lead recording.
- `SETUP_GUIDE.md` — Guide on configuring n8n and Vapi for production deployment.

---

## 🚀 Quick Start (Local Hosting)

1. Open terminal in project folder.
2. Start local web server:
   ```bash
   npx http-server -p 8080
   ```
   *or*
   ```bash
   python -m http.server 8000
   ```
3. Open `http://localhost:8080` in your browser.
4. Click top industry pills to switch personas or click the ⚙️ icon to enter custom Vapi API credentials.
