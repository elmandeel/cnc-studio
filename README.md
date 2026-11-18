# CNC Studio (Beta)

CNC Studio is a browser-based CNC milling simulator based on Fanuc 31i programming, created by Dr. Ali Almandeel with AI assistance. Designed for teaching and learning, it includes G-code editing, 2D and 3D simulation, and tool and stock setup. Currently in beta and under active development.

## Run online

[**Launch CNC Studio**](https://elmandeel.github.io/cnc-studio/)

Open the link in a modern web browser. No GitHub account or HTML download is required. You can share this same link in Microsoft Teams.

## Current version

**v147 — Automatic Updates**

Program edits and changes to stock, G54, and tool data update the simulation preview automatically. Valid text and numeric edits are applied after a short pause of approximately 450 milliseconds. A valid project change stops playback, rebuilds the preview, and returns the simulation to the start. Use **Play** or **Step** to animate the updated program.

Incomplete or invalid entries pause the update and retain the previous valid preview until corrected.

## Run locally

1. Download `index.html`.
2. Open it in a modern web browser.
3. Edit the included G-code or import a program, then configure stock, G54, and tools as needed.
4. Use **Play** or **Step** to run the simulation. Switch between **2D**, **3D**, and **Split view** as needed.

## Beta status

Features, simulation accuracy, and browser compatibility are still being developed and tested. Fanuc 31i programming is the reference for the simulator; this beta does not implement every command or controller behavior.

Phone-sized browser tests have been performed, including touch gestures. Physical iPhone and Android testing remains outstanding for this release.
