# THE FABRIC
### A Computational Study on Relational Mechanics.

> "Relationships are not static objects found in the dark; they are active conditions of maintenance."

**[Live Exhibition](https://gz2436.github.io/Creative-Coding-25Fall/)**

---

## Gallery

![State 1](final/pic/sr-1.png)

![State 2](final/pic/sr-2.png)

![State 3](final/pic/sr-3.png)

---

## I. Concept & Ideation
**Theme:** *Relationships as Conditions*

This project, titled **"The Fabric"**, is the culmination of a semester-long exploration into visualizing abstract human mechanics. While the Midterm studies (*Distance, Threshold, Presence*) focused on static fields distorted by the mouse, the Final Project seeks to embody the **viscosity and elasticity** of real intimacy.

The central metaphor is a "woven fabric." Relationships are interconnected nodes. When one node moves, it pulls its neighbors. The interaction is designed to be physical and consequential:
*   **Open Hand (Touch)**: Represents gentle influence. The fabric deforms slightly but maintains its structure.
*   **Closed Fist (Grip)**: Represents tension, obsession, or control. The fabric is pulled violently towards the center, potentially distorting the grid beyond recognition.

## II. Development Process
The transition from Midterm to Final involved a significant technical leap from standard interaction (Mouse) to physical embodiment (Hand Tracking).

1.  **Midterm Foundation**: I started by refining the particle systems from the midterm studies, ensuring the code structure was modular (Nodes, Grid, Update Loop).
2.  **Sensor Integration**: I integrated **ml5.js** (HandPose) to replace the mouse cursor. This allows the user to effect change from a distance, mirroring the theme of "action at a distance."
3.  **Aesthetic Refinement**: A critical part of the process was unifying the visual language—moving away from "tech demo" aesthetics to a "Museum Minimalist" style (Monochrome, Inter font, copious whitespace).

## III. Challenges & Solutions

### 1. The "Memory Trace" (Physics Logic)
**The Problem**: Initially, the grid felt too "bouncy." As soon as the hand was removed, the particles snapped back to their original positions instantly. This felt robotic and lacked emotional weight.
**The Solution**: I implemented a variable easing system in the physics engine.
*   *Active State*: High responsiveness (`lerp 0.1`) when interacting.
*   *Recovery State*: Extremely low viscosity (`lerp 0.02`) when healing.
This creates a **"Memory Trace"**—if you disturb the field, the "scar" of that interaction lingers for seconds before fading, symbolizing how relationships hold the memory of past conflicts.

### 2. Layout Stability (The FOUT Issue)
**The Problem**: On high-res displays, the transition from the loading screen to the art piece would "jump" visibly because the web fonts (`Inter`) hadn't finished loading before the canvas was centered.
**The Solution**: I constructed a `document.fonts.ready` promise chain. The application now forces a wait state until the typography is pixel-perfectly rendered before removing the overlay, ensuring a seamless, cinema-like entry.

---

## IV. Technical Stack
*   **Language**: HTML5, CSS3, Vanilla JavaScript (ES6+)
*   **Libraries**:
    *   [p5.js](https://p5js.org/) (Canvas rendering)
    *   [ml5.js](https://ml5js.org/) (Computer Vision / HandPose)
*   **Typography**: Inter (Google Fonts)

---
*Fall 2025 Creative Coding Final*
