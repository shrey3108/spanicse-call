# Dental Voice AI Agent - Setup Guide

## Files
- `vapi_prompt.txt` — Vapi assistant ka system prompt
- `vapi_tools.json` — Vapi tools (3 tools: checkAvailability, bookAppointment, saveLeadInfo)
- `n8n_workflow.json` — n8n workflow (import karo directly)

---

## Step 1: n8n Setup

1. n8n mein **Import Workflow** → `n8n_workflow.json` upload karo
2. **Google Calendar credential** connect karo:
   - n8n → Credentials → Add → Google Calendar OAuth2
   - Client ko authorization link bhejo → wo click karke allow karega
   - Ek baar allow kiya = permanent access, client se dobara kuch nahi chahiye
3. **Google Sheets credential** connect karo (apna account use karo)
4. Google Sheet banao with columns:
   `Timestamp | Patient Name | Phone | Treatment | Date | Time | New Patient | Lead Score | Status | Notes`
5. Sheet ID copy karo → workflow mein `YOUR_GOOGLE_SHEET_ID` replace karo
6. Workflow **activate** karo
7. Webhook URL copy karo (format: `https://your-n8n.com/webhook/vapi-dental`)

---

## Step 2: Google OAuth for Client Calendar

n8n mein Google Calendar credential add karte waqt:
1. Google Cloud Console → OAuth 2.0 Client ID banao
2. n8n credential settings mein Client ID + Secret daalo
3. "Connect" click karo → authorization link milega
4. **Ye link client ko bhejo** → wo apne Google account se login karke allow karega
5. Done — ab n8n client ke calendar mein appointments add kar sakta hai
6. Client ko kuch aur karna nahi hai — appointments apne Google Calendar mein dikhenge

---

## Step 3: Vapi Setup

1. Vapi dashboard → **Create Assistant**
2. **System Prompt**: `vapi_prompt.txt` ka content paste karo
3. `[Clinic Name]` replace karo actual clinic name se
4. **Tools** section mein → `vapi_tools.json` ke 3 tools add karo
5. Har tool mein `YOUR_N8N_URL` replace karo apne n8n webhook URL se
6. **Voice** select karo (Hindi/Hinglish ke liye: ElevenLabs ya Deepgram recommended)
7. **Phone number** assign karo (Vapi dashboard se ya Twilio import)

---

## Step 4: Test

1. Vapi dashboard mein "Test Call" karo
2. Check karo:
   - Agent sahi se baat kar raha hai?
   - checkAvailability kaam kar raha hai?
   - bookAppointment calendar mein event bana raha hai?
   - Google Sheet mein data aa raha hai?

---

## Flow Summary

```
Caller → Vapi Agent (voice conversation)
  → Qualifying questions (treatment, urgency, name, phone)
  → Lead scored (hot/warm/cold)
  
  HOT lead:
    → checkAvailability → shows slots
    → bookAppointment → Google Calendar event + Sheet entry
    → Confirmation to caller
  
  WARM/COLD lead:
    → saveLeadInfo → Sheet entry for follow-up
```
