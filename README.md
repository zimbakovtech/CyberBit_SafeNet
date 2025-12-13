# Cyber Bit – Cyber Security Phishing Trainer (Kaboom.js)

`phishing_game.html` is a self‑contained educational game about phishing and online safety, built with Kaboom.js and designed to be kid‑friendly.

The player explores a bedroom, receives realistic phishing‑style notifications on different devices (phone, computer, tablet), and makes choices that affect their XP, level, and allowance.

---

## How to Run

### 1. Clone the repo (GitHub)

```bash
git clone https://github.com/zimbakovtech/CyberBit_SafeNet.git
cd CyberBit_SafeNet
```

### 2. Open the game

You only need a modern desktop browser; no build step or server is required.

- **macOS (terminal):**

  ```bash
  open phishing_game.html
  ```

- **macOS/Windows/Linux (file explorer):** navigate to the cloned folder and
  double‑click `phishing_game.html` to open it in your default browser.

- **VS Code (optional, nice for dev):** install the *Live Server* extension,
  then right‑click `phishing_game.html` and choose **Open with Live Server**.

---

## Game Overview

### Main Menu

- Title screen: **CYBER BIT – A Phishing Awareness Adventure**.
- Buttons: **START** (enter the bedroom) and **QUIT** (thank‑you screen).
- Short tip explaining that real attacks often feel urgent and unexpected.
- Keyboard shortcuts:
  - **ENTER** – Start the game.
  - **P** – Open the progress report (if implemented).

### Bedroom (Hub Scene)

- You play as a child character in a cozy bedroom.
- Devices in the room:
  - **Phone** on a stand.
  - **Computer** on the center desk.
  - **Tablet** on a small table.
- A sidebar on the right shows each device and whether it has alerts.
- A top HUD bar shows:
  - **Level** and current **XP**.
  - XP progress bar to the next level.
  - Current **Allowance** (money) for the player.

### Devices & Notifications

- Phishing‑style notifications appear on random devices over time:
  - Each device gets a **red badge** and a **toast** in the top‑right when a new alert arrives.
  - Examples: fake delivery SMS, “account locked” emails, social media security alerts.
- Notifications are persistent in logic but the visual badges/toasts auto‑hide after a few seconds.
- Each notification is tied to a generated phishing scenario with:
  - Sender line (often a slightly wrong address or domain).
  - Message body with urgency and suspicious links.
  - “Red flags” hints explaining what to watch out for.

### Scenarios & Outcomes

- Each device opens into a device‑specific UI:
  - **Phone** – app grid home screen (Messages, Mail, Phone, Browser).
  - **Computer** – desktop with app icons (Mail, Browser, Social).
  - **Tablet** – tablet/iPad‑like dock with apps.
- The app with the active alert gets a small red badge; tapping/clicking it opens a **scenario card**.
- The scenario card shows:
  - Title and device.
  - Sender (email, SMS number, or app).
  - Message text with a suspicious URL.
  - A “RED FLAGS” panel listing clues.
- You then choose between two clear actions:
  - **Risky choice** (e.g. “CLICK LINK & LOGIN”, “OPEN LINK & PAY”).
  - **Safe choice** (e.g. “DELETE & REPORT”, “IGNORE / USE OFFICIAL APP”).

### XP, Levels, and Allowance

- The game tracks persistent player state in `localStorage`:
  - **XP** and **Level**.
  - **Allowance** (starting with a default value).
  - Completed scenario IDs and optional settings.
- Outcomes:
  - **Safe choice** → you gain XP based on difficulty, can level up, and keep your allowance.
  - **Risky choice** → you “get hacked” and lose part of your **allowance** instead of XP.
- Good decisions show a **SAFE** screen explaining what you did right.
- Bad decisions show a **YOU GOT HACKED** screen explaining what went wrong and reminding you that you lost some allowance.

### Sound & Feedback

- Simple, built‑in beeps provide feedback (no external audio files):
  - UI click sounds for buttons and device/app selections.
  - Notification chime when new alerts arrive.
  - Different tones for safe vs hacked outcomes.
- Visual effects:
  - Soft fade‑in between scenes.
  - Level‑up banner when you reach a new level.

---

## Controls

**Menu**

- **ENTER** – Start game.
- **P** – Progress report (if enabled).
- **ESC** – Quit to the thank‑you screen.

**Bedroom (Room)**

- **Arrow Keys** – Move the player.
- **SPACE** – Inspect the nearest device (when prompted).
- **R** – Restart the room.

**Devices (Phone / Computer / Tablet)**

- **Mouse / Trackpad** – Click the app with the red badge.
- **ESC** – Return to the bedroom.

**Scenarios & Endings**

- **Mouse / Trackpad** – Click the **safe** or **risky** action button.
- **ESC** (on ending screens) – Return to the relevant device or back to the bedroom.
- **R** (on ending screens) – Restart the bedroom.

---

## Educational Goals

The game is designed to help kids (and adults) practice:

- Noticing small details in sender names and URLs.
- Recognising urgent or threatening language as a red flag.
- Choosing safer actions (ignore, delete, verify via official apps).
- Understanding that risky clicks can cost them “allowance” (a child‑friendly metaphor for money and consequences).

Because scenarios are generated from templates with varying difficulty, players can replay to see new combinations and reinforce good habits.

