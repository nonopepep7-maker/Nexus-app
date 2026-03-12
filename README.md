# NEXUS — Personal App Suite

> A polished, zero-dependency collection of five single-file web apps with a unified dark aesthetic, smooth animations, and local-first data storage.

---

## ✨ Overview

**NEXUS** is a handcrafted personal productivity suite built entirely in vanilla HTML, CSS, and JavaScript — no frameworks, no build tools, no internet required after the first font load. Every app shares a cohesive dark design language with animated backgrounds, micro-interactions, and a consistent typographic system.

```
nexus/
├── index.html          ← Launcher Hub
├── memorygame.html     ← Memory Card Game
├── clock.html          ← Clock · Stopwatch · Countdown
├── procrastination.html← Focus Timer + Task Tracker
└── notepad.html        ← Markdown Notepad
```

---

## 🚀 Quick Start

No installation. No server. No dependencies.

1. **Download** all five `.html` files into the same folder.
2. **Open** `index.html` in any modern browser.
3. **Click** any app card to launch it in a new tab.

```bash
# Optional: serve locally for best experience
npx serve .
# or
python -m http.server 8080
```

> ⚠️ All five files **must live in the same directory** for the launcher links to work correctly.

---

## 📦 Apps

### 🏠 Launcher Hub — `index.html`

The central home screen for the suite.

- Animated orb background with layered noise texture
- Live digital clock updating every second
- Four glowing app cards with hover shimmer effects
- Scan-line overlay and corner bracket decorations
- Staggered card entrance animations on load

---

### 🧩 Memory Game — `memorygame.html`

A classic flip-and-match card game with polished 3D animations.

| Feature | Details |
|---|---|
| **Difficulty** | Easy (4×4, 8 pairs) or Hard (6×4, 12 pairs) |
| **Card flip** | CSS 3D `rotateY` with `perspective` |
| **Match effect** | Green glow + scale pop animation |
| **Miss effect** | Red shake + auto-flip back after 700ms |
| **Stats** | Live move counter, elapsed timer, pairs found |
| **Emoji deck** | 24 unique emoji symbols, randomised each game |

**How to play:** Click any card to flip it. Find its matching pair before it flips back. Match all pairs to win.

---

### ⏱ Clock — `clock.html`

Three tools in one tabbed interface.

#### Analog & Digital Clock
- Smooth-sweep second hand (updates every 100ms)
- Hour, minute, and second hands with correct compound rotation
- Full date display (weekday, month, day, year)

#### Stopwatch
- Centisecond precision (`mm:ss.cs` format)
- Lap recording with full history list
- Start / Pause / Resume / Reset / Lap controls

#### Countdown Timer
- Input hours, minutes, and seconds
- Circular SVG progress ring with linear stroke animation
- Urgency pulse animation when ≤ 10 seconds remain
- Ring turns green on completion

---

### 🚀 Focus Timer — `procrastination.html`

A Pomodoro-style focus assistant with task management.

#### Timer Modes

| Mode | Focus | Break |
|---|---|---|
| Pomodoro | 25 min | 5 min |
| Short | 15 min | 5 min |
| Deep Work | 50 min | 10 min |

#### Features
- Circular SVG ring progress indicator
- Automatic phase switching (focus → break → focus)
- Session counter, streak counter, total minutes focused
- Break ring turns amber to distinguish from focus phase
- **Task list** with add, complete, delete, and clear-done actions
- Tasks persist across sessions via `localStorage`
- Rotating motivational quotes on each page load
- Skip button to advance phase manually

---

### 📝 Notepad — `notepad.html`

A fast, distraction-free writing environment.

| Feature | Details |
|---|---|
| **Multiple notes** | Sidebar list with title + preview + date |
| **Auto-save** | Debounced 400ms save to `localStorage` |
| **Markdown preview** | Toggle between raw and rendered view |
| **Supported MD** | Headings, bold, italic, code, blockquote, lists, links, HR |
| **Export** | Download current note as `.md` file |
| **Status bar** | Live word count, character count, line count, time |
| **Fonts** | Editor uses *Lora* serif for comfortable long-form writing |

> Notes are saved automatically to the browser's `localStorage`. They persist between sessions but are browser- and device-specific.

---

## 🎨 Design System

All apps share a unified visual language:

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#080810` | Page background |
| `--surface` | `#0f0f1a` | Cards, inputs, panels |
| `--border` | `rgba(255,255,255,0.08)` | Subtle separators |
| `--text` | `#e8e8f0` | Primary text |
| `--muted` | `#6b6b8a` | Labels, hints, metadata |

#### App Accent Colors

| App | Color | Hex |
|---|---|---|
| Launcher | Violet | `#7b61ff` |
| Clock | Coral | `#ff6b6b` |
| Focus | Emerald | `#06d6a0` |
| Notepad | Amber | `#ffd166` |
| Memory | Violet | `#7b61ff` |

#### Typography
- **Display / Headings** — [Syne](https://fonts.google.com/specimen/Syne) (800 weight)
- **Body / UI / Code** — [DM Mono](https://fonts.google.com/specimen/DM+Mono) (300–500)
- **Notepad Editor** — [Lora](https://fonts.google.com/specimen/Lora) (400/600, serif)

Fonts load from Google Fonts CDN. The apps remain fully functional offline after the initial font cache is populated.

---

## 💾 Data & Privacy

| App | Storage | Data |
|---|---|---|
| Memory Game | None | Stateless; resets on page load |
| Clock | None | Reads system clock only |
| Focus Timer | `localStorage` | Task list (`nx-tasks`) |
| Notepad | `localStorage` | All notes (`nx-notes`) |

- **No accounts.** No sign-up. No tracking.
- **No network requests** beyond Google Fonts (CSS + font files).
- **All data stays on your device** in your browser's local storage.
- To clear data: open DevTools → Application → Local Storage → delete keys.

---

## 🌐 Browser Compatibility

| Browser | Status |
|---|---|
| Chrome / Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Safari 15+ | ✅ Full support |
| Mobile (iOS/Android) | ✅ Responsive |

Requires: CSS custom properties, CSS Grid, `backface-visibility`, `localStorage`, ES6.

---

## 📁 File Structure

```
.
├── index.html            # Hub launcher — open this first
├── memorygame.html       # Memory card game
├── clock.html            # Clock / Stopwatch / Countdown
├── procrastination.html  # Focus timer + tasks
└── notepad.html          # Markdown notepad
└── README.md             # This file
```

All five files are **self-contained**. Each one embeds its own CSS and JavaScript inline — there are no external `.css` or `.js` files to manage.

---

## 🛠 Customisation

Since everything is plain HTML/CSS/JS, customisation is straightforward:

**Change accent colors** — edit the `:root` CSS variables at the top of any file:
```css
:root {
  --accent: #your-color;
  --glow: rgba(r, g, b, 0.35);
}
```

**Change Pomodoro durations** — edit the mode buttons in `procrastination.html`:
```javascript
setMode(25, 5, 'Pomodoro', this)  // focus mins, break mins, label
```

**Add more emoji to the memory game** — extend the `EMOJIS` array in `memorygame.html`.

**Add more motivational quotes** — extend the `QUOTES` array in `procrastination.html`.

---

## 📄 License

Free to use, modify, and distribute for personal use.

---

*Built with care — no frameworks harmed in the making of this suite.*
