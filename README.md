# Robotic Ball II Web Controller

A zero-dependency, single-page web app to connect to and control the Robotic Ball II (SW23) using the **Web Bluetooth API**.

## Features

1. **Direct Connection**:
   - One-click Web Bluetooth pairing (filters for `SW23*` prefix and Service `0xFFF0`).
   - Listens to incoming notifications on characteristic `0xFFF6` for battery and firmware info.
2. **Directional D-Pad**:
   - 8-way directional buttons (Forward, Backward, Diagonals, Left/Right Aim).
   - Speed slider (10% - 100%) and Step duration slider (0.2s - 3.0s).
   - Dedicated **Immediate Stop** and **Reset / Re-center** buttons.
3. **Lighting & Effects**:
   - HTML5 color picker to set any custom solid RGB LED color.
   - Presets for Breathe, Rainbow, and Dazzle modes.
   - Lights off toggle.
4. **Sequence Programmer (Macros)**:
   - Simple line-by-line scripting area to program automated routines.
   - Commands:
     - `speed <10-100>`
     - `forward <seconds>`
     - `back <seconds>`
     - `left <seconds>`
     - `right <seconds>`
     - `aim <degrees>` (e.g. `aim 90`, `aim -90`)
     - `led <r> <g> <b>`
     - `mode <breathe|rainbow|dazzle>`
     - `wait <seconds>`
     - `stop`
   - Real-time **Abort** button.
5. **Live Diagnostic Log**:
   - Inspects all raw outgoing (`TX`) and incoming (`RX`) hex frames.

## How to Run

Web Bluetooth requires either **HTTPS** or **`http://localhost`**.

### Quick Local Server with Python:

From the repository root:
```bash
python3 -m http.server 8000 --directory webapp
```

Then open Chrome, Edge, or any Web Bluetooth supported browser at:
[http://localhost:8000](http://localhost:8000)
