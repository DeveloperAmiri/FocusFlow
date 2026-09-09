<div align="center">

# 🍅 FocusFlow

**A beautiful Pomodoro timer with task tracking, streaks and stats — all in one file.**

Glassmorphism UI · zero dependencies · your data never leaves your browser.

![HTML](https://img.shields.io/badge/HTML5-%20100%25-E34F26?logo=html5&logoColor=white)
![JS](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green)
![Dependencies](https://img.shields.io/badge/dependencies-0-success)

</div>

---

## ✨ Features

- 🍅 **Classic Pomodoro cycles** — 25 min focus → 5 min short break → after 4 cycles a 15 min long break (all lengths configurable)
- ⏱ **Animated progress ring** — gradient ring that glows in the mode's color, with a live countdown in the tab title
- ✅ **Task tracking** — add tasks with estimated 🍅 counts, mark one active, and watch it earn pomodoros as you complete focus sessions
- 📊 **Stats that motivate** — 🍅 today, focus minutes, day streak 🔥 and lifetime total, persisted in `localStorage`
- 🌴 **Auto-flow** — sessions chain automatically (toggleable), so you can stay in the zone
- 🔔 **Gentle reminders** — a soft WebAudio chime + browser notifications (opt-in) when a session ends
- 🌗 **Dark & light themes** — glassmorphism in both
- ⌨️ **Keyboard shortcuts** — `space` start/pause · `r` reset · `s` skip

## 🚀 Quickstart

```bash
git clone https://github.com/DeveloperAmiri/FocusFlow.git
cd FocusFlow
open index.html        # or just double-click it — no server, no build
```

## 🎮 How it works

1. Add a task (e.g. *"finish the report"* · estimate 3 🍅) and click it to make it active
2. Hit **start** and focus until the chime
3. Take your break — the next session auto-starts when it's over
4. Each completed focus session adds a 🍅 to your active task and your daily stats

| Key | Action |
|---|---|
| `space` | start / pause |
| `r` | reset the current session |
| `s` | skip to the next session (no credit) |

## 🧠 Implementation notes

- **Drift-free timer** — remaining time is derived from `Date.now()` timestamps every 250 ms, so the clock never accumulates error even if the tab throttles
- **State machine** — `focus → short → focus … → long` with a 4-session cycle counter; skipping never grants credit
- **Mode theming via CSS custom properties** — `body[data-mode]` swaps the accent color, and the SVG ring reads it through `stroke: var(--mode-color)`
- **Streak logic** — the streak rolls over at midnight only when the previous active day was yesterday
- Everything persists to `localStorage` (settings, tasks, stats) — no accounts, no network calls, no tracking
- Fonts load from Google Fonts (Fraunces & Inter) when online, with system-serif/sans fallbacks offline

## 📄 License

Released under the [MIT License](LICENSE) — © 2026 DeveloperAmiri
