# 🇦🇪 Dubai Travel Expert | The AI Concierge ™
**A High-Performance AI Kiosk System for Luxury Tourism.**

This project is a multi-cloud "Headless Kiosk" designed to provide voice-driven concierge services in hotel lobbies and tourism hubs. It leverages real-time voice synthesis and a socket-based bridge to synchronize a physical display with an AI's conversation.

---

## 🏗 The "Golden Triangle" Architecture
The system is divided into three distinct layers to ensure zero latency and global scalability:

1.  **THE BRAIN (Voice & Logic):** - Powered by **Vapi.ai**.
    - Handles Speech-to-Text (STT), Large Language Model (LLM) reasoning, and Text-to-Speech (TTS).
    - Uses a custom tool `updateKioskDisplay` to trigger visual changes.

2.  **THE NERVE CENTER (Backend Bridge):** - Hosted on **Render** (`kiosk-bridge.onrender.com`).
    - Built with **Node.js** and **Socket.io**.
    - Receives tool-call webhooks from Vapi and broadcasts them instantly to the frontend.

3.  **THE FACE (Frontend Kiosk):**
    - Hosted on **GitHub Pages**.
    - A responsive **HTML5/JavaScript** application.
    - Dynamically updates UI elements (QR Codes, VIP Welcomes) and background themes (`vibe`) based on the conversation context.

---

## 🚀 Key Features
* **Voice-to-Visual Sync:** When the AI speaks about a tour, the kiosk instantly displays the booking QR code.
* **Visual Vibe Protocol:** The background color shifts based on the mood:
    - 🌧 `rain`: Deep Blue gradients for indoor activity focus.
    - ✨ `luxury`: Gold/Dark gradients for VIP identification.
    - 🔥 `adventure`: Red/Black gradients for high-energy activities.
* **VIP Identification:** Specific hotel mentions (e.g., Burj Al Arab) trigger an exclusive "WELCOME VIP" screen state.
* **Lead Capture:** Automatic extraction of guest contact details for instant WhatsApp confirmation.

---

## 🛠 Tech Stack
- **Frontend:** HTML5, CSS3 (Animations), JavaScript (Vapi Web SDK, Socket.io Client).
- **Backend:** Node.js, Express, Socket.io (Server).
- **AI Infrastructure:** Vapi.ai (Voice AI), OpenAI (LLM Backbone).
- **Hosting:** GitHub Pages (Static), Render (Dynamic Bridge).

---

## 📖 Setup & Deployment

### Backend (Render)
1. Deploy `index.js` to Render.
2. Set up the Environment Variable `PORT`.
3. Configure your Vapi Tool URL to point to `https://your-render-app.onrender.com/webhook`.

### Frontend (GitHub)
1. Replace `VAPI_PUBLIC_KEY` and `ASSISTANT_ID` in `index.html`.
2. Ensure the `RENDER_BRIDGE_URL` points to your active Render instance.
3. Enable GitHub Pages on the `main` branch.

---

## 👤 Author
**Ahmed | Dubai Travel Expert ™**
*Luxury Travel | Storytelling | AI-Optimized Experiences ™*
