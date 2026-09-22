# PS3 XMB True Wave Audio Engine

An interactive, high-fidelity replication of the legendary PlayStation®3 XMB (XrossMediaBar) background wave animation, complete with its iconic ambient soundscape synthesized entirely in the browser.

![PS3 Wave Preview](https://img.shields.io/badge/Platform-HTML5%20%2F%20Canvas-blue?style=flat-square)
![Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## Features

- **Iconic Wave Animation**: A three-layer canvas-rendered wave system with distinct colors, line weights, frequencies, and speeds that capture the deep, fluid aesthetic of the original PS3 background.
- **Dynamic Vignette**: A radial gradient overlay mimicking a classic television CRT display/console UI setup.
- **Floating Particles**: Drifting boundary-faded particles designed to run infinitely without loop-reset snapping.
- **Procedural Ocean Wave Soundscape**: A custom white noise generator passed through a modulating bandpass filter (controlled by synchronous LFOs) to simulate ocean waves crashing and receding, offering a completely non-tonal, soothing, and relaxing ambient backdrop.
- **Zero Dependencies**: Pure Vanilla HTML5, CSS3, and modern ES6 JavaScript. No bundlers, no npm, no heavy assets—just open and play!

---

## Getting Started

### Prerequisites

You only need a modern web browser that supports the **Web Audio API** and **HTML5 Canvas** (e.g., Google Chrome, Mozilla Firefox, Microsoft Edge, or Apple Safari).

### How to Run

1. **Clone the Repository** or download the files:
   ```bash
   git clone <your-repo-url>
   cd PS3-animation
   ```
2. **Open the `index.html`**:
   Simply double-click `index.html` in your file explorer to open it in your browser, or open it via a local server (like Live Server in VS Code).
3. **Initialize System**:
   Click anywhere on the screen to initialize the Web Audio context, activate the background audio synthesizers, and fade out the welcome screen.

---

## How It Works

### Wave Mathematics
The beautiful waves are drawn on a `<canvas>` using a combination of sine and cosine functions operating over a continuous `timestamp % LOOP_DURATION` loop. By mapping the x-coordinates through:
$$y = A \sin(\omega_1 x + \phi_1) \cos(\theta) + B \cos(\omega_2 x - \phi_2) \sin(\theta)$$
the animation maintains continuous flow without any abrupt jumps or cuts.

### Web Audio Synthesizer
The audio system generates a **Procedural Ocean Wave**: a custom white noise buffer modulating its bandpass center cutoff frequency around $500\text{Hz}$ via a slow $0.08\text{Hz}$ LFO. This creates an infinite, non-tonal wave crash and recede simulation, preventing any ear-fatigue or static humming over long listening sessions.

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.
