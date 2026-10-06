# 🎨 Hacktober Daily

> A clean, minimal single-page web application displaying a daily handheld layout card of online Hacktoberfest events, closely matching a hand-drawn sketch aesthetic.

![Hacktober Daily Preview](https://raw.githubusercontent.com/Yash/hacktoberfest-daily-card/main/src/assets/preview.png)

---

## ✨ Features

- 🎨 **Hand-Drawn Sketch Aesthetic**: Features organic rounded outlines (`2.5px solid #1e1e1e`), subtle drop shadows, and handwritten typography.
- 🎨 **Strict Pastel Color Palette**:
  - 🟩 **Container**: Pastel Mint Green (`#b2f2bb`)
  - 🟦 **Box 1 (Mini Event)**: Pastel Sky Blue (`#a5d8ff`)
  - 🟥 **Box 2 (Stream)**: Pastel Coral Pink (`#ffc9c9`)
  - 🟨 **Box 3 (Challenges)**: Pastel Butter Yellow (`#ffec99`)
  - ⬛ **Outlines & Text**: Charcoal Black (`#1e1e1e`)
- 📅 **Seamless Date Browsing**: Navigate effortlessly across all days of October (Oct 1 – Oct 31) using arrow controls, a date picker, or the "Today" shortcut.
- 🌐 **Timezone Conversion**: Toggle between **UTC** and your **Local Timezone** with one click.
- 📸 **Export & Sharing Tools**:
  - 📷 **PNG Card Export**: Download the card as a high-resolution PNG image.
  - 📋 **Copy Summary**: Copy daily event markdown summaries to your clipboard.
  - 🗓️ **iCal Calendar (.ics)**: Download `.ics` calendar files to import directly into Google Calendar or Apple Calendar.
- 🔍 **Interactive Event Details**: Click any bullet point to view event descriptions, platform tags, and direct join links.
- ⚡ **Offline-First & Pre-Seeded**: Includes complete pre-seeded data for October 1–31 so the card works instantly even without internet access.
- 🤖 **Automated Daily Scraper**:
  - Automated GitHub Action scheduled daily at **06:00 UTC** (`.github/workflows/daily-scraper.yml`).
  - Classification engine categorizes events into Workshops/AMAs, Live Streams, and Challenges.
  - Deployable on **Vercel** (`api/events.js`) and **Render** (`backend/app.py`).

---

## 🛠️ Tech Stack

- **Frontend**: HTML5, Vanilla CSS, JavaScript (ES6+), Vite, `html2canvas`
- **Typography**: Google Fonts (`Patrick Hand`, `Kalam`, `Architects Daughter`)
- **Backend & APIs**: Node.js Serverless (Vercel), Python Flask (Render)
- **Automation**: GitHub Actions (Cron Scraper at `0 6 * * *`)

---

## 📁 Repository Structure

```
Hacktober-Daily/
├── index.html                      # Main HTML single-page app
├── package.json                    # Project dependencies & scripts
├── vercel.json                     # Vercel deployment configuration
├── render.yaml                     # Render Flask API deployment spec
├── src/
│   ├── style.css                   # Custom hand-drawn CSS & color system
│   ├── main.js                     # Interactive card logic (exports, modal, date switcher)
│   └── data/
│       └── october_events.json     # Pre-seeded October 1-31 events dataset
├── api/
│   └── events.js                   # Vercel serverless /api/events endpoint
├── backend/
│   ├── app.py                      # Flask API server for Render
│   ├── requirements.txt            # Python dependencies
│   └── scraper.py                  # Python BeautifulSoup / urllib scraper engine
├── scripts/
│   ├── scraper.js                  # Node.js scraper & categorizer script
│   └── generate_full_october.js    # Dataset generator script
└── .github/
    └── workflows/
        └── daily-scraper.yml       # Automated 06:00 UTC daily scraper workflow
```

---

## 🚀 Getting Started Locally

### Prerequisites
- Node.js (v18+)
- npm or pnpm

### 1. Clone & Install
```bash
git clone https://github.com/YOUR_USERNAME/hacktober-daily.git
cd hacktober-daily
npm install
```

### 2. Run Local Development Server
```bash
npm run dev
```
Open `http://localhost:5173` in your browser.

### 3. Run Scraper Script Locally
```bash
npm run scrape
```

### 4. Build for Production
```bash
npm run build
```

---

## ☁️ Deployment

### Deploying to Vercel
1. Push your repository to GitHub.
2. Import the project in Vercel.
3. Vercel automatically detects the Vite frontend and `/api/events.js` serverless endpoint via `vercel.json`.

### Deploying to Render
1. Create a new **Web Service** on Render.
2. Connect your GitHub repository.
3. Render automatically reads `render.yaml` to build Python environment and serve `backend/app.py`.

---

## 💖 Credits

Made with 💖 by **Yash**
