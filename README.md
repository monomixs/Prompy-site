# Prompy

> A fast, private place to write, organize, and store your AI image prompts — complete with a secure vault, multi-image support, and optional cloud backup.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![No Build Step](https://img.shields.io/badge/build-none-success)
![Single File App](https://img.shields.io/badge/app-single%20file-blueviolet)

---

## Table of Contents

- [Features](#features)
- [Screenshots](#screenshots)
- [Getting Started](#getting-started)
- [Cloud Sync Setup](#cloud-sync-setup-optional)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Changelog](#changelog)
- [License](#license)

---

## Features

### 📝 Prompt Management
- Create, edit, and organize AI image prompts with custom tags
- Search, plus sort and filter by **Newest**, **Oldest**, or **A–Z**
- Up to **5 reference images** per prompt
  - Stacked-photo preview on the card when a prompt has 2+ images
  - Swipeable gallery in the detail view

### 🔒 Secure Vault
- PIN-protected vault, fully separate from your normal prompts
- Dedicated Vault Settings screen — search, filter, export/import, cloud sync, and PIN management
- Lock the vault with a single tap

### ✅ Multi-Select
- Press and hold any card to enter selection mode
- Bulk **export** (as a ZIP), bulk **delete**, or bulk **upload** to the cloud
- Smooth animated transitions in and out of selection mode

### ☁️ Cloud Backup (Backendless)
- Optional cloud sync using your own [Backendless](https://backendless.com) REST API key
- Each prompt is packaged as a self-contained `.zip` (data + images)
- Organized server-side into `prompts/normal/` and `prompts/vault/`
- Pull everything back down anytime with **Update Feed**

### 📦 Import / Export
- Export all prompts — or just your current selection — as a `.zip`, with one folder per prompt and all of its images
- Import ZIPs back in, or migrate legacy exports from the old Android app

### 💻 Zero Install
- Runs entirely in the browser — no build step, no server required
- A single `index.html` file: open it directly, or host it anywhere static files are served

---

## Screenshots

<!-- Add a screenshot or screen recording of the app here -->
_Coming soon — feel free to drop in a screenshot or GIF of the UI here._

---

## Getting Started

Prompy is a single self-contained HTML file. There's no build step and nothing to install.

### Run Locally

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

Then just open `index.html` in your browser:

```bash
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

### Deploy to GitHub Pages

1. Go to your repository's **Settings → Pages**
2. Under **Branch**, select your default branch and **`/ (root)`** as the folder
3. Save — your app will be live at `https://<your-username>.github.io/<your-repo>/`

---

## Cloud Sync Setup (Optional)

Prompy can back up and restore your prompts using [Backendless](https://backendless.com).

1. Create a free Backendless app and grab its **REST API Key**
2. In Prompy, go to **Settings → Advanced Settings**
3. Paste your REST API Key into the **API Configuration** field
4. Use **Upload Prompts** to back up, or **Update Feed** to restore

> Cloud sync is entirely optional — Prompy works fully offline using local browser storage.

---

## Project Structure

```text
.
├── index.html        # The entire app — markup, styles, and logic
└── CHANGELOG.md       # Version history
```

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| UI | Vanilla HTML / CSS / JavaScript — no frameworks, no bundler |
| ZIP packaging | [JSZip](https://stuk.github.io/jszip/) |
| Cloud storage | [Backendless](https://backendless.com) *(optional)* |
| Local persistence | Browser `localStorage` |
