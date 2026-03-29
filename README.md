# 🍅 Focus Timer

A clean, distraction-free Pomodoro timer. No accounts, no tracking, no installation — just open and work.

**[→ Open the app](https://dsmyatskiy.github.io/focus-timer/)**

---

## Features

- **Three interval types** — Focus (Pomodoro), Short break, Long break
- **Automatic progression** — timer moves through intervals on its own; long break triggers after N completed pomodoros
- **Fully configurable** — adjust duration of each interval and how often the long break occurs
- **Session counter** — tracks pomodoros completed today, survives page reload; adjust manually with + / − or reset with one click
- **Alarm sounds** — three built-in sounds (Bell, Digital, Soft) plus upload your own audio file; adjustable volume
- **Persistent settings** — all preferences saved in browser localStorage, no account needed
- **Zero dependencies at runtime** — React loaded via CDN, everything else is vanilla JS and Web Audio API

## How it works

The classic Pomodoro cycle:

```
Focus → Short break → Focus → Short break → Focus → Short break → Focus → Long break → repeat
```

Default durations: 25 min focus / 5 min short break / 15 min long break / long break every 4 pomodoros. All configurable in Settings.

## Customization

All app-level settings live in a single config block at the top of `index.html`:

```js
window.APP_CONFIG = {
  appName: "Focus Timer",
  author: {
    email:  "your@email.com",
    github: "yourname",
  },
  defaults: {
    pomo:    25,     // focus duration, minutes
    short:    5,     // short break, minutes
    long:    15,     // long break, minutes
    cycle:    4,     // pomodoros before long break
    volume:   0.7,   // alarm volume 0–1
    sound:   "bell", // bell | digital | soft
  },
};
```

No build step needed — edit the file, push to GitHub, done.

## Deployment

The entire app is a single `index.html` file. Deploy anywhere that serves static files:

**GitHub Pages** (recommended, free)
1. Fork or clone this repository
2. Go to Settings → Pages → Source: `main` branch, `/ (root)` folder
3. Your app will be live at `https://username.github.io/focus-timer/`

**Any other static host** — Netlify, Vercel, Cloudflare Pages — just drop `index.html` and you're done.

## Tech stack

| What | How |
|---|---|
| UI | React 18 (via CDN, no build step) |
| Audio | Web Audio API — sounds synthesized in browser, no audio files |
| Storage | localStorage — settings and counter persist across sessions |
| Hosting | GitHub Pages |
| Dependencies | Zero npm packages |

## License

MIT — do whatever you want, just keep the copyright notice.

---

Made by [dsmyatskiy](https://github.com/dsmyatskiy) · [dsmyatskiy@gmail.com](mailto:dsmyatskiy@gmail.com)
