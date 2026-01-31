<div align="center">

<img src="https://raw.githubusercontent.com/andzcr/AZZIST/main/photos/azzist_hero.jpg" alt="Azzist Hero Banner" width="100%">

# Build Your Own Azzist. Smart, Fast & Yours.

</div>

<div id="-project-description"></div>

Meet **Azzist** – a complete, modular, and **100% free** virtual assistant designed to elevate web interaction.

It’s not just a "wrapper" over an API. It is a complete ecosystem (Frontend + Backend + Generator) that transforms a passive visitor into an engaged user. My goal was to create something that *anyone* can use for their website, with no hidden costs. **Get yours, for free.**

## ✨ Frontend Architecture (`bot.js`)

I wanted the user experience to be "fluid," not static. Here are the systems I integrated:

### 1. User Experience & Interaction
- **Smart Nudging (Section Tracking):** The bot "sees" what you are looking at. If you linger on the *Contact* or *Projects* section, it sends a contextual message related to that specific content.
- **Highlight-to-Ask:** If you select text on the site, a discreet tooltip appears. One click, and the bot uses the selected text as context for a query.
- **Rage Click Detection:** The bot detects user frustration (rapid, repeated clicks or chaotic mouse movements) and proactively intervenes, asking if you need help.
- **Exit Intent Technology:** If you move your mouse outside the window (towards the tabs), the bot "catches" you before you leave with an offer (e.g., CV download).

### 2. Hardware & Environment Awareness. The bot adapts its behavior
- **Battery Status Check:** Checks the device's battery level (`navigator.getBattery`). If it's below 20% and not charging, the bot enters a "short and to the point" mode ("I see your battery is running low...").
- **Geo-Location & Weather Greeting:** Identifies the user's city (via `ipapi.co`) and checks local weather (via `open-meteo.com`).
- **Behavioral Logic:** If the user is from Galați (the author's city), it displays a specific message ("Small world"). If they are from another city, it greets them by mentioning their location. It also greets with "Good morning/afternoon/evening" based on the system's local time.

### 3. Accessibility & Utilities
- **Text-to-Speech (TTS):** The bot can "speak" using the Web Speech API, featuring visual synchronization (audio visualizer bars).
- **Slash Commands:** A menu system (`/cv`, `/reset`, `/contact`) for quick accessibility.
- **Sentiment Analysis:** Rapid client-side analysis (Regex-based) to detect if you are angry, happy, or communicative. It automatically shifts its tone depending on who it is talking to.
- **Urgent Mode:** If urgency is detected, the interface changes color (red), and the bot becomes more concise.
- **Quick Replies:** FAQ cards that can be interacted with via drag-and-drop.
- **Form Autofill:** The bot can automatically fill in the contact form on the website.
- **Download Manager:** Manages the download of the CV and the chat transcript (generates a `.txt` file with timestamps).
- **Image Upload:** Allows users to upload images directly into the chat.
- **Focus Mode:** Dims the rest of the website and highlights only the chat window to capture the user's attention in **special** cases.
- **Local Storage Memory:** Remembers conversation history and context (last visited section) for 24 hours.
- **Hard Reset:** Option to clear history with a confirmation modal ("Are you sure?").
- **Rating System:** After 5 interactions or upon saying "Goodbye," it asks for a rating (1-5 stars) with interactive visual feedback.

---

### 🔔 Telegram Notification System
A system I am particularly proud of. The bot doesn't just talk; it **notifies me in real-time** about what is happening on the site.

<div align="center">
<img src="https://raw.githubusercontent.com/andzcr/AZZIST/main/photos/Notificare.png" alt="Telegram Notification System" width="600px">
</div>

- **Real-time Alerts:** I receive an **instant** message on my phone whenever someone opens the chatbot.
- **Lead Generation:** If someone completes a form or leaves a review, the data is sent **directly** to Telegram.
- **Feedback Loop:** I receive the rating given by users at the end of their conversation with Azzist.

---

## 🎨 Design & Visuals (`bot.css`)

- **Burger Menu:** A menu in the chat header for quick settings (Voice, Export, Reset).
- **Glassmorphism:** `backdrop-filter: blur()` effects to integrate seamlessly and modernly into any website.
- **Animations:** Custom keyframes for everything – from chat bubbles popping in (`messagePop`) to the launch button's pulse.
- **Dynamic Theming:** CSS Variables allow for easy brand color customization.
- **Mobile First:** The interface transforms completely on mobile (full screen) to ensure usability.

---

## 📡 Backend & AI (`server.js`)

The brain behind the operation.
- **Google Gemini Integration:** Uses the `gemini-pro` model (or `flash` as a fallback) for fast and creative responses.
- **Context Management:** Loads a "System Prompt" from an external file, allowing the bot to know who it is (Azzist) and whom it represents.
- **Robust Error Handling:** If the Google API times out, the server automatically attempts alternative models.

---

### 🏭 The AzzistBOT Generator
One of the most complex modules of the project is the **Azzist Generator**, available at [andz.ro/azzist](https://andz.ro/azzist).

You don't need to write code to have your own bot. I created a system that:
- Collects data about your business through a simple-to-use form.
- Shapes the bot's "personality" in real-time.
- **Generates a complete .ZIP package Client-Side** (using `JSZip`), containing the server, environment files, PDF documentation (dynamically generated with `jspdf`), and the customized frontend code.

<div align="center">
  <p><i>The bot auto-configures and packages itself for download.</i></p>
</div>

<div align="center">
  <img src="https://github.com/andzcr/AZZIST/raw/main/photos/preview.gif" alt="Azzist Preview" width="100%">
</div>

---

<div align="center">
Made for <a href="https://andz.ro">ANDZ</a>, accesible for anyone.
</div>
