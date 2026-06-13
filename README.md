# Analog Stopwatch & Countdown Timer Application ⏱️

An advanced, feature-rich desktop GUI application engineered in Core Java using the **Java Swing** and **AWT Graphics** ecosystems. This project seamlessly blends precise digital state engines with a custom-rendered vector analog interface.

---

## 🚀 Key Architectural Features

- **Dual-Mode System Logic:** Effortlessly toggles dynamic processing states between an incremental stopwatch counter and a user-defined decremental countdown timer.
- **Trigonometric Vector Rendering:** Custom mathematical coordinate geometry (`Math.cos` and `Math.sin` vector tracking) computes pixel offsets to dynamically draw dial ticks and rotate the sweeping analog hand in real-time.
- **Asynchronous Execution Stack:** Leverages multiple concurrent instances of `javax.swing.Timer` executing in parallel execution frames to handle non-blocking live system clocks, countdown drops, and stopwatch updates.
- **Thread-Safe Operations:** Formats event cycles cleanly using `SwingUtilities.invokeLater()` to prevent runtime exceptions in window rendering threads.

---

## 🛠️ Core Technical Pillars Applied

1. **Custom Graphics & Anti-Aliasing:** Overrides `paintComponent()` inside an inner class structure, utilizing standard rendering hints to output crisp vector edges without relying on image resources.
2. **Event-Driven UI Patterns:** Harnesses the `ActionListener` design pattern to capture button triggers and gracefully direct application data states (Start, Stop, Reset, Set Timer).
3. **Data Validation Parsing:** Incorporates robust regular expression pattern filtering (`\\d+`) inside user dialog inputs to catch non-numeric entries and prevent calculation crashes.

---

## 📊 Operational Architecture

```text
                        ┌──────────────────────────────┐
                        │ User Interface (Java Swing)  │
                        └──────────────┬───────────────┘
                                       │
                      [intercepts user actions via buttons]
                                       │
                                       ▼
                       ┌──────────────────────────────┐
                       │   Central Event Router       │
                       │     (actionPerformed)        │
                       └───────┬──────────────┬───────┘
                               │              │
                    ┌──────────┘              └──────────┐
                    ▼                                    ▼
       ┌────────────────────────┐           ┌────────────────────────┐
       │     Stopwatch Mode     │           │    Countdown Mode      │
       ├────────────────────────┤           ├────────────────────────┤
       │ • Increments elapsed t │           │ • Decrements seconds t │
       │ • Computes Vector Hand │           │ • Spawns JDialog alert │
       │ • Updates timeLabel    │           │ • Updates timeLabel    │
       └────────────────────────┘           └────────────────────────┘
```
## 📋 Technical Prerequisites
Java Development Kit (JDK): Version 8 or higher.

Runtime Libraries: Standard javax.swing and java.awt native libraries (packaged out-of-the-box inside standard Java installations).

---
## 💻 Compilation & Deployment Steps
Step 1: Clone the Repository
```Bash
git clone [https://github.com/ayushkatiyar001/Stopwatch-Timer-App.git](https://github.com/ayushkatiyar001/Stopwatch-Timer-App.git)
cd Stopwatch-Timer-App
```
Step 2: Compile the Module Source
Compile the explicit package structure using the terminal:
```Bash
javac stopwatch/StopwatchTimerApp.java
```
Step 3: Run the Application Execution Hook
Fire up the byte-code engine by target-pointing the runtime classpath:
```Bash
java stopwatch.StopwatchTimerApp
```
---
## 📂 Structural Module Mapping
StopwatchTimerApp (Main Driver & View Context): Handles core lifecycle, thread structures, structural panels, button panels, and dialog operations.

DialPanel (Inner Dynamic Graphics Layout): Manages component redraw protocols, trigonometric angle updates, canvas clearances, and drawing algorithms for vector texturing.
