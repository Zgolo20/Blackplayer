# BlackPlayer — APK Build Guide (PWABuilder)

## Step 1: Host the PWA

Upload the `blackplayer/` folder to any static host.

### Option A — Cloudflare Pages (Recommended for you)
1. Go to https://dash.cloudflare.com → Workers & Pages → Create
2. Click **"Upload assets"** (no Git required)
3. Drag & drop the entire `blackplayer/` folder
4. Click Deploy → your URL will be like `blackplayer-xyz.pages.dev`

### Option B — Netlify Drop
1. Go to https://app.netlify.com/drop
2. Drag & drop the `blackplayer/` folder
3. Get your URL instantly (e.g. `blackplayer-abc.netlify.app`)

### Option C — GitHub Pages
1. Push `blackplayer/` contents to a GitHub repo
2. Settings → Pages → Deploy from branch → main / root
3. Your URL: `https://username.github.io/repo-name`

---

## Step 2: Verify PWA on PWABuilder

1. Go to **https://www.pwabuilder.com**
2. Enter your hosted URL and press **Start**
3. Wait for the score — it should be green ✓
   - Manifest: ✓
   - Service Worker: ✓
   - HTTPS: ✓ (all hosts above provide this)

---

## Step 3: Generate APK

1. Click **"Package for stores"**
2. Choose **Android**
3. Fill in:
   - **Package ID:** `com.blackplayer.app`
   - **App name:** `BlackPlayer`
   - **Version:** `1.0.0`
   - Leave signing as "Generate new"
4. Click **Download**
5. You get:
   - `BlackPlayer.apk` ← sideload this
   - `BlackPlayer.aab` ← for Google Play Store

---

## Step 4: Install on Huawei Y61

Since your device doesn't use Google Play:

1. Transfer `BlackPlayer.apk` to your device via USB
2. On the Y61: **Settings → Security → Unknown sources → ON**
3. Open a file manager → tap the `.apk` → Install
4. BlackPlayer appears on your home screen 🎵

> **Tip:** You can also install the PWA directly from Huawei Browser
> without building an APK — open your hosted URL in the browser,
> tap the menu (⋮) → "Add to home screen"

---

## File Structure

```
blackplayer/
├── index.html          ← Apple-style player (jet black theme)
├── manifest.json       ← PWA metadata & icons
├── sw.js               ← Service worker (full offline cache)
└── icons/
    ├── icon-72x72.png
    ├── icon-96x96.png
    ├── icon-128x128.png
    ├── icon-144x144.png
    ├── icon-152x152.png
    ├── icon-192x192.png
    ├── icon-384x384.png
    └── icon-512x512.png
```

---

## What's Included

| Feature | Status |
|---|---|
| Fully offline (service worker) | ✅ |
| Installable as app | ✅ |
| Standalone display (no browser chrome) | ✅ |
| Lock screen controls (Media Session API) | ✅ |
| Touch seek & volume | ✅ |
| Safe-area / notch support | ✅ |
| Adaptive (maskable) icons | ✅ |
| Theme color (pure black) | ✅ |
| Multi-file queue | ✅ |
| Shuffle & repeat modes | ✅ |
