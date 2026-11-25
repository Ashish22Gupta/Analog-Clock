# 🕰️ Analog Clock
### A Realistic, Roman-Numeral Wall Clock with Digital Readout

> ⚠️ **DISCLAIMER:** This is a **personal learning and portfolio project**. It demonstrates CSS transforms, real-time JavaScript date handling, and detailed skeuomorphic UI design. All logic runs entirely in the browser — no data is collected, stored, or transmitted.

A visually rich analog clock that renders a vintage wall-clock face — complete with Roman numerals, a linen-textured dial, golden hour markers, and an animated starfield backdrop. Three smooth-sweeping hands rotate in real time via CSS transforms, while a floating digital readout shows the exact time in `HH:MM:SS` format below the face.

![Version](https://img.shields.io/badge/Version-1.0.0-c9aa5f)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-F4B400)
![Responsive](https://img.shields.io/badge/Responsive-Desktop%20%26%20Mobile-2D6A4F)

---

## 🔗 Live Links

- **Live Demo:** [analog-clock-timer.netlify.app](https://analog-clock-timer.netlify.app/)
- **Source Code:** [github.com/Ashish22Gupta/Analog-Clock](https://github.com/Ashish22Gupta/Analog-Clock)

---

## ✨ Implemented Features

### 🕐 Real-Time Analog Hands
- **Accurate Hour Hand** - Rotates at `30° × hour + (minute / 2)` so it creeps smoothly between numerals instead of jumping.
- **Precise Minute Hand** - Rotates at `6° × minutes` for exact positional accuracy.
- **Smooth Second Hand** - Rotates at `6° × seconds`, ticking once per second via `setInterval(1000)`.
- **Live Transform Updates** - Each hand's `transform: rotate()` is recalculated every second.

### 🔢 Digital Time Readout
- **Floating Pill Display** - Glassmorphic badge below the clock shows `HH:MM:SS` in monospace.
- **Zero-Padded Format** - Uses `padStart(2, '0')` so hours, minutes, and seconds always display two digits.
- **Faster Refresh** - Digital readout updates every `500ms` for near-instant accuracy.
- **Initial Render** - `updateDigitalTime()` is called once on load so the display isn't blank for the first half-second.

### 🎨 Detailed Skeuomorphic Design
- **Roman Numeral Dial** - All twelve numerals (XII–I) placed via absolute positioning with serif `Times New Roman` styling.
- **SVG-Embedded Clock Face** - Inline data-URI SVG provides a radial-gradient backdrop with a linen texture pattern and dashed inner ring.
- **Golden Hour Dots** - Twelve small gold radial-gradient dots mark each hour position.
- **Layered Shadows** - Multi-layer `box-shadow` creates depth: outer drop shadow, beveled ring, and inner glass reflections.
- **Glass Reflection** - A soft radial highlight in the upper-left simulates a glass cover.
- **Metallic Hands** - Each hand uses linear gradients, rounded tips, and shadow highlights for a 3D look. The second hand is red with a glowing amber tip.
- **Center Pin** - A gold radial-gradient pin covers the pivot point where all three hands meet.

### 🌌 Animated Background
- **Radial Starfield** - Two offset radial-gradient dots create a subtle twinkling star effect.
- **Slow Drift Animation** - A 40-second `@keyframes` loops the background position for gentle motion.
- **Deep Space Gradient** - `radial-gradient(circle at 30% 10%, #0a0f2a, #03050b)` gives the page a cosmic feel.

### 📱 Fully Responsive Design
- **Desktop:** Clock face at `70vh` with `clamp()` font sizing for numerals.
- **Tablet (≤768px):** Clock shrinks to `55vh`; numerals reposition and shrink.
- **Mobile (≤480px):** Compact `45vh` face with `11px` numerals; hands re-centered for narrow viewports.
- **Touch-Friendly** - `user-select: none` prevents accidental text selection on tap.

### ♿ UX Details
- **No Cursor Blink** - The pointer stays stable; `overflow: hidden` on body prevents scrollbars.
- **Digital Hint Below** - Positioned at `bottom: -50px` with backdrop blur so it never overlaps the clock face.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Clock markup with layered divs for each hand and numeral |
| **CSS3** | Custom `conic-gradient` ticks, SVG data-URI background, multi-layer shadows, `clamp()` responsive typography, media queries |
| **Vanilla JavaScript** | Real-time `Date` API, transform rotation updates, digital time formatting |
| **SVG (inline data URI)** | Procedural clock-face rendering with gradients and textures |
| **Netlify** | Static hosting and deployment |

---

## 📁 Project Structure

```text
Analog-Clock/
├── index.html          # Clock structure: face layers, numerals, hands, digital hint
├── style.css           # Skeuomorphic styling, animations, responsive rules
└── script.js           # Hand rotation logic + digital time formattinga
