# 🐾 Dog Trick School

A Progressive Web App (PWA) for teaching your dog tricks — with step-by-step guides and YouTube video links for every single one.

Built for Nova 🦴, a Golden Retriever puppy, but works for any dog.

![License](https://img.shields.io/badge/license-MIT-orange) ![PWA](https://img.shields.io/badge/PWA-ready-brightgreen) ![Tricks](https://img.shields.io/badge/tricks-growing-yellow)

---

## ✨ Features

- **Growing trick library** — each trick has full step-by-step instructions, easily extended by editing one array in `index.html`
- **YouTube video links** — 1–2 tutorial videos per trick, opening directly from the app
- **Personalised** — enter your dog's name on first launch and it replaces throughout the entire app
- **Progress tracking** — mark tricks as 🔥 Learning or ⭐ Done, with a live progress bar
- **Search & filter** — find tricks by name, difficulty, or status
- **Installable** — works as a home screen app on iPhone and Android
- **Offline support** — fully cached after first load via service worker
- **Persistent** — dog name and all progress saved to device storage, survives closing and reopening

---

## 📱 Live App

> **[https://your-username.github.io/Nova-trick](https://your-username.github.io/Nova-trick)**

*(Replace with your actual GitHub Pages URL)*

---

## 🚀 Installing on Your Phone

### iPhone (Safari)
1. Open the live URL in Safari
2. Tap the **Share** icon → **Add to Home Screen**
3. Tap **Add** — done

### Android (Chrome)
1. Open the live URL in Chrome
2. Tap the **three-dot menu** → **Add to Home Screen**
3. Or wait for the automatic install banner to appear

Once installed, the app opens full-screen like a native app and works offline.

---

## 🗂 Repository Structure

```
Nova-trick/
├── index.html   # The entire app — React, styles, and all trick data in one file
└── sw.js        # Service worker — handles offline caching
```

Both files must be in the same directory for the service worker to function correctly.

---

## 🛠 Deployment

### GitHub Pages (recommended — free & HTTPS)

1. Push both files to your `main` branch
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch → main → / (root)**
4. Save — your app will be live at `https://your-username.github.io/Nova-trick` within a minute

### Self-hosted (Nginx / Apache)

Upload both files to your web root:

```bash
scp index.html your-user@your-server:/var/www/html/index.html
scp sw.js your-user@your-server:/var/www/html/sw.js
```

> ⚠️ HTTPS is required for PWA installation and the service worker to activate. On GitHub Pages this is automatic. On a self-hosted server, use [Let's Encrypt](https://letsencrypt.org) for a free SSL certificate.

---

## 🔧 Tech Stack

| Technology | Purpose |
|---|---|
| React 18 (CDN) | UI and state management |
| Babel Standalone | In-browser JSX transpilation |
| Web App Manifest | PWA installability |
| Service Worker | Offline caching |
| localStorage | Persistent dog name and progress |
| YouTube thumbnail API | Video preview images |
| Google Fonts | Fredoka One + Nunito typefaces |

No build step. No dependencies to install. Just two files.

---

## 🐕 Tricks

Tricks are defined in the `tricks` array inside `index.html`. Each trick follows this structure:

```javascript
{
  id: 1,                        // unique number — increment for each new trick
  name: "Paw",                  // display name
  emoji: "🤝",                  // emoji shown on the card
  difficulty: "Easy",           // "Easy", "Medium", or "Hard"
  time: "1 hour",               // estimated training time
  prerequisite: "Sit",          // "None" or the name of a required trick
  description: "Short summary shown in the modal.",
  videos: [
    { id: "YouTubeVideoID", title: "Video title shown in the app" }
  ],
  steps: [
    "Step one instruction.",
    "Step two instruction.",
    // up to 6 steps recommended
  ]
}
```

### Adding a new trick

1. Open `index.html` in any text editor
2. Find the `const tricks = [` array (near the top of the `<script>` block)
3. Copy an existing trick entry and paste it at the end of the array (before the closing `]`)
4. Update every field — give it the next available `id` number
5. Find a YouTube tutorial, grab the video ID from the URL (`youtube.com/watch?v=`**`THIS_PART`**), and add it to the `videos` array
6. Save the file, commit, and push — GitHub Pages will redeploy within a minute

### Difficulty levels

| Value | Meaning |
|---|---|
| `"Easy"` | 🟢 Good for beginners and puppies |
| `"Medium"` | 🟡 Requires a foundation trick or more sessions |
| `"Hard"` | 🔴 Physically demanding or multi-step combinations |

---

## 📝 Notes

- Jumping tricks (Jump Over, Jump Onto Back) are not recommended for dogs under 12 months as joints are still developing
- Roll Over and similar tricks are best suited to physically fit dogs
- The app uses positive reinforcement methods throughout — no punishment-based techniques
- Treat calories should stay within ~10% of your dog's daily intake; reduce meal portions on heavy treat days

---

## 📄 License

MIT — free to use, share, and modify.

---

*Made with 🐾 for Nova and dogs everywhere.*
