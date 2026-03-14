# NEXUS

I got tired of having 10 browser tabs open just to check the time, jot something down, or stay focused. So I made my own little toolkit that lives on my computer.

---

## What's inside

Five HTML files. You put them in a folder and open `index.html`. That's genuinely it.

```
index.html           ← the home screen
memorygame.html      ← card matching game
clock.html           ← clock, stopwatch, countdown
procrastination.html ← focus timer + todo list
notepad.html         ← notes with markdown
```

---

## How to use it

Download the five files into the same folder. Open `index.html` in your browser. Click whatever you want to use.

If you want to run it through a local server for some reason:

```bash
npx serve .
# or
python -m http.server 8080
```

But honestly just double-clicking `index.html` works fine.

---

## The apps

**Memory Game** — flip cards and find matching pairs. Easy mode is 4×4, hard mode is 6×4. It tracks your moves and time. Nothing fancy, just a fun little thing to have around.

**Clock** — three tabs. An analog + digital clock, a stopwatch that goes down to centiseconds, and a countdown timer with a circular progress ring that pulses red when time is almost up.

**Focus Timer** — basically a Pomodoro timer. Pick 25, 15, or 50 minute sessions. It switches between focus and break automatically. There's also a small todo list underneath it that remembers your tasks between sessions.

**Notepad** — a simple notes app with a sidebar for multiple notes. It saves as you type, supports markdown if you want it, and you can export any note as a `.md` file. The editor uses a serif font which makes long writing sessions a lot more comfortable.

---

## A few things worth knowing

- Everything is saved in your browser's localStorage. No accounts, no servers, no cloud.
- The memory game resets when you close it. Everything else remembers where you left it.
- All five files are completely self-contained. There's no CSS folder, no JS folder, nothing else to manage.
- Fonts come from Google Fonts so you need internet the first time. After that it's cached and works offline.

---

## Changing things

It's all plain HTML so tweaking stuff is easy. Want different Pomodoro times? Find this line in `procrastination.html` and change the numbers:

```javascript
setMode(25, 5, 'Pomodoro', this) // focus minutes, break minutes
```

Want different colors? Every app has a block at the top that looks like this:

```css
:root {
  --accent: #7b61ff;
}
```

Change that hex code to whatever you want.

---

## Why I made this

I wanted tools that open instantly, don't ask me to sign in, don't have ads, and don't disappear when a startup shuts down. These live on my machine. They'll work ten years from now.

That was the whole idea.
