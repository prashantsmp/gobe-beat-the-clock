# ⏱️ Beat The Clock 10.000s — GoBe Robot Kiosk Game

> **Target Platform:** GoBe Telepresence & Commercial Service Robots  
> **Display Profile:** 1080 × 1920 (Full HD Portrait Kiosk Display)  
> **Architecture:** Single-file self-contained web app (`index.html`)  
> **Live Demo:** [https://prashantsmp.github.io/gobe-beat-the-clock/](https://prashantsmp.github.io/gobe-beat-the-clock/)

---

## 🎮 Game Concept & Rules

**Beat The Clock 10.000s** is a sensory-deprivation reflex arcade game engineered for touchscreen robot kiosks:

1. **Touch to Start:** Tap the tactile capacitive slam button to start the high-precision timer.
2. **The 5-Second Sensory Blindout:** At **05.000s**, the digital display and circular ring dial glitch out and black out completely (`??:??.???`).
3. **Slam at Exactly 10.000s:** Rely purely on your internal rhythm and tempo to slam the button at exactly **10.000 seconds**.
4. **Suspense Reveal:** The robot analyzes the telemetry for 650ms before revealing your millisecond offset and precision tier!

---

## 🏆 Precision Tiers

| Tier | Tolerance Window ($|\Delta = t - 10.000\text{s}|$) | Audio & Visual Feedback |
| :--- | :--- | :--- |
| **⚡ GOD TIER** | $< 0.001\text{s}$ (Exact 10.000s) | Golden aura, particle confetti barrage, victory fanfare |
| **🎯 SNIPER** | $\le 0.050\text{s}$ ($09.950\text{s} - 10.050\text{s}$) | Neon cyan badge, victory chord |
| **⚡ CLOSE CALL** | $\le 0.200\text{s}$ ($09.800\text{s} - 10.200\text{s}$) | Warning amber badge, mid-click tone |
| **💀 BUST** | $> 0.200\text{s}$ | Crimson badge, red LED pulse, fail buzzer |

---

## ⚙️ Technical Highlights

- **Anti-Drift Timer Engine:** Runs on `performance.now()` in a `requestAnimationFrame` loop to prevent JavaScript thread timing drift.
- **In-Memory Web Audio API Synth:** Zero external audio assets (no `.mp3` or `.wav` dependencies); procedural oscillators, noise buffers, and biquad filters synthesize all ticks, clicks, glitches, risers, and fanfares.
- **Capacitive Touch Ergonomics:** Built for GoBe robot kiosks using `pointerdown` to bypass the mobile 300ms click delay.
- **Responsive Kiosk Scaler:** Automatically fits and centers on any screen (desktop or mobile) while preserving the native $1080 \times 1920$ layout.
- **On-Screen Touch Keyboard:** Allows challengers to register their names without physical keyboards attached.
- **Local Persistence:** Retains player name and Hall of Fame high scores across browser refreshes via `localStorage`.
