# CNC Studio (Beta)

CNC Studio is a browser-based CNC milling simulator based on Fanuc 31i programming, created by Dr. Ali Almandeel with AI assistance. Designed for teaching and learning, it includes G-code editing, 2D and 3D simulation, and tool and stock setup. Currently in beta and under active development.

## Run online

[**Launch CNC Studio**](https://elmandeel.github.io/cnc-studio/)

Open the link in a modern web browser. No GitHub account or HTML download is required.

## Current version

**v149 — Sequence Number Diagnostics**

Program errors identify the original **N sequence number**. Errors inside a numbered program also include its **O program number**, for example **O14 · N35**. This source location is preserved through repeated subprogram calls and expanded drilling/tapping cycles. A block without an N number is identified as **Unnumbered block**, with its code shown for context; selecting an error still targets the original editor block.

Use the **Sample Programs** dropdown to load **Face/Mill**, **Drill/Tap**, or **Subprogram**. Each selection loads its program, stock, G54, and tool setup. The separate sample buttons and the two classwork-specific stock/tool preset controls have been removed.

Program edits and changes to stock, G54, and tool data update the simulation preview automatically. Valid text and numeric edits are applied after a short pause of approximately 450 milliseconds. A valid project change stops playback, rebuilds the preview, and returns the simulation to the start. Use **Play** or **Step** to animate the updated program.

Incomplete or invalid entries pause the update and retain the previous valid preview until corrected.

## Add to the iPhone or iPad Home Screen

The custom CNC cutter icon and **CNC Studio** launch name are included. This icon update preserves the v149 simulator code and interface.

1. Open [CNC Studio](https://elmandeel.github.io/cnc-studio/) in Safari.
2. Tap **Share**, then **Add to Home Screen**.
3. Keep the name **CNC Studio**, enable **Open as Web App** if offered, then tap **Add**.

If an existing shortcut still shows the old icon, remove that shortcut and add it again from the refreshed website. The hosted app requires a connection to load; this update does not add offline caching.

## Run locally

1. Download `index.html`.
2. Open it in a modern web browser.
3. Edit the included G-code or import a program, then configure stock, G54, and tools as needed.
4. Use **Play** or **Step** to run the simulation. Switch between **2D**, **3D**, and **Split view** as needed.

## Beta status

Features, simulation accuracy, and browser compatibility are still being developed and tested. Fanuc 31i programming is the reference for the simulator; this beta does not implement every command or controller behavior.

Phone-sized browser tests have been performed, including touch gestures. Physical iPhone and Android testing remains outstanding for this release.

